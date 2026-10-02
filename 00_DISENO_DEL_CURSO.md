# Power BI + IA: trabajo profesional en 60 minutos

Curso práctico en español para personas que ya trabajan con Power BI. Un único caso sintético, NorteSur, se recorre **paso a paso desde los archivos hasta la solución**. La ruta principal usa primero la interfaz de Power BI; M aparece para una auditoría reproducible y las salidas derivadas. Cada etapa G01–G20 indica objetivo, motivo, ubicación, clics, resultado, comprobación y papel de la IA. No se enseña Power BI básico ni se dedican minutos a fallos inducidos.

## Resultado y método

El participante termina con una carga trazable, un modelo comprobado, medidas de ventas y margen con comparación YTD, un hallazgo comercial acotado, una ficha de medida y un control repetible. Cada prompt pide directamente el entregable final, sus supuestos y una lista corta de comprobaciones. Se registra el tiempo de contexto, generación y validación. La validación confirma la entrega; no constituye un ejercicio de búsqueda de errores.

| Minutos | Bloque | Resultado visible |
|---|---|---|
| 00–10 | Fuentes e importación GUI | CSV importados, VentasOrigen conservada y tipos controlados |
| 10–22 | Auditoría y salidas con IA/M | VentasAuditadas, Ventas, Cuarentena y ControlCarga reconciliadas |
| 22–32 | Calendario y modelo | Cerrar y aplicar, cuatro tablas y tres relaciones comprobadas |
| 32–48 | DAX, visuales y validación | Medidas base, YTD y matriz contrastada |
| 48–57 | Análisis, documentación y control | Hallazgo, ficha y control local |
| 57–60 | Cierre | Tiempo completo y próxima tarea |

El montaje técnico puede prepararse antes de clase. En directo se muestra la secuencia completa: **fuentes → importación y normalización GUI → auditoría M derivada del origen → conciliación → Calendario → Cerrar y aplicar → comprobar tablas y columnas → revisar relaciones en vista Modelo → Nueva medida → visual y validación**. El curso tiene un punto de control tras cada G: instructor o alumno confirma el resultado antes de continuar. Si un participante se retrasa, sigue la demostración con la copia preparada y retoma su archivo en el mismo G. No se entrega DAX para pegar en un modelo sin comprobar.

## Contrato del caso

NorteSur es una distribuidora ficticia; todos los datos son sintéticos, en EUR. Ventas tiene una fila válida por IdLinea y los campos IdLinea, FechaVenta, IdProducto, IdRegion, Cantidad, PrecioUnitario, CosteUnitario y Descuento. Productos y Regiones tienen una fila por clave. Calendario cubre cada día de 2024 y 2025, con Fecha, Ano y MesNumero, y se marca como tabla de fechas. Las dimensiones filtran Ventas mediante relaciones 1 a varios, activas y de dirección única. La relación temporal es `Calendario[Fecha]` → `Ventas[FechaVenta]`.

Ventas netas suma `Cantidad * PrecioUnitario * (1 - Descuento)` por línea. Coste suma `Cantidad * CosteUnitario`; Margen es la diferencia; Margen % divide los importes agregados. La comparación YTD usa 31/03/2025 y el mismo tramo de 2024. Se conservan los filtros de producto y región. Los datos de entrada incluyen 28 filas; la salida de referencia tiene 24 aceptadas, tres apartadas con motivo y un duplicado exacto eliminado. Esos datos no se imputan o descartan sin trazabilidad.

Power Query conecta, limpia, transforma y prepara tablas, incluso Calendario con M; combinar consultas no crea relaciones. Tras **Cerrar y aplicar**, las relaciones se crean o comprueban en vista Modelo o Administrar relaciones. La detección automática de Power BI también se revisa. Calendario como tabla calculada DAX en **Nueva tabla** es una alternativa a M en el **Editor avanzado**. Las medidas DAX van a **Nueva medida**. Ambas rutas de Calendario requieren después configurar su relación.

## Entregables

Presentación editable de 24 diapositivas con notas; guion de 60 minutos; recorrido G01–G20 y cuaderno con seis entregables; prompts P01–P14 con versiones NorteSur listas para copiar (P01 conserva su plantilla); consultas M, medidas DAX, datos y solución; registro y comparativa ilustrativa de tiempo; control local y web autónoma. Los archivos de errores inducidos dejan de formar parte del curso. La muestra sirve para comprobar exactitud, no para demostrar rendimiento a escala. M y DAX deben probarse en Power BI Desktop antes de afirmar que funcionan allí.

## Criterio de éxito

El alumno puede copiar un prompt contextual, recibir una solución concreta y usarla en el lugar correcto. La carga reconcilia 28 = 24 + 3 + 1; la matriz muestra ventas YTD 2025 de 30.560 EUR frente a 28.740 EUR en 2024; el análisis distingue observación de causa; la documentación es reutilizable. Una comparación de ahorro exige medir el mismo alcance y nivel de calidad en ambos métodos. Las cifras ilustrativas no son promesas.
