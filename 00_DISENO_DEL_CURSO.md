# Power BI + IA · solución profesional en 110 minutos orientativos

Curso en español para profesionales que ya usan Power BI. Un caso sintético, NorteSur, muestra cómo reducir trabajo repetitivo con IA sin perder calidad de datos, trazabilidad ni validación. El resultado final se diseña primero: fuentes → una preparación M con salidas de auditoría → modelo estrella → medidas DAX → matriz → hallazgo → documentación y medición. Los 110 minutos son una orientación para una práctica completa; cada bloque avanza al comprobar su resultado, no al llegar a una hora fija.

## Decisión metodológica

En cada tarea se elige la opción más simple, rápida, reproducible y verificable. Interfaz para acciones únicas y visuales; M para importación y transformaciones repetitivas; DAX para medidas y contexto de filtro; IA para redactar, explicar, revisar y corregir código. Se agrupan las operaciones de una misma tarea en un bloque coherente. La comprobación se hace al final de ese bloque y antes de cualquier cálculo dependiente. Una acción sencilla puede avanzar con «listo»; una cifra, relación o conclusión necesita evidencia concreta.

| Minutos | Bloque | Entrega |
|---:|---|---|
| 00–08 | 01 · Contrato y herramienta | P01 y tres fuentes identificadas |
| 08–33 | 02 · Preparación y auditoría | Un script M, referencias, Ventas/Cuarentena/ControlCarga/Calendario |
| 33–45 | 03 · Modelo | Cuatro tablas y tres relaciones verificadas |
| 45–62 | 04 · DAX | Ocho medidas entregadas juntas, creadas en orden y validadas en conjunto |
| 62–72 | 05 · Informe | Matriz y filtros aceptados |
| 72–80 | 06 · Hallazgo | Variación y dos hipótesis acotadas |
| 80–105 | 07 · Documentación y automatización | Ficha y nuevo control Python generado desde prompt |
| 105–110 | 08 · Transferencia | Registro del tiempo completo y próxima tarea |

El flujo didáctico de cada ejercicio es **problema → prompt → solución completa → lugar de aplicación → explicación breve → ejecución → validación**. El guion y cuaderno desarrollan los ocho bloques sin clases de Power BI básico ni errores inducidos.

## Contrato NorteSur

Tres CSV sintéticos en EUR: `VentasOrigen.csv`, `Productos.csv` y `Regiones.csv`. Una línea válida por IdLinea. Ventas netas suma Cantidad × PrecioUnitario × (1 − Descuento) por línea; Coste suma Cantidad × CosteUnitario; Margen es diferencia; Margen % divide importes agregados. No se imputa Cantidad nula. Se rechazan fechas inválidas y claves desconocidas con motivo; solo se quitan duplicados exactos y se conserva su recuento. Calendario diario cubre 2024–2025. Relación activa 1:* y filtro único de Productos, Regiones y Calendario hacia Ventas. Comparación YTD al 31/03/2025 frente al mismo periodo de 2024. Filtros de producto y región se conservan.

Referencias independientes: entrada 28, aceptadas 24, rechazadas 3, duplicado exacto 1; 2024 ventas 28.740 y coste 18.360; 2025 ventas 30.560 y coste 20.520; 2025 R01 17.460 y R02 13.100. Son pruebas de corrección, no cifras para ajustar artificialmente la solución. La muestra pequeña no demuestra rendimiento a escala.

## Arquitectura y límites

`02_PreparacionNorteSur.m` devuelve un registro con Productos, Regiones, VentasOrigen, VentasAuditadas, Ventas, Cuarentena, ControlCarga y Calendario. Seis referencias de una línea extraen las salidas; solo Productos, Regiones, Ventas y Calendario se cargan al modelo. Power Query prepara tablas, **no crea relaciones**. Tras Cerrar y aplicar se comprueban columnas y relaciones en vista Modelo. Calendario DAX en Nueva tabla es una alternativa, no una medida. Ocho medidas DAX se entregan como un conjunto con dependencias; Desktop las crea en Nueva medida. M, DAX y relaciones requieren comprobación en Power BI Desktop antes de afirmar que funcionan allí.

## Entregables

Presentación editable de 26 diapositivas con notas del instructor, guion, recorrido 01–08, cuaderno de seis ejercicios, prompts reutilizables, código M/DAX, datos y esperados, registro/comparativa de tiempos, ejercicio Python generado por IA y web autónoma. El paquete contiene los CSV con nombres que coinciden con las consultas. No incluye PBIX montado ni un benchmark de ahorro laboral.
