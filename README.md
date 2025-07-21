# proyecto_final_juantorres_modelospredictivos

GRUPO 1AN-216
PROFESOR: Juan Marcos Castillo, PhD

NOMBRE: Juan Torres

# DESARROLLO DE UN MODELO DE ANÁLISIS PREDICTIVO PARA EL COSTO DE SEGUROS MÉDICOS BASADO EN LOS ANCEDENTES MÉDICOS Y DEMOGRÁFICOS DEL ASEGURADO

Este proyecto tiene como objetivo desarrollar un modelo predictivo capaz de estimar con precisión el costo médico que representa un individuo para una aseguradora, utilizando sus antecedentes médicos y características demográficas.

## DESCRIPCIÓN DEL PROBLEMA

En la actualidad, las compañías de seguros enfrentan el reto de estimar de manera precisa los costos asociados a la salud de cada persona, tomando en cuenta sus antecedentes personales y de salud. Esta evaluación es crucial tanto para la gestión financiera de las empresas de seguros como para distribuir las primas de manera justa entre los asegurados.

El problema de investigación que se plantea consiste en desarrollar un modelo predictivo capaz de estimar el costo del seguro médico (charges) a partir de datos demográficos y de salud, como: la edad, el índice de masa corporal, la cantidad de hijos, el género, el hábito de fumar y la ubicación geográfica. El objetivo es evaluar el desempeño de distintos modelos para identificar cuál ofrece la mejor precisión en la predicción.

Este desafío se aborda utilizando métodos de análisis estadístico, visualización de datos y machine learning, considerando distintos enfoques de modelado, desde regresión lineal hasta modelos más avanzados como XGBoost y Gradient Boosting.

Como ya se presentó, existen muchos aspectos que pueden influir en el costo que representa un individuo para las aseguradoras, en términos de salud. Sin embargo, muchos de ellos tienen su causa raíz en factores demográficos y de estilo de vida. Es por eso que para abordar el problema, se utilizará la información del dataset: Medical Cost Personal Dataset, ya que cuenta con información muy útil en ese sentido. El dataset se descargó de la plataforma Kaggle. con el nombre insurance.csv.

## FUENTE DE DATOS

- NOMBRE DEL ARCHIVO: `insurance.csv`
- FUENTE: Medical Cost Personal Datasets - Kaggle

### VARIABLES INCLUIDAS

- `age`: Edad del beneficiario.
- `sex`: Género del asegurado.
- `bmi`: Índice de Masa Corporal.
- `children`: Número de dependientes cubiertos.
- `smoker`: Fumador o no.
- `region`: Región de residencia en EE.UU.
- `charges`: Costo estimado del seguro médico.

## HERRAMIENTAS UTILIZADAS

- Python: para análisis, modelado y visualización.
- Excel: para explorar transformaciones de la variable objetivo

## RUTA DEL ANÁLISIS

1. EXPLORACIÓN, LIMPIEZA Y CODIFICACIÓN  
Se realizó una limpieza inicial y un análisis estadístico descriptivo.  
Las variables categóricas (`sex`, `smoker` y `region`) fueron transformadas mediante codificación para que pudieran ser utilizadas por los modelos de machine learning. Esto incluyó:
   - **One-Hot Encoding** para `region`
   - **Codificación binaria** para `sex` y `smoker`

El resultado fue un *dataset codificado* listo para modelado.

2. DESARROLLO DE MODELOS PREDICTIVOS  
Se entrenaron cinco modelos distintos:
   - Regresión Lineal
   - Ridge Regression
   - Random Forest
   - Gradient Boosting
   - XGBoost

Las métricas utilizadas para la evaluación fueron: MAE, MSE, RMSE, MAPE y R². En la primera fase, los resultados no fueron satisfactorios.

3. TRANSFORMACIÓN DE LA VARIABLE OBJETIVO  
Se exploraron cuatro transformaciones para mejorar el rendimiento del modelo:
   - Logaritmo natural (`ln y`)
   - Logaritmo base 10 (`log y`)
   - Inverso (`1/y`)
   - Raíz cuadrada (`√y`)

Cada transformación fue aplicada en versiones independientes del dataset y evaluada con los mismos modelos.

4. ENTRENAMIENTO Y EVALUACIÓN DE MODELOS  
Se creó un código separado para cada transformación, en el que se:
   - Importa el dataset transformado
   - Se realiza análisis estadístico
   - Se entrena y evalúa el modelo
   - Se generan gráficos de valores reales vs predichos y de residuos

## CONCLUSIONES

- Se alcanzó el objetivo de desarrollar un modelo eficaz para predecir el costo del seguro médico a partir de datos personales.
- La transformación logarítmica (`ln y`) fue clave para mejorar el ajuste del modelo, ya que la variable original presentaba una distribución sesgada hacia la derecha.
- El modelo Gradient Boosting fue el más efectivo en todas las versiones analizadas, destacando por su capacidad para capturar relaciones no lineales y complejas.




