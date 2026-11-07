# Retroalimentación · Revisión del 7 de noviembre

**Proyecto:** LogiNeiva S.A.S. · Control y trazabilidad de inventarios con RFID (empresa ficticia)
**Estudiante:** Julián Andrés Cabrera Murcia
**Revisión:** sábado 7 de noviembre de 2026 · Docente Jesús Ariel González Bonilla
**Avance revisado:** fork `julian235234r54`, `14-week/02-optional-activity/Productos/` (cuaderno, datos, base SQLite, capturas y FO-IV-159)

El avance va adelantado en estructura: ya hay carga, limpieza, SQLite, consultas, KPI, una serie mensual y un tablero. Además, el caso es propio y tiene sentido logístico.

**La prioridad para el sábado 14 de noviembre es que las cifras del cuaderno sean confiables.** Hoy el texto, los resultados y la base de datos dicen cosas distintas, y eso se debe resolver antes de pulir el tablero.

## 1. Los resultados cambian en cada ejecución

Los errores de calidad se inyectan con `random` sin semilla, de modo que cada ejecución produce otros datos. Por eso las cifras no coinciden:

| Dato | En el texto | En la salida del cuaderno | En `inventario_rfid.db` |
|---|---|---|---|
| Filas de productos tras la limpieza | 214 | 178 | 181 |
| Precisión del inventario | 93,04 % | 93,68 % | |
| Trazabilidad RFID | 90,21 % | 89,58 % | |
| Categorías vacías | 40 | 20 | |
| Bebidas | ≈ 45 | 41 | |
| SIN_CATEGORIA | ≈ 38 | 20 | |
| Ubicación con más lecturas | I9 | J9 | |

Qué hacer:

- Fijar una semilla al inicio (`random.seed(2026)` y `np.random.seed(2026)`).
- Mejor aún, generar una sola vez el archivo sucio, guardarlo y limpiar siempre ese archivo.
- Ejecutar «Reiniciar y ejecutar todo» y escribir el análisis al final, con las cifras definitivas.
- El tablero (celda 54) no debe llevar valores escritos a mano. Debe leerlos de las variables.
- El cuaderno lee `datos/inventario_rfid.xlsx`, pero en el repositorio el archivo es `Productos/Inventario_rfid.xlsx`. La ruta debe funcionar en cualquier equipo.

## 2. Los datos no cumplen el mínimo de una empresa ficticia

| Requisito de la guía | Cómo está | Ajuste |
|---|---|---|
| Tabla principal con 1.000 filas o más | Movimientos y lecturas tienen 300; productos, 150 | Ampliar movimientos o lecturas |
| 12 meses de historia o más | 10 meses (enero a octubre de 2026) | Ampliar la historia |
| Documentar cómo se generaron los datos | No aparece | Explicar herramienta y reglas |
| Datos con temporadas y patrones | Sin reglas documentadas | Definir temporadas, productos de alta rotación o zonas problemáticas, para que exista un hallazgo |

## 3. La limpieza deja problemas sin resolver

- **Duplicados:** se agregaron 40, pero el diagnóstico solo detecta 12 y al final quedan 2 en el cuaderno, aunque el texto dice que no quedó ninguno. En la base entregada, además, 36 filas repiten un `id_producto`. Como antes de limpiar se dañaron columnas, `drop_duplicates()` ya no las reconoce como iguales. Conviene deduplicar por `id_producto`.
- **Identificadores en 0:** se dañaron 10 `id_producto` y la limpieza no los corrige. Esas filas quedan sin poder cruzarse con movimientos ni lecturas.
- **Diagnóstico incompleto:** solo cuenta duplicados y nulos. Faltan los stocks negativos, las ubicaciones «ERROR», los nombres vacíos y las cantidades por fuente.
- **Stock vacío o negativo:** al reemplazarlo por 0 se afirma que no hay existencias, y eso cambia el análisis. Evalúe dejarlo vacío o marcarlo como «por verificar», y justifique la decisión.
- **Antes, después y motivo:** la guía pide los tres por cada corrección, más una bitácora final. Hoy solo está el código.
- **Las otras dos tablas:** movimientos y lecturas pasan a SQLite sin revisión. En la base entregada, 14 movimientos corresponden a productos que no están en la tabla limpia, un efecto de los identificadores dañados.

## 4. SQL: faltan dos de las consultas exigidas

Las cuatro consultas son de una sola tabla. La guía exige también:

- **Un JOIN:** por ejemplo, unidades que salieron por categoría, uniendo `movimientos` con `productos`.
- **Un filtro por fechas:** por ejemplo, salidas del segundo semestre o de un trimestre.

La tercera consulta suma entradas y salidas como una sola cantidad, así que no mide rotación. Separe por `tipo_movimiento`. Falta también el diccionario de datos y el grano de la tabla principal (qué representa una fila).

## 5. Pregunta y KPI: lo más importante para que el proyecto tenga hallazgo

**La pregunta.** «¿De qué manera la implementación de RFID puede optimizar…?» no se puede responder con estos datos, porque no hay un antes y un después de RFID. La guía pide una pregunta concreta y medible. Ejemplo: «¿Qué categorías y zonas de la bodega concentran las diferencias entre la ubicación registrada y la ubicación detectada por RFID entre enero y diciembre?».

**La precisión del inventario.** Hoy se calcula filas limpias ÷ filas totales. Eso mide cuántas filas sobrevivieron a la limpieza, no qué tan preciso es el inventario, y además depende de los errores que usted mismo agregó. Sus datos permiten un KPI real:

> Precisión de ubicación = lecturas donde `ubicacion_detectada` coincide con `ubicacion` del producto ÷ total de lecturas × 100.

Con los datos originales ese valor da 2,3 %, porque las ubicaciones parecen asignadas al azar. Antes de usarlo, ajuste la generación para que la mayoría coincida y solo algunas zonas o categorías concentren las diferencias.

**La rotación.** Debe usar salidas ÷ stock promedio; el valor actual es el promedio de unidades movidas por producto.

**Qué decisión apoya cada resultado.** Por ejemplo, «Top 10 con mayor stock» debe decir quién actúa y qué hace con esa información. Las recomendaciones actuales son generales («implementar», «monitorear», «capacitar»): indiquen qué producto o zona, quién y cuándo.

## 6. Lo que sigue para la Fase 2

- **Análisis temporal:** hoy se agrupa por número de mes. Falta el promedio móvil y la comparación entre periodos.
- **Tablero:** cada gráfico debe tener un título que diga el hallazgo («Bebidas concentra…»), no solo el nombre de la variable.
- **Cifras de control:** filas antes y después, valor del KPI y dos totales recalculables.
- **Partes de la guía que faltan:** ficha del proyecto y «Overview & insights» en inglés (mínimo seis oraciones). Conviene además ordenar el cuaderno según la sección 5 de la guía.
- **FO-IV-159:** falta la fecha de cierre, el número de estudiantes, la hoja ESTUDIANTE, la bibliografía y los productos del proyecto. No suba al repositorio la hoja ESTUDIANTE ya diligenciada, porque tiene datos personales: va solo por Moodle.

**Entrega:** sábado 14 de noviembre a las 23:59, solo en c3-project de Moodle (FO-IV-159 y ZIP de anexos). El avance en GitHub no reemplaza esa entrega.
