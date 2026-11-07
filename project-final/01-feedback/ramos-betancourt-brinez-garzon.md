# Retroalimentación · Revisión del 7 de noviembre

**Proyecto:** Flota Alto Magdalena S.A.S. · Confiabilidad de una flota de transporte del Huila (empresa ficticia)
**Estudiantes:** Isabella Ramos Betancourt y José Julián Briñez Garzón
**Revisión:** sábado 7 de noviembre de 2026 · Docente Jesús Ariel González Bonilla
**Avance revisado:** fork `Isarb-21`, `14-week/02-optional-activity/proyecto_aula_c3_flota.ipynb`, commit «Avance del Proyecto»

La Fase 1 está muy bien resuelta. La ficha, la pregunta medible, el MTBF, las tres fuentes, la generación con semilla, el diagnóstico, las correcciones con antes, después y motivo, la bitácora, el diccionario, el grano y las cuatro consultas están presentes. Las cifras de las consultas cuadran entre sí: 220.757 horas de operación y 1.477 fallas por tipo y por turno.

**La prioridad para el sábado 14 de noviembre es completar las partes 6 a 9 y demostrar la respuesta a la pregunta.** El cuaderno llega hasta la parte 5.

## 1. Lo que hay que demostrar

El «Overview» ya afirma resultados que todavía no se calculan en el cuaderno: el MTBF de 171,7 a 132,9 horas, la caída de 22,6 % y el hallazgo principal. El cálculo es coherente con el total de horas, pero debe verse en las partes 6 y 7.

La consulta 4 filtra de entrada tractocamiones, volquetas, frenos y llantas. Muestra que esas fallas subieron (112 a 204), pero no prueba que sean las que explican la caída, porque no se compara con el resto. Antes de concluir:

- Calcule el cambio entre semestres para **todos** los tipos de vehículo y **todos** los sistemas.
- Muestre qué parte del aumento total de fallas (de S1 a S2) aporta cada combinación.
- Si el aumento se reparte en otros sistemas, ajuste la conclusión.

## 2. Turno de noche: revise la interpretación

La conclusión de que falta cobertura técnica en la noche va más allá de lo que muestran los datos. El diccionario define `turno` como el turno en que **se atendió** la falla, mientras que el «Overview» dice que la noche **concentra las fallas**. Son cosas diferentes.

Además, para saber si la noche falla más hay que comparar con las horas operadas por turno, que hoy no existen. Dos opciones: agregar ese dato o presentar el resultado solo como la carga del taller por turno.

## 3. Consulta 3 y meses pico

La consulta 3 cuenta fallas por mes, pero el conteo depende de cuánto operó la flota ese mes. La pregunta es sobre MTBF, así que los picos de junio y octubre deben revisarse con horas ÷ fallas por mes antes de recomendar la preparación del taller.

## 4. Datos sintéticos: qué decir en la sustentación

Los patrones del proyecto se programaron en el generador (más fallas de mayo a octubre, noche, frenos y llantas). Eso es válido y está bien documentado. Lo importante es presentarlo con claridad:

- El cuaderno recupera un patrón diseñado, no descubre una causa real.
- Las explicaciones como lluvias o temporadas de carga son supuestos del caso, no resultados del análisis.

Tengan listas las razones de cada decisión de limpieza. Por ejemplo, por qué el límite de 240 horas y por qué los costos vacíos no se imputan. Cada integrante debe poder explicar cualquier celda.

## 5. Lo que sigue para la Fase 2

| Parte | Qué debe quedar |
|---|---|
| 6 · Análisis temporal | MTBF por mes, promedio móvil y comparación S1 frente a S2 |
| 7 · Tablero | Fila de KPI (MTBF, MTTR y costo por falla) y cuatro gráficos o más, con títulos que digan el hallazgo |
| 8 · Cifras de control | Filas antes y después, valor del KPI principal y dos totales recalculables |
| 9 · Historia y recomendación | Contexto, hallazgo y recomendación: qué hacer, quién y cuándo |

**Qué decisión apoya cada gráfico.** Cada uno debe llevar a una acción del jefe de taller: qué vehículos revisar, qué sistema priorizar y en qué mes. Si un gráfico no cambia ninguna decisión, sobra.

**Antes de entregar:**

- Ejecutar «Reiniciar y ejecutar todo» y confirmar que corre de principio a fin, generación de datos incluida.
- Revisar que las cifras del «Overview» coincidan con las de las partes 6 a 9.
- Diligenciar el FO-IV-159 con los dos integrantes.
- Asegurar que los aportes de ambos integrantes queden en evidencia.

**Entrega:** sábado 14 de noviembre a las 23:59, solo en c3-project de Moodle (FO-IV-159 y ZIP de anexos), un envío por pareja. El avance en GitHub no reemplaza esa entrega.
