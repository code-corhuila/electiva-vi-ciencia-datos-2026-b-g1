# Retroalimentación · Revisión del 7 de noviembre

**Proyecto:** Trilladora Cumbres del Macizo S.A.S. · Factor de rendimiento del café (empresa ficticia)
**Estudiante:** Cristhian Gaitán Guzmán (individual)
**Revisión:** sábado 7 de noviembre de 2026 · Docente Jesús Ariel González Bonilla
**Avance revisado:** fork `cristhiangg61-cmd`, `14-week/02-optional-activity/proyecto-aula/` (`Proyecto_Aula_CGG.ipynb` y `Fase0_Proyecto_Aula_CGG.md`)

La definición del proyecto es sólida: la pregunta es concreta, el KPI tiene fórmula y se explica por qué se calcula con totales y no promediando factores. También separa bien lo que es del sector (la referencia de 94 kg) de lo que serán supuestos del generador.

**La prioridad es arrancar ya los datos.** El cuaderno solo tiene la Fase 0. Hoy era la revisión de la Fase 1 y las partes 2 a 9 están en «pendiente», de modo que en una semana hay que construir casi todo el proyecto.

## Qué sigue, en orden

1. **Generador de datos:** archivos `lotes_recepcion.csv` y `proveedores.xlsx`, con semilla fija, reglas documentadas, 1.000 filas o más, 12 meses o más y tres problemas de calidad o más a propósito.
2. **Partes 2 a 5:** carga, diagnóstico con cifras, limpieza con antes, después y motivo, bitácora, diccionario, grano, SQLite y tres consultas o más.
3. **Partes 6 a 9:** factor por mes, promedio móvil, comparación entre semestres, tablero, cifras de control y recomendación.
4. **Parte 0:** reemplazar la plantilla por el texto final en inglés.

## Cuidados

- Como la trilladora está en la lista de ideas de la guía, sus datos, nombre y reglas deben ser propios. Dos proyectos con la misma empresa ficticia, los mismos datos o el mismo cuaderno quedan en 0,0.
- Defina desde el generador qué proveedores y meses se comportan distinto. Si todo sale parejo, no habrá hallazgo ni recomendación.
- Cada resultado debe apoyar una decisión concreta de compras o de recepción: quién la toma y cuándo.

## Lista para llegar al 100 %

La entrega debe quedar en «Cumple» en todos los puntos. Se revisó lo publicado en GitHub hasta el 7 de noviembre. «Por verificar» significa que debe comprobarse ejecutándolo. La sección Entrega se revisa en Moodle el 14 de noviembre.

| Sección | Requisito de la guía | Estado |
|---|---|---|
| Ficha | Integrantes con nombre completo | Cumple |
| Ficha | Empresa, tipo y a qué se dedica | Cumple |
| Ficha | Problema: qué decisión se toma mal hoy | Cumple |
| Ficha | Pregunta concreta, medible y con tiempo | Cumple |
| Ficha | KPI principal con fórmula y dos de apoyo | Cumple |
| Ficha | Fuentes de datos y formato | Cumple |
| Datos | Tabla principal con 1.000 filas o más | Falta |
| Datos | Tres clasificaciones o más | Falta |
| Datos | 12 meses de historia o más | Falta |
| Datos | Generación y reglas documentadas | Falta |
| Datos | Tres problemas de calidad o más a propósito | Falta |
| Datos | Sin datos de talleres, parcial o clase | Cumple |
| Cuaderno | Parte 0: Overview en inglés, seis oraciones o más | Falta |
| Cuaderno | Parte 2: carga, tamaño y muestra | Falta |
| Cuaderno | Parte 3: diagnóstico con cifras | Falta |
| Cuaderno | Parte 4: tres limpiezas con antes, después y motivo | Falta |
| Cuaderno | Parte 4: bitácora de cambios | Falta |
| Cuaderno | Parte 5: diccionario y grano | Falta |
| Cuaderno | Parte 5: carga en SQLite | Falta |
| Cuaderno | Parte 5: consulta con GROUP BY | Falta |
| Cuaderno | Parte 5: consulta con JOIN | Falta |
| Cuaderno | Parte 5: consulta con filtro de fechas | Falta |
| Cuaderno | Parte 5: interpretación de cada consulta | Falta |
| Cuaderno | Parte 6: KPI por mes | Falta |
| Cuaderno | Parte 6: promedio móvil | Falta |
| Cuaderno | Parte 6: comparación entre periodos | Falta |
| Cuaderno | Parte 7: fila de KPI y cuatro gráficos o más | Falta |
| Cuaderno | Parte 7: títulos que dicen el hallazgo | Falta |
| Cuaderno | Parte 8: cifras de control | Falta |
| Cuaderno | Parte 9: historia y recomendación (qué, quién, cuándo) | Falta |
| Cuaderno | Corre con «Reiniciar y ejecutar todo» | Falta |
| Entrega | FO-IV-159 en Excel, completo | Falta |
| Entrega | Cinco referencias o más, entre ellas Torres et al. y pandas | Falta |
| Entrega | Anexo 1: capturas y fotos de la sustentación | Falta |
| Entrega | Anexo 2: .ipynb ejecutado y datos | Falta |
| Entrega | Anexo 2: documento técnico en PDF, 10 páginas o menos | Falta |
| Entrega | Anexo 2: presentación de la sustentación | Falta |
| Entrega | Envío en c3-project de Moodle | Falta |

**Entrega:** sábado 14 de noviembre a las 23:59, solo en c3-project de Moodle (FO-IV-159 y ZIP de anexos). El avance en GitHub no reemplaza esa entrega.
