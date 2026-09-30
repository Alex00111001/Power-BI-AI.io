# Fuentes oficiales y límites verificados

Consulta: **30-09-2026**. Fuentes primarias de Microsoft Learn. Son referencias para el curso; los requisitos de producto deben volver a comprobarse antes de impartirlo. Las estimaciones de ahorro de tiempo del curso son hipótesis didácticas, no resultados publicados por Microsoft ni promesas de rendimiento.

## 1. Copilot para Power BI: requisitos y alcance

[Copilot for Power BI overview](https://learn.microsoft.com/en-us/power-bi/create-reports/copilot-introduction)

- Capacidad de pago Fabric **F2 o superior** o Power BI Premium **P1 o superior**; una licencia Pro o PPU por sí sola no basta. Las capacidades de prueba y SKU gratuitos no son compatibles.
- Se requieren región compatible y configuración administrativa que permita Copilot; las nubes soberanas no están admitidas.
- Algunas experiencias son generales y otras siguen en versión preliminar. No presentar todas como equivalentes.
- En la experiencia independiente y en apps, la documentación indica que el uso multilingüe aún no está oficialmente admitido; prever una alternativa para un curso en español.
- La disponibilidad puede tardar hasta 24 horas tras comprar o ampliar capacidad. La adquisición de capacidad no debe ser un paso de la sesión.
- La capacidad de Copilot y las operaciones posteriores, como consultas y actualizaciones, tienen consumo: no prometer uso ilimitado.

## 2. Habilitación y permisos

[Enable Fabric Copilot for Power BI](https://learn.microsoft.com/en-us/power-bi/create-reports/copilot-enable-power-bi)

- Sin acceso a una Fabric Copilot capacity, Desktop necesita un área de trabajo apta con rol de administrador, miembro o colaborador, capacidad F2+/P1+ y Copilot habilitado.
- Los administradores pueden limitar el acceso. La experiencia independiente exige habilitación a nivel de inquilino; una habilitación delegada solo a la capacidad no basta para esa experiencia.
- Las configuraciones de procesamiento entre regiones dependen de la geografía y las administra la organización. No pedir a los alumnos que las cambien durante el curso.
- Private Link y entornos de red cerrada figuran como no compatibles.
- Para que el curso sea reproducible, el recorrido principal puede usar una IA aprobada por la organización con esquema y datos sintéticos; Copilot integrado es una variante cuando el entorno esté preparado.

## 3. DAX Query View: ejecutar antes de incorporar

[DAX query view](https://learn.microsoft.com/en-us/power-bi/transform-model/dax-query-view)

- Permite ejecutar consultas contra el modelo y recibir consultas de los visuales desde Performance Analyzer.
- Una consulta de prueba puede definir medidas locales; ejecutar una consulta no equivale a incorporar automáticamente esas medidas al modelo.
- La vista web requiere permisos de escritura y sus consultas se descartan al cerrar. Desktop guarda consultas con el modelo.
- Límites de resultados documentados: 15 MB y un millón de valores por consulta; web añade un máximo de 99.999 filas. No utilizar esta vista como un mecanismo de exportación masiva.
- La cuadrícula no refleja todos los formatos del modelo. Validar números y contextos, no solo su apariencia.

## 4. Performance Analyzer: evidencia, no intuición

[Use Performance Analyzer to examine report performance](https://learn.microsoft.com/en-us/power-bi/create-reports/performance-analyzer)

- Mide duración por visual y separa consulta DAX, consulta directa, representación del visual y otras tareas.
- Permite copiar consultas y exportar el registro a JSON. Desktop ofrece ejecutarlas en DAX Query View; en el servicio se puede copiar y abrir la vista por separado.
- Las duraciones incluyen esperas por otras operaciones. «Other» no demuestra por sí solo que una fórmula DAX sea lenta.
- Recomendación didáctica: comparar la misma interacción, visual, filtros y datos; repetir mediciones, distinguir carga inicial de ejecuciones posteriores y documentar las condiciones. Es un protocolo del curso, no un benchmark de Microsoft.
- Optimizar un código sin medir el resultado no demuestra mejora. Comprobar primero equivalencia funcional.

## 5. Query folding y el límite de una demo con CSV

[Overview of query evaluation and query folding in Power Query](https://learn.microsoft.com/en-us/power-query/query-folding-basics)

- El plegado traduce transformaciones compatibles para que las ejecute el origen. Puede ser completo, parcial o inexistente.
- Depende del conector, el origen y las transformaciones. SQL Server y OData suelen ofrecer capacidad para plegar; **CSV y Excel no tienen motor de consulta al que delegar esas transformaciones**.
- Una práctica con CSV sirve para limpiar y validar M, pero no demuestra query folding ni ahorro de procesamiento en servidor.
- No inferir plegado por tener menos pasos o por reordenarlos. Validar en un origen compatible; si la sesión solo usa archivos, explicarlo como extensión y evitar atribuirle una aceleración observada.

## 6. Modelo estrella y granularidad

[Understand star schema and the importance for Power BI](https://learn.microsoft.com/en-us/power-bi/guidance/star-schema)

- Las dimensiones sirven para filtrar y agrupar; los hechos, para resumir. Mantener una granularidad consistente en los hechos.
- Una dimensión necesita una clave única para situarse en el lado «uno». Duplicados o claves incompatibles no se corrigen de forma fiable solo con una medida DAX.
- La IA puede revisar un esquema y plantear alternativas; la decisión requiere significado de negocio, cardinalidad y datos reales de claves.
- La guía admite excepciones razonadas. No convertir el modelo estrella en un mandato que ignore requisitos del caso.

## 7. Relaciones bidireccionales

[Bi-directional relationship guidance](https://learn.microsoft.com/en-us/power-bi/guidance/relationships-bidirectional-filtering)

- Microsoft recomienda minimizar las relaciones bidireccionales: pueden perjudicar rendimiento y producir experiencias confusas.
- Hay escenarios legítimos, pero no se deben activar como reparación genérica de un resultado inesperado.
- Para debugging, pedir a la IA que describa la propagación de filtros, detecte rutas y pruebe una hipótesis concreta. La propuesta debe contrastarse con subtotales y filtros previstos.

## 8. PBIP: cambios de texto revisables

[Power BI Desktop projects](https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview)

- PBIP guarda definiciones del informe y del modelo como archivos de texto; permite revisión de diferencias, reutilización y control de versiones.
- La documentación actual indica que Desktop detecta cambios externos y solicita aplicarlos. No enseñar como requisito universal que siempre haya que reiniciar Desktop.
- La conversión PBIX ↔ PBIP se realiza mediante Guardar como en Desktop; no existe conversión programática admitida en esta guía.
- Las etiquetas de confidencialidad no están admitidas con PBIP. Usar rutas cortas; el límite habitual de Windows puede afectar proyectos con carpetas y nombres largos.
- Las ediciones externas se deben guardar como UTF-8 sin BOM. No incluir credenciales ni archivos de caché en materiales o repositorios.
- Automatización adecuada al curso: proponer descripciones o formato, revisar diferencias, aplicar en una copia y volver a ejecutar pruebas.

## 9. TMDL: automatización de metadatos con revisión

[Use Tabular Model Definition Language (TMDL) view in Power BI](https://learn.microsoft.com/en-us/power-bi/transform-model/desktop-tmdl-view)

- TMDL View en Desktop figura como disponibilidad general; la versión web está en preliminar.
- Permite generar scripts de objetos, previsualizar diferencias y aplicar cambios. Es adecuado para mostrar modificaciones repetitivas de descripciones o formatos.
- Modifica metadatos; no actualiza automáticamente los datos. Cambiar M o una columna calculada puede requerir actualización manual.
- Renombrar un campo puede romper visuales. Una propuesta de IA no debe aplicarse sin revisar el alcance de los objetos modificados.
- Los scripts web no persisten al cerrar; en Desktop se guardan con el archivo y, en PBIP, como archivos .tmdl en TMDLScripts.
- El curso debe partir de un fragmento exportado por Desktop y conservar el resto de propiedades; no inventar estructuras ni sustituir objetos completos a ciegas.

## 10. Copilot, DAX y corrección semántica

[Use Copilot with semantic models in Power BI](https://learn.microsoft.com/en-us/power-bi/create-reports/copilot-semantic-models)

- Copilot puede generar consultas DAX, explicar código y proponer medidas dentro de las consultas. El resultado se debe validar antes de incorporarlo al modelo.
- Una expresión que funciona en la consulta inicial puede producir un valor incorrecto en otro contexto de filtro. El comprobador sintáctico no sustituye las pruebas de negocio.
- En conexión en vivo, Copilot no ve expresiones de medidas ni objetos ocultos o privados del mismo modo que en un modelo local.
- Descripciones claras y contexto del modelo mejoran la información disponible. Evitar asumir que la IA conoce reglas no documentadas.
- Pedir consultas con casos esperados, filtros y subtotales. La evaluación debe cubrir totales, valores vacíos, división por cero y comparación temporal según las reglas del caso.

## Uso en la formación

La ruta principal debe funcionar con Power BI Desktop, los archivos sintéticos entregados y una herramienta de IA autorizada. Preparar respuestas guardadas como alternativa si hay latencia o falta de acceso. La extensión Copilot se demuestra únicamente cuando se hayan validado capacidad, región, permisos y configuración. Las fuentes respaldan comportamientos del producto; no respaldan cifras concretas de ahorro laboral.
