# Evaluación de algoritmos de Machine Learning para predicción de pago de préstamos

Este repositorio contiene el código desarrollado para evaluar modelos de **Machine Learning supervisado** en la predicción del pago de préstamos. El problema se aborda como una tarea de **clasificación binaria**, donde el objetivo es predecir si un cliente pagará o no su préstamo a partir de variables financieras, demográficas y crediticias.

## Dataset

El conjunto de datos utilizado proviene de la competencia de Kaggle:

[Playground Series - Season 5, Episode 11](https://www.kaggle.com/competitions/playground-series-s5e11/data)

El dataset contiene archivos de entrenamiento y prueba:

* `train.csv`: contiene las variables predictoras y la variable objetivo `loan_paid_back`.
* `test.csv`: contiene las variables predictoras.
* `sample_submission.csv`: formato de referencia para la entrega de predicciones.

La variable objetivo es:

```text
loan_paid_back
```

Donde:

```text
1 = el cliente pagó el préstamo
0 = el cliente no pagó el préstamo
```

## Objetivo del proyecto

El objetivo principal del proyecto es comparar el desempeño de diferentes algoritmos de clasificación para estimar la probabilidad de pago de un préstamo.

## Modelos evaluados

Se evaluaron tres modelos principales:

* Regresión Logística con expansión polinómica.
* Random Forest.
* XGBoost.


## Resultados principales

Los resultados obtenidos muestran que **XGBoost** fue el modelo con mejor desempeño general en la métrica principal ROC-AUC.

| Modelo              | ROC-AUC CV media | ROC-AUC OOF |
| ------------------- | ---------------: | ----------: |
| XGBoost             |           0.9156 |      0.9154 |
| Regresión Logística |           0.9120 |      0.9120 |
| Random Forest       |           0.9098 |      0.9096 |

El mejor modelo fue:

```text
XGBoost
```

Con los siguientes hiperparámetros principales:

```text
n_estimators = 100
max_depth = 4
```

## Requisitos

Las principales librerías utilizadas son:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
xgboost
shap
```

Para instalar las dependencias:

```bash
pip install -r requirements.txt
```

