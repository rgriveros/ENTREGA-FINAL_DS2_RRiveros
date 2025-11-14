# Predicción de alcanzamiento de etapa avanzada en proyectos mineros argentinos

## Entrega final — Proyecto DS2

## Autor: Gabriel Riveros Lobos

### Rol: Process improvement technician · Data analyst (freelance)

### Repositorio / Notebook: EntregaFinal_DS2_RRiveros.ipynb

### Artefactos entregados: 
data/artifacts/{preproc_fitted.joblib, df_transformed.parquet, split_indices.joblib, model_final.joblib, final_metrics.csv, shap_summary.png, shap_feature_table.csv, best_params_lightgbm.json}

### Métrica primaria: PR AUC (Average Precision)

### Modelo final seleccionado: LightGBM (reentrenado sobre train+val)

Fecha de entrega: 13/11/2025


Resumen de la entrega: 
Notebook reproducible que descarga y versiona datos, aplica limpieza no destructiva y aplicada, construye pipeline de preprocesado auditable, crea splits reproducibles, compara modelos baseline y avanzados, selecciona y persiste LightGBM final, y entrega análisis de interpretabilidad con SHAP.

## Abstracto
Este trabajo desarrolla y entrega un flujo reproducible para predecir la probabilidad de que un proyecto minero público en Argentina alcance una etapa avanzada. Partiendo de datos públicos obtenidos por CKAN, se aplicó una limpieza no destructiva (generación de columnas *_clean), control de calidad y versionado de artefactos. La etapa de preprocesado construyó un pipeline auditable (ColumnTransformer + Pipeline) que prioriza columnas limpias y documenta transformaciones; las features resultantes se persistieron en formato parquet para modelado.

Para evaluación se definió PR AUC (Average Precision) como métrica primaria, dada la naturaleza desbalanceada del problema y la necesidad operacional de priorizar un top-k de proyectos. Se compararon modelos baseline y modelos avanzados; LightGBM superó los baselines en PR AUC y métricas complementarias (AUC ROC, Precision@k, Brier score). El modelo final fue reentrenado sobre train+val con semilla fija y persistido junto al pipeline de preprocesado. Se incluyeron comprobaciones de calibración y una propuesta de umbrales operativos (Precision@k) para facilitar la adopción práctica.

La interpretación se realizó con SHAP: se exportó una tabla de importancias y dirección de efecto por feature, junto con visualizaciones summary y ejemplos locales para casos representativos. Se documentan limitaciones importantes: tamaño limitado de la muestra, clases con baja frecuencia que requieren decisiones sobre agrupamiento o muestreo, y dependencia de la calidad de variables originales (posibles columnas constantes o mal codificadas). Se incluyen recomendaciones inmediatas para producción: persistir preproc + modelo en un endpoint con validación de inputs, monitorear deriva y métricas operativas (Precision@k, distribución de probabilidades, Brier score), y priorizar mejora de calidad y trazabilidad de las variables críticas.

El repositorio entregado contiene instrucciones paso a paso para replicar el experimento en una sesión limpia, los artefactos necesarios para auditoría y despliegue, y un README inicial que resume decisiones clave y cómo reproducir la evaluación y generación de reportes.
