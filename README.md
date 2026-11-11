# California Housing Prices

Proyecto de análisis exploratorio y predicción del precio medio de viviendas en California mediante técnicas de análisis de datos y *Machine Learning*.

## Descripción

El objetivo es explorar las características de las zonas de California y evaluar qué tan bien distintos modelos de regresión pueden estimar el precio medio de las viviendas (`median_house_value`). El proyecto conserva un flujo de trabajo introductorio: exploración, visualización, creación de variables, preprocesamiento y comparación de modelos.

## Contenido del proyecto

| Archivo | Descripción |
|---|---|
| `CaliforniaHousing.ipynb` | Notebook con el análisis completo, visualizaciones, entrenamiento y evaluación de modelos. |
| `requirements.txt` | Librerías necesarias para ejecutar el proyecto. |
| `housing.csv` | Archivo de datos requerido. No está incluido en este repositorio; debe añadirse localmente. |

## Análisis realizado

1. **Exploración de datos:** revisión de dimensiones, tipos de variables, valores faltantes y distribución de las categorías de proximidad al océano.
2. **Visualización:** histogramas, distribución geográfica de las observaciones y mapa de precios.
3. **Correlaciones:** análisis de la relación entre las variables numéricas y el precio medio.
4. **Ingeniería de características:** creación de `rooms_per_household`, `bedrooms_per_room` y `population_per_household`.
5. **Preprocesamiento:** imputación de valores faltantes, estandarización de variables numéricas y codificación One-Hot de variables categóricas.
6. **Modelado:** comparación de regresión lineal, árbol de decisión y bosque aleatorio. Se incluye un modelo base como referencia.
7. **Evaluación:** uso de R², MAE y RMSE, además de gráficos de predicciones, residuos e importancia de variables.

### Archivo de datos

Coloca el archivo `housing.csv` en la carpeta principal del proyecto. También puedes guardarlo dentro de una carpeta llamada `data/`. El notebook busca el archivo en ambas ubicaciones.

La estructura esperada es:

```text
CaliforniaHousing/
├── CaliforniaHousing.ipynb
├── README.md
├── requirements.txt
└── housing.csv
```

Abre el notebook:

```bash
jupyter notebook CaliforniaHousing.ipynb
```

Ejecuta las celdas en orden.

## Modelos y métricas

Los modelos comparados son:

- **Regresión lineal:** referencia de un modelo que representa relaciones lineales entre las variables predictoras y el precio.
- **Árbol de decisión:** permite representar relaciones no lineales mediante reglas de decisión.
- **Bosque aleatorio:** combina varios árboles de decisión para obtener una predicción agregada.
- **Modelo base:** predice la mediana del precio del conjunto de entrenamiento y sirve como punto de comparación.

Se reportan tres métricas:

- **R²:** mide la proporción de variabilidad explicada por el modelo.
- **MAE:** mide el promedio del error absoluto en las unidades del precio.
- **RMSE:** mide el error cuadrático medio en la misma escala del precio y penaliza más los errores grandes.

Los valores finales se calculan al ejecutar el notebook; no se fijan en este README porque dependen de los datos y del flujo de entrenamiento.

## Observaciones del análisis exploratorio

En la revisión inicial del conjunto de datos original se encontraron 20.640 registros y 10 columnas. La variable `total_bedrooms` contiene 207 valores faltantes. Entre las variables numéricas originales, `median_income` presentó una correlación positiva de aproximadamente 0,69 con `median_house_value`.

