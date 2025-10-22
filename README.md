# Taller 1: Predicción de Riesgo de Accidentes

Este repositorio contiene el desarrollo del Taller 1, enfocado en la creación de modelos de machine learning para predecir el riesgo de accidentes de tráfico. Se exploraron dos enfoques principales: un modelo lineal simple y un ensamble avanzado de stacking.

## 🚀 Resultados en la Competición

Los modelos fueron evaluados en la competición de Kaggle, obteniendo los siguientes resultados:

| Modelo | Score (RMSE) | Posición en Leaderboard |
| :--- | :---: | :---: |
| **Ensamble Stacking** | **0.05556** | **696** |
| Modelo Lineal (Ridge) | 0.07199 | 2559 |

---

## 🤖 Comparación de Modelos

### Modelo Lineal (Baseline)
Se implementó un modelo de **Regresión Ridge** como punto de partida. Aunque es rápido y fácil de interpretar, su naturaleza lineal limita su capacidad para capturar las interacciones complejas y no lineales presentes en los datos, como la relación entre el clima, la iluminación y el tipo de vía. Esto se reflejó en un score de **0.07199**, ubicándose en la posición **2559**.

### Ensamble Stacking (Modelo Avanzado)
Para mejorar el rendimiento, se construyó un **ensamble de stacking**. Este enfoque es significativamente más potente por las siguientes razones:

1.  **Combina Fortalezas**: El ensamble utilizó tres modelos base robustos (**XGBoost, LightGBM y CatBoost**). Cada uno de estos modelos es experto en identificar diferentes tipos de patrones en los datos.
2.  **Meta-aprendizaje**: En lugar de promediar las predicciones, el stacking añade un "meta-modelo" (`Ridge`) que aprende a ponderar de forma inteligente las predicciones de los modelos base. Este "gerente" sabe cuándo confiar más en XGBoost, cuándo en LightGBM, etc., según el tipo de datos de entrada.
3.  **Reducción del Error**: Al combinar las perspectivas de múltiples modelos diversos, el ensamble es más robusto y generaliza mejor, reduciendo el error de predicción.

Gracias a esta estrategia avanzada, el ensamble de stacking logró un score de **0.05556**, lo que nos posicionó en el **lugar 696** del leaderboard, demostrando ser un enfoque muy superior para este problema.

---

## 🛠️ Estructura del Repositorio

* `/data`: Contiene los datasets de entrenamiento (`train.csv`) y prueba (`test.csv`).
* `punto1.ipynb` a `punto4.ipynb`: Notebooks con el desarrollo de la solución, desde el análisis exploratorio hasta el modelado final.
* `/submission files`: Contiene los archivos de envío generados, incluyendo `submission_ensemble.csv` y `submission_lineal.csv`.
