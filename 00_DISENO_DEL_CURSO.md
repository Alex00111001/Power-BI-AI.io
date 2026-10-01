# Power BI + IA para el trabajo profesional

Diseño final del curso. Duración exacta: 90 minutos. Idioma: español. Destinatarios: profesionales que ya crean consultas, modelos, medidas e informes en Power BI. El curso sustituye el enfoque previo y se construye alrededor de un único caso de ventas. No incluye introducción a Power BI.

## Resultado de aprendizaje

Al terminar, cada participante podrá encargar a una IA una transformación M y una medida DAX con contrato verificable, diagnosticar un resultado incorrecto, evaluar un cambio de modelo, contrastar una hipótesis comercial y producir documentación y un control repetible. Registrará el tiempo completo, incluida validación y retrabajo.

## Curso completo y distribución

| Minutos | Bloque | Dinámica y resultado |
|---|---|---|
| 00–08 | Método y medición | Contexto, contrato de salida, límites, línea base y prompt reutilizable |
| 08–24 | Power Query y M | Demo de 6 min, ejercicio de 6 min, revisión de 4 min. Limpieza con cuarentena y reconciliación |
| 24–43 | DAX con IA | Secuencia Power Query → Cerrar y aplicar → tablas cargadas → relaciones en vista Modelo → medidas. Comprobación del modelo real de 3 min, demo de 5 min, ejercicio de 7 min y validación de 4 min |
| 43–55 | Debugging y rendimiento | Diagnóstico de 3 min, práctica de 6 min, revisión de 3 min. Margen ponderado y filtros |
| 55–65 | Modelado | Revisión de 3 min, reto de 4 min, discusión de 3 min. Grano, cardinalidad y propagación |
| 65–74 | Análisis | Demo de 3 min, hipótesis de 3 min, contraste de 3 min. Hallazgos frente a causas |
| 74–84 | Documentación y automatización | Documentación de 4 min, control repetible de 4 min, revisión de 2 min |
| 84–90 | Cierre y transferencia | Reto final de 3 min, respuesta de 1 min, plan de aplicación y medición de 2 min |

90 min incluyen preguntas durante las revisiones. Preparación técnica y montaje del modelo ocurren antes de la sesión, pero antes del primer DAX cada alumno comprueba su archivo abierto frente a P01. Si falta una pieza, ese alumno sigue la recuperación paso a paso y no recibe medidas hasta demostrar que el modelo está listo; la demo común continúa con la copia preparada. Un solo instructor puede impartirlo. Participantes trabajan por parejas durante ejercicios. La ruta base requiere Power BI Desktop y un asistente de IA autorizado por su organización, sin depender de Copilot integrado. Si no hay acceso a IA o red, se usan las respuestas y soluciones locales suministradas.

## Caso común y contrato técnico

Distribuidora ficticia NorteSur. Datos completamente sintéticos. Ventas de enero a marzo de 2024 y 2025. Corte de comparación: 31/03/2025. Moneda EUR. Grano: una línea de venta identificada por IdLinea. Dos productos P01/P02 y dos regiones R01/R02. 24 líneas válidas, más un duplicado exacto, una fecha inválida, una cantidad nula y una clave de producto huérfana, total 28 filas de entrada. No se imputan errores en silencio. Resultado: 24 filas aceptadas, 3 rechazadas y 1 duplicado eliminado.

Tablas finales: Ventas, Productos, Regiones y Calendario (todos los días de 2024 y 2025). Relaciones uno a varios de dimensiones a hechos, filtro único y FechaVenta activa. Campos de Ventas: IdLinea, FechaVenta, IdProducto, IdRegion, Cantidad, PrecioUnitario, CosteUnitario, Descuento. Descuento es fracción entre 0 y 1. Ventas netas = cantidad × precio × (1 − descuento). Coste = cantidad × coste unitario. Margen % = (ventas netas − coste) / ventas netas. La tabla Calendario se marca como tabla de fechas.

Power Query conecta, limpia, transforma y prepara las tablas para la carga; puede combinar consultas, pero eso no crea relaciones del modelo. Tras **Cerrar y aplicar**, se comprueban tablas y columnas cargadas y se crean o revisan relaciones en vista Modelo o Administrar relaciones, incluidas las detectadas automáticamente. Calendario puede prepararse con M en Power Query o crearse con DAX en **Nueva tabla**; en ambas rutas su relación activa `Calendario[Fecha]` 1 a varios `Ventas[FechaVenta]` se comprueba después en el modelo. Solo entonces se crean medidas DAX con **Nueva medida**.

La muestra pequeña demuestra corrección y proceso. No permite demostrar mejoras de rendimiento a escala. Los tiempos tradicionales y con IA son hipótesis didácticas, nunca promesas ni resultados observados. El tiempo con IA incluye contexto, generación, validación y retrabajo. Para comparaciones reales: mismo alcance, mismos controles de calidad, tareas equivalentes y mediana de varias repeticiones, con orden alternado.

## Componentes que se producirán desde este diseño

1. Presentación editable de 32 diapositivas, con notas del instructor y referencias donde correspondan.
2. Guion del instructor con tiempos exactos, intervenciones, acciones, preguntas, respuestas, transiciones y plan de contingencia.
3. Cuaderno de prácticas con instrucciones, resultados esperados, criterios de aceptación, pistas y soluciones separadas.
4. Datos CSV, consultas M, medidas DAX correctas y versiones con errores deliberados.
5. Biblioteca de prompts con campos sustituibles, ejemplos completos, controles y formato de salida.
6. Comparativa de tiempos explícitamente ilustrativa y registro vacío para medir la sesión.
7. Automatización local de controles y documentación, más explicación de la ruta opcional PBIP/TMDL.
8. Cierre con evaluación breve, respuestas y plan de aplicación al trabajo real.

## Secuencia de la presentación

01 título; 02 resultados y agenda; 03 método de trabajo; 04 tiempos y calidad; 05 caso y contrato; 06 petición M; 07 tratamiento de errores; 08 ejercicio M; 09 reconciliación; 10 comprobación del modelo real; 11 medidas base; 12 inteligencia temporal; 13 ejercicio DAX; 14 pruebas de filtros; 15 respuestas DAX; 16 debugging por evidencia; 17 error de margen; 18 error de filtros; 19 rendimiento medible; 20 reto de modelo; 21 relaciones correctas; 22 revisión del modelo; 23 análisis del caso; 24 hallazgo e hipótesis; 25 contraste en Power BI; 26 documentación útil; 27 automatización local; 28 Copilot y opciones de equipo; 29 reto final; 30 respuesta y evaluación; 31 ahorro medido; 32 aplicación y cierre.

## Criterios de aceptación del curso

Todos los ejercicios comparten nombres de tablas y campos. Las cifras de soluciones salen del mismo conjunto de datos. Los errores tienen síntoma, causa, corrección y prueba de regresión. Cada bloque produce un resultado profesional reutilizable. Las licencias y funciones opcionales no impiden impartir la ruta base. Los materiales distinguen corrección del código, corrección del negocio y rendimiento. Los archivos sincronizados de sources permanecen como referencia de solo lectura.
