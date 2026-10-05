# Power BI de 0 a la automatización con ChatGPT · solución profesional en 120 minutos orientativos

Curso en español para profesionales que ya usan Power BI. Un caso sintético, NorteSur, muestra cómo reducir trabajo repetitivo con IA sin perder calidad de datos, trazabilidad ni validación. El resultado final se diseña primero: fuentes → una preparación M con salidas de auditoría → modelo estrella → medidas DAX → resultados → cinco hallazgos con IA → informe visual → conclusión → documentación y automatización. Los 120 minutos son una orientación para una práctica completa; cada bloque avanza al comprobar su resultado, no al llegar a una hora fija.

## Decisión metodológica

En cada tarea se elige la opción más simple, rápida, reproducible y verificable. Interfaz para acciones únicas y visuales; M para importación y transformaciones repetitivas; DAX para medidas y contexto de filtro; IA para redactar, explicar, revisar y corregir código. **P01–P12 se envían de uno en uno**. Dentro de PXX se pueden agrupar operaciones relacionadas, pero el asistente valida su resultado, declara «PXX completado y validado», se detiene y pide el siguiente prompt. Nunca inicia PXX+1 por iniciativa propia. Una acción sencilla puede validarse con «listo»; una cifra, relación o conclusión necesita evidencia concreta.

| Minutos | Bloque | Entrega |
|---:|---|---|
| 00–08 | 01 · Contrato y herramienta | P01 y tres fuentes identificadas |
| 08–33 | 02 · Preparación y auditoría | Un script M, referencias, Ventas/Cuarentena/ControlCarga/Calendario |
| 33–45 | 03 · Modelo | Cuatro tablas y tres relaciones verificadas |
| 45–62 | 04 · DAX | P04: cuatro medidas base; P05: cuatro medidas YTD después de validar P04 |
| 62–72 | 05 · Hallazgos con IA | P06: cinco hallazgos y conclusión |
| 72–90 | 06 · Informe visual e hipótesis | P07: construcción guiada; P08: evidencia adicional |
| 90–115 | 07 · Documentación y automatización | Ficha y nuevo control Python generado desde prompt |
| 115–120 | 08 · Transferencia | Aceptación final y próxima tarea |

El flujo didáctico de cada prompt es **problema → PXX → solución dentro de PXX → ejecución → evidencia → validación → cierre → espera del siguiente prompt**. Los ocho bloques organizan temas y tiempo, pero no autorizan fusionar prompts. El guion y cuaderno desarrollan el recorrido sin clases de Power BI básico ni errores inducidos.

## Contrato NorteSur

Tres CSV sintéticos en EUR: `VentasOrigen.csv`, `Productos.csv` y `Regiones.csv`. Una línea válida por IdLinea. Ventas netas suma Cantidad × PrecioUnitario × (1 − Descuento) por línea; Coste suma Cantidad × CosteUnitario; Margen es diferencia; Margen % divide importes agregados. No se imputa Cantidad nula. Se rechazan fechas inválidas y claves desconocidas con motivo; solo se quitan duplicados exactos y se conserva su recuento. Calendario diario cubre 2024–2025. Relación activa 1:* y filtro único de Productos, Regiones y Calendario hacia Ventas. Comparación YTD al 31/03/2025 frente al mismo periodo de 2024. Filtros de producto y región se conservan.

Referencias independientes: entrada 28, aceptadas 24, rechazadas 3, duplicado exacto 1; 2024 ventas 28.740 y coste 18.360; 2025 ventas 30.560 y coste 20.520; 2025 R01 17.460 y R02 13.100. Son pruebas de corrección, no cifras para ajustar artificialmente la solución. La muestra pequeña no demuestra rendimiento a escala.

## Arquitectura y límites

`02_PreparacionNorteSur.m` devuelve un registro con Productos, Regiones, VentasOrigen, DuplicadosExactos, Ventas, Cuarentena, ControlCarga y Calendario. VentasOrigen conserva FilaOrigen y los ocho valores originales. DuplicadosExactos registra solo las apariciones posteriores; Cuarentena conserva originales, conversiones y todas las causas. ControlCarga calcula recuentos y reconciliación desde las tablas. Seis referencias de una línea extraen las salidas; solo Productos, Regiones, Ventas y Calendario se cargan al modelo. Power Query prepara tablas, **no crea relaciones**. Tras Cerrar y aplicar se comprueban columnas y relaciones en vista Modelo. Calendario DAX en Nueva tabla es una alternativa, no una medida. Las cuatro medidas de P04 y las cuatro de P05 se entregan y validan en grupos separados; Desktop las crea en Nueva medida. M, DAX y relaciones requieren comprobación en Power BI Desktop antes de afirmar que funcionan allí.

## Entregables

Presentación editable de 28 diapositivas con notas del instructor, guion, recorrido 01–08, cuaderno de seis ejercicios, prompts reutilizables, código M/DAX, datos y esperados, tabla de hallazgos y conclusión verificable, ejercicio Python generado por IA y web autónoma. El paquete contiene los CSV con nombres que coinciden con las consultas. No incluye PBIX montado ni un benchmark de ahorro laboral.


## 2026-10-05 · Simplificación didáctica autorizada

Una sola comprobación final por laboratorio, agrupada por bloque funcional. Reutiliza resultados y modelo ya confirmados: no vuelvas a pedirlos si no cambiaron. Acepta valores con filtros o una lista concreta; solicita captura solo cuando sea imprescindible para aclarar el modelo real o diagnosticar una discrepancia. Mantén duplicados, claves desconocidas, fechas inválidas, nulos relevantes, Cuarentena y ControlCarga. Mantén las protecciones DAX y explica brevemente DIVIDE, IF e ISBLANK; son controles técnicos internos, no ejercicios adicionales. No pidas contextos vacíos, filtros artificiales ni pruebas obligatorias de BLANK(). Solo una discrepancia observada abre diagnóstico adicional.

Secuencia intacta: P01 contrato, P02 preparación, P03 modelo, P04 medidas base, P05 inteligencia temporal y P06–P12 posteriores. P04 entrega las cuatro bases juntas; P05 las cuatro temporales juntas. Validaciones visibles: totales, regiones, productos, periodos, YTD y variaciones. Arquitectura, lógica de negocio y código M/DAX se conservan. Después de cada cambio, regenerar materiales/web/ZIP, verificar y actualizar GitHub Pages; no dar por publicada una versión sin comprobar despliegue.


## 2026-10-05 · P08 sin verificación de hipótesis

Por petición del usuario, P08 solo plantea dos hipótesis alternativas, evidencia externa sugerida y una pregunta para negocio. No exige verificarlas, conseguir registros, contactar a un responsable ni solicitar confirmación adicional. Completa en una respuesta y pide P09. Cierre: «P08 completado: hipótesis planteadas, no verificadas. Envíame P09 para continuar». Esto es una excepción a las pausas generales de validación; no se presentan hipótesis como causas demostradas. Publicar cada cambio en GitHub sigue siendo obligatorio.
