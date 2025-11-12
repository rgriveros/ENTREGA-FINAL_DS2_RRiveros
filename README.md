# Entrega Final DATA SCIENCE 2 - PROYECTOS MINEROS ARGENTINOS
## Autor: Rodolfo Gabriel Riveros Lobos
### Fecha: 2025-11-13

### Colab: https://colab.research.google.com/drive/1b6zigKZPdA5ECoi4eVS-X-Eey8C6Idxo?usp=sharing

## Objetivo:
Construir un modelo de clasificación para predecir si un proyecto alcanzará una etapa avanzada (sí/no), facilitando priorización de inversión y asignación de recursos operativos. Pregunta de negocio: ¿Qué proyectos de la cartera tienen alta probabilidad de alcanzar una etapa avanzada y, por tanto, merecen priorización de inversión?

## Audiencia beneficiada:
Gerencias de proyectos, analistas de cartera e inversores que requieren señales tempranas sobre proyectos con mayor probabilidad de avance.

## Métrica principal:
AUC ROC — elegida por su robustez ante desequilibrios en clases y porque mide la capacidad global del modelo para distinguir proyectos que avanzan de los que no.

## Resumen ejecutivo:
Este notebook presenta la carga y limpieza de datos, la ingeniería de features, la comparación de modelos (baseline vs tree-based), la optimización ligera de hiperparámetros y la explicación del modelo final con SHAP. El entregable incluye el modelo final serializado, métricas comparativas y recomendaciones operativas para priorizar la cartera.

## Estructura del repositorio:
- notebook_final_entrega.ipynb
- data/ (raw_snapshot.csv o sample_input.csv)
- outputs/models/
- outputs/figures/
- outputs/metrics/
- requirements.txt

## Instrucciones rápidas:
1. Abrir notebook en Colab (link).
2. Ejecutar: !pip install -r requirements.txt
3. Ejecutar Runtime > Restart and run all
