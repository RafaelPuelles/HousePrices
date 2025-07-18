# HousePrices

Este proyecto utiliza modelos de regresión avanzados para predecir el precio de viviendas a partir de un conjunto de datos con características diversas. El trabajo fue desarrollado en Google Colaboratory, aprovechando el entorno distribuido de Apache Spark para el procesamiento y entrenamiento de los modelos.

## Objetivo

Predecir el precio final de viviendas en base a sus características físicas y de ubicación, utilizando distintos algoritmos de regresión implementados en PySpark. El objetivo es comparar el rendimiento de los modelos y evaluar su capacidad predictiva en un entorno escalable.

## Dataset

Se utilizó el conjunto de datos **"House Prices - Advanced Regression Techniques"**, disponible en Kaggle:  
🔗 [https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

> **Nota:** Por restricciones de licencia, el dataset no está incluido en este repositorio.  
> Para ejecutar el notebook, deberás descargar manualmente los datos desde Kaggle y colocarlos en una carpeta local llamada `/data`.

## Herramientas y tecnologías

- **Python 3**: Lenguaje de programación utilizado.
- **Google Colab**: Entorno de desarrollo utilizado para el proyecto.
- **Apache Spark (PySpark)**: Librería principal para procesamiento distribuido y machine learning. Usada para:
  - `pyspark.ml.regression.RandomForestRegressor`, `GBTRegressor`, `DecisionTreeRegressor`, `FMRegressor` (modelos de regresión).
  - `pyspark.ml.feature.StringIndexer`, `VectorAssembler` (transformación de datos).
  - `pyspark.ml.tuning.CrossValidator`, `ParamGridBuilder` (ajuste de hiperparámetros).
  - `pyspark.ml.evaluation.RegressionEvaluator` (evaluación de modelos).
  - `pyspark.sql.functions` y `pyspark.sql.types` para el procesamiento de datos.
- **Pandas**: Para manipulación y análisis de datos.
  
## Modelos aplicados

Se entrenaron y evaluaron los siguientes modelos de regresión utilizando PySpark MLlib:

- `RandomForestRegressor`
- `GBTRegressor` (Gradient Boosted Trees)
- `DecisionTreeRegressor`
- `FMRegressor` (Factorization Machines)

## Métrica de evaluación

La métrica utilizada para comparar el rendimiento de los modelos fue el **Root Mean Squared Error (RMSE)**, una medida estándar para tareas de regresión.

## Resultados

Los modelos fueron evaluados utilizando **Root Mean Squared Error (RMSE)**. A continuación se presentan los valores obtenidos por cada uno:

| Modelo                  | RMSE                      |
|-------------------------|---------------------------|
| RandomForestRegressor   | **26,360.45**             |
| FMRegressor             | 41,046.22                 |
| GBTRegressor            | 43,981.54                 |
| DecisionTreeRegressor   | 54,961.56                 |

El modelo que obtuvo el mejor desempeño fue el **Random Forest Regressor**, logrando el menor error promedio en la predicción del precio de las viviendas. El rendimiento de los otros modelos fue considerablemente inferior, especialmente en el caso del `DecisionTreeRegressor`, lo que sugiere que los modelos de ensamblado y de aprendizaje más robusto tienen mejor capacidad predictiva para este conjunto de datos.

## Estructura del repositorio

```
/
├── notebooks/             # Contiene el notebook de Google Colab (.ipynb)
├── data/                  # (Vacía por defecto) Colocar aquí los datos descargados de Kaggle
└── README.md              # Este archivo
```

## Cómo ejecutar el proyecto

1. Descarga el dataset desde Kaggle y colócalo en la carpeta `data/`.
2. Abre el archivo `.ipynb` en Google Colab.
3. Ejecuta las celdas paso a paso. El entorno Spark ya está preconfigurado en Colab.
