# Power BI + IA: trabajo profesional en 60 minutos

Curso práctico en español para personas que ya trabajan con Power BI. Un único caso sintético, NorteSur, muestra cómo obtener con IA una propuesta de M, DAX, análisis o documentación y llevarla a Power BI con una comprobación breve. No se enseña Power BI básico ni se dedican minutos a fallos inducidos.

## Resultado y método

El participante termina con una carga trazable, un modelo comprobado, medidas de ventas y margen con comparación YTD, un hallazgo comercial acotado, una ficha de medida y un control repetible. Cada prompt pide directamente el entregable final, sus supuestos y una lista corta de comprobaciones. Se registra el tiempo de contexto, generación y validación. La validación confirma la entrega; no constituye un ejercicio de búsqueda de errores.

| Minutos | Bloque | Resultado visible |
|---|---|---|
| 00–05 | Objetivo, contrato y cronómetro | P01 contextual y criterio de entrega |
| 05–17 | Power Query con IA | M listo para usar, Ventas, Cuarentena y ControlCarga |
| 17–25 | Carga y modelo | Cuatro tablas y tres relaciones comprobadas |
| 25–39 | DAX con IA | Medidas base, YTD y matriz de aceptación |
| 39–47 | Análisis del caso | Hallazgo, hipótesis y contraste |
| 47–55 | Documentación y automatización | Ficha de Margen % y control local |
| 55–60 | Cierre | Tiempo completo, límites y siguiente tarea |

El montaje técnico puede prepararse antes de clase. En directo se muestra la secuencia completa: **Power Query → Cerrar y aplicar → comprobar tablas y columnas → revisar relaciones en vista Modelo → Nueva medida**. Si el archivo de un participante no está listo, usa la copia preparada mientras recibe una corrección puntual. No se entrega DAX para pegar en un modelo sin comprobar.

## Contrato del caso

NorteSur es una distribuidora ficticia; todos los datos son sintéticos, en EUR. Ventas tiene una fila válida por IdLinea y los campos IdLinea, FechaVenta, IdProducto, IdRegion, Cantidad, PrecioUnitario, CosteUnitario y Descuento. Productos y Regiones tienen una fila por clave. Calendario cubre cada día de 2024 y 2025, con Fecha, Ano y MesNumero, y se marca como tabla de fechas. Las dimensiones filtran Ventas mediante relaciones 1 a varios, activas y de dirección única. La relación temporal es `Calendario[Fecha]` → `Ventas[FechaVenta]`.

Ventas netas suma `Cantidad * PrecioUnitario * (1 - Descuento)` por línea. Coste suma `Cantidad * CosteUnitario`; Margen es la diferencia; Margen % divide los importes agregados. La comparación YTD usa 31/03/2025 y el mismo tramo de 2024. Se conservan los filtros de producto y región. Los datos de entrada incluyen 28 filas; la salida de referencia tiene 24 aceptadas, tres apartadas con motivo y un duplicado exacto eliminado. Esos datos no se imputan o descartan sin trazabilidad.

Power Query conecta, limpia, transforma y prepara tablas, incluso Calendario con M; combinar consultas no crea relaciones. Tras **Cerrar y aplicar**, las relaciones se crean o comprueban en vista Modelo o Administrar relaciones. La detección automática de Power BI también se revisa. Calendario como tabla calculada DAX en **Nueva tabla** es una alternativa a M en el **Editor avanzado**. Las medidas DAX van a **Nueva medida**. Ambas rutas de Calendario requieren después configurar su relación.

## Entregables

Presentación editable de 24 diapositivas con notas; guion de 60 minutos; cuaderno con seis prácticas breves; prompts P01–P14 con versiones NorteSur listas para copiar (P01 conserva su plantilla); consultas M, medidas DAX, datos y solución; registro y comparativa ilustrativa de tiempo; control local y web autónoma. Los archivos de errores inducidos dejan de formar parte del curso. La muestra sirve para comprobar exactitud, no para demostrar rendimiento a escala. M y DAX deben probarse en Power BI Desktop antes de afirmar que funcionan allí.

## Criterio de éxito

El alumno puede copiar un prompt contextual, recibir una solución concreta y usarla en el lugar correcto. La carga reconcilia 28 = 24 + 3 + 1; la matriz muestra ventas YTD 2025 de 30.560 EUR frente a 28.740 EUR en 2024; el análisis distingue observación de causa; la documentación es reutilizable. Una comparación de ahorro exige medir el mismo alcance y nivel de calidad en ambos métodos. Las cifras ilustrativas no son promesas.
