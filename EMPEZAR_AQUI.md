# Power BI de 0 a la automatización con ChatGPT · 120 minutos orientativos

Curso práctico para profesionales que ya trabajan con Power BI. Abre `indice.html` y sigue los bloques **01–08** con los prompts **P01–P12 de uno en uno**. Cada prompt se ejecuta, se valida y se cierra antes de que el alumno envíe el siguiente. Se agrupan operaciones compatibles dentro de un mismo prompt, sin fusionar prompts distintos. «Listo» sirve para acciones sencillas; cifras, columnas y relaciones requieren evidencia real. Los 120 minutos son orientativos. La página incluye presentación editable, seis entregables, prompts y descargas; funciona sin archivos externos, salvo enlaces a Microsoft Learn.

| Material | Uso |
|---|---|
| `presentacion/Power_BI_de_0_a_la_automatizacion_con_ChatGPT_actualizado.pptx` | Presentación editable de 28 diapositivas con notas del instructor |
| `materiales/01_Guion_del_instructor.md` | Secuencia, tiempos orientativos y mapa de las diapositivas |
| `materiales/02_Cuaderno_del_participante.md` | Prácticas y resultados esperados |
| `materiales/07_Recorrido_guiado.md` | Ocho bloques desde contrato hasta solución |
| `materiales/03_Prompts_reutilizables.md` | P01 plantilla y 12 prompts para NorteSur |
| `materiales/04_Solucionario.md` | Código y contrastes independientes |
| `materiales/05_Hallazgos_con_IA.md` | Cinco hallazgos priorizados y sus medidas/filtros |
| `materiales/06_Conclusion_verificable.md` | Conclusión breve y límites de la evidencia |
| `materiales/08_Informe_visual_de_hallazgos.md` | P07: layout, KPIs, visuales y textos ejecutivos |
| `laboratorio/README_MONTAJE.md` | Preparación de Desktop |

## Recorrido

00–08 contrato y herramienta; 08–33 bloque M y validación; 33–45 modelo; 45–62 DAX; 62–72 hallazgos con IA; 72–90 informe visual e hipótesis; 90–115 documentación/control; 115–120 cierre y transferencia.

Antes de DAX, pega `02_PreparacionNorteSur.m` en el **Editor avanzado** de Power Query, crea las salidas de `03_Salidas.md`, valida ControlCarga/Cuarentena/Calendario, pulsa **Cerrar y aplicar** y comprueba cuatro tablas y tres relaciones. Calendario DAX alternativo va en **Nueva tabla**; cada definición DAX se pega en **Nueva medida**. P10 hace que la IA genere una automatización Python nueva para el alumno; no se ejecuta ni adapta la referencia del instructor. Python contrasta archivos y referencias, pero no ejecuta M, DAX ni relaciones. El alumno debe comparar la evidencia con Power BI Desktop.


Cada laboratorio termina con una sola comprobación útil del resultado. Reutiliza modelo y resultados confirmados. Las protecciones DAX y controles técnicos permanecen internos: no se exigen filtros artificiales, pruebas de BLANK() ni capturas rutinarias. P04 agrupa ventas, coste, margen y margen %; P05 agrupa YTD, año anterior y variaciones.


**P09 opcional.** La ficha de medida no es requisito para avanzar ni cerrar el curso. Tras P08 se puede elegir P09 o enviar P10 directamente. En P12, omitir P09 no constituye un pendiente. El tiempo de esa actividad se puede omitir.
