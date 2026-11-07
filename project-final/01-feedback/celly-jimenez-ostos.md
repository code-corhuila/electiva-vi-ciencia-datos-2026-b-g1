# Retroalimentación · Revisión del 7 de noviembre

**Proyecto:** Piscícola Aguas Claras del Yaguará S.A.S. · Factor de conversión alimenticia (empresa ficticia)
**Estudiantes:** Juan David Celly y Ana Sofía Jiménez Ostos
**Revisión:** sábado 7 de noviembre de 2026 · Docente Jesús Ariel González Bonilla
**Avance revisado:** fork `JDCelly`, `14-week/` (cuaderno `Proyecto-Aula-Piscicola-Aguas-Claras.ipynb` e informe en PDF)

Es un avance muy completo: el cuaderno ya tiene las partes 0 a 9, con limpieza documentada, SQLite, análisis mensual, tablero, cifras de control y una recomendación con responsables y fechas. También destaca que reconozcan que el proveedor no marca una diferencia clara en lugar de forzar un hallazgo.

**La prioridad para el sábado 14 de noviembre es dejarlo como trabajo propio y terminado:** completar los datos pendientes, comprobar las cifras y sostener la recomendación con evidencia.

## 1. Pendientes de forma

- **Integrantes:** el cuaderno y parte del informe conservan «[Nombre completo 1]» y «[Nombre completo 2]». El informe también tiene pendiente «[declarar herramienta y uso, si aplica]».
- **Textos de plantilla:** eliminen las indicaciones que no hacen parte del informe, como «cámbiela: así sus datos serán distintos…» y «Si declara apoyo de IA…».
- **Programa:** el informe dice Ingeniería Mecatrónica, mientras la guía indica Ingeniería Industrial. Confirmen cuál corresponde.
- **FO-IV-159:** se entrega en el Excel oficial, no en PDF. El documento técnico es aparte y tiene un máximo de 10 páginas; el PDF actual tiene 21.

## 2. Ajustes técnicos

- **Cifras de control:** la columna «¿coincide?» usa una tolerancia de 0,06. Con ese margen, un FCA de 1,76 también aparecería como «OK» frente a 1,704. Use una tolerancia acorde a cada cifra. Además, los valores de referencia están escritos a mano: deben tomarse del informe final.
- **Consulta de tablas:** la verificación de SQLite muestra 0 columnas en las cuatro tablas. El conteo no está funcionando; corríjalo o retírelo.
- **Dos variaciones del módulo C:** la consulta 4 da +0,082 y la Parte 6, +0,085, porque una agrupa por fecha de cosecha y la otra por semana. Escojan una como oficial y expliquen la diferencia.
- **Noviembre de 2024:** el FCA de 2,02 es el arranque, con pocas jaulas, y aun así entra al promedio móvil. Evalúen excluirlo.
- **Comparación entre periodos:** con 14 lotes frente a 44, conviene mostrar el resultado con esa reserva también en el tablero, no solo en el texto.

## 3. La recomendación: lo más importante

**Reducir la ración en meses de lluvia.** El análisis muestra que el FCA sube en lluvias (1,77 frente a 1,67), pero no prueba que reducir la ración lo baje. Podría frenar el crecimiento y retrasar la cosecha. Es mejor proponer una prueba en algunas jaulas, con grupo de comparación, antes de aplicarla a toda la granja.

**Módulo C.** El sobrecosto de 8.620 kg de alimento, cerca de COP 36 millones en 24 meses, es un dato útil para la gerencia. Defina de dónde sale cada meta, como el FCA menor o igual a 1,75: si es una meta supuesta, indíquelo.

## 4. Sustentación

Los patrones del módulo C y las lluvias se programaron en el generador. Preséntelo así: el cuaderno recupera un patrón diseñado, no descubre una causa real. Ambos integrantes deben poder explicar cualquier celda y cualquier cifra, incluida la lógica del generador y el cálculo de biomasa ganada por semana.

## Antes de entregar

- Ejecutar «Reiniciar y ejecutar todo» y revisar que el cuaderno y el informe den las mismas cifras.
- Asegurar que los aportes de ambos integrantes queden en evidencia.
- Revisar que ningún archivo público contenga datos personales.

## Lista para llegar al 100 %

La entrega debe quedar en «Cumple» en todos los puntos. Se revisó lo publicado en GitHub hasta el 7 de noviembre. «Por verificar» significa que debe comprobarse ejecutándolo. La sección Entrega se revisa en Moodle el 14 de noviembre.

| Sección | Requisito de la guía | Estado |
|---|---|---|
| Ficha | Integrantes con nombre completo | Parcial |
| Ficha | Empresa, tipo y a qué se dedica | Cumple |
| Ficha | Problema: qué decisión se toma mal hoy | Cumple |
| Ficha | Pregunta concreta, medible y con tiempo | Cumple |
| Ficha | KPI principal con fórmula y dos de apoyo | Cumple |
| Ficha | Fuentes de datos y formato | Cumple |
| Datos | Tabla principal con 1.000 filas o más | Cumple |
| Datos | Tres clasificaciones o más | Cumple |
| Datos | 12 meses de historia o más | Cumple |
| Datos | Generación y reglas documentadas | Cumple |
| Datos | Tres problemas de calidad o más a propósito | Cumple |
| Datos | Sin datos de talleres, parcial o clase | Cumple |
| Cuaderno | Parte 0: Overview en inglés, seis oraciones o más | Cumple |
| Cuaderno | Parte 2: carga, tamaño y muestra | Cumple |
| Cuaderno | Parte 3: diagnóstico con cifras | Cumple |
| Cuaderno | Parte 4: tres limpiezas con antes, después y motivo | Cumple |
| Cuaderno | Parte 4: bitácora de cambios | Cumple |
| Cuaderno | Parte 5: diccionario y grano | Cumple |
| Cuaderno | Parte 5: carga en SQLite | Cumple |
| Cuaderno | Parte 5: consulta con GROUP BY | Cumple |
| Cuaderno | Parte 5: consulta con JOIN | Cumple |
| Cuaderno | Parte 5: consulta con filtro de fechas | Cumple |
| Cuaderno | Parte 5: interpretación de cada consulta | Cumple |
| Cuaderno | Parte 6: KPI por mes | Cumple |
| Cuaderno | Parte 6: promedio móvil | Cumple |
| Cuaderno | Parte 6: comparación entre periodos | Cumple |
| Cuaderno | Parte 7: fila de KPI y cuatro gráficos o más | Cumple |
| Cuaderno | Parte 7: títulos que dicen el hallazgo | Cumple |
| Cuaderno | Parte 8: cifras de control | Parcial |
| Cuaderno | Parte 9: historia y recomendación (qué, quién, cuándo) | Parcial |
| Cuaderno | Corre con «Reiniciar y ejecutar todo» | Por verificar |
| Entrega | FO-IV-159 en Excel, completo | Parcial |
| Entrega | Cinco referencias o más, entre ellas Torres et al. y pandas | Parcial |
| Entrega | Anexo 1: capturas y fotos de la sustentación | Falta |
| Entrega | Anexo 2: .ipynb ejecutado y datos | Falta |
| Entrega | Anexo 2: documento técnico en PDF, 10 páginas o menos | Falta |
| Entrega | Anexo 2: presentación de la sustentación | Falta |
| Entrega | Envío en c3-project de Moodle | Falta |

**Entrega:** sábado 14 de noviembre a las 23:59, solo en c3-project de Moodle (FO-IV-159 y ZIP de anexos), un envío por pareja. El avance en GitHub no reemplaza esa entrega.
