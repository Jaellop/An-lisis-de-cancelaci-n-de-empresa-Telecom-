# Predicción de Cancelación de Clientes (Churn) en Telecom X

## Propósito del análisis

El propósito de este proyecto es **predecir la cancelación de clientes
(Churn)** en la empresa *Telecom X* a partir de variables relevantes del
servicio, perfil de clientes y comportamiento de consumo.

El análisis busca:\
- Identificar los principales factores que influyen en la cancelación.\
- Entrenar modelos de clasificación para predecir el churn.\
- Proponer estrategias de retención basadas en los resultados obtenidos.

------------------------------------------------------------------------

## Estructura del proyecto

-   **`Telecom_Test_3.ipynb`** → Cuaderno principal con todo el flujo
    del análisis, EDA y modelado.\
-   **`datos_tratados.csv`** → Datos procesados y listos para ser usados
    en el modelado.\
-   **`/visualizaciones/`** → Carpeta opcional con gráficos generados
    durante el análisis exploratorio (heatmaps, boxplots, histogramas,
    etc.).\
-   **`README.md`** → Este archivo explicativo.

------------------------------------------------------------------------

##  Preparación de los datos

1.  **Clasificación de variables**
    -   **Categóricas:** tipo de contrato, forma de pago, servicios
        adicionales (ej. `OnlineSecurity`, `TechSupport`,
        `InternetService`).\
    -   **Numéricas:** `tenure`, `Charges.Monthly`, `Charges.Total`.
2.  **Normalización y codificación**
    -   Variables categóricas → transformadas con **One-Hot Encoding**.\
    -   Variables numéricas → normalizadas mediante escalado, mejorando
        el desempeño de modelos sensibles a magnitudes.
3.  **Separación de conjuntos de datos**
    -   **70% entrenamiento**\
    -   **30% prueba**\
        → Esta división permitió evaluar la capacidad de generalización
        de los modelos.

------------------------------------------------------------------------

##  Modelado y justificación

Se entrenaron modelos de clasificación como:\
- **K-Nearest Neighbors (KNN)**\
- **Decision Tree Classifier**

**Justificación:**\
- KNN fue elegido por su capacidad de capturar similitudes entre
clientes.\
- Árboles de decisión permiten interpretar con claridad los factores que
más influyen en el churn.

**Métricas evaluadas:**\
- Accuracy\
- Precision\
- Recall\
- F1-score\
- Matriz de confusión

------------------------------------------------------------------------

##  Análisis Exploratorio (EDA) e Insights

Ejemplos de visualizaciones:\
- **Heatmap de correlaciones** → para identificar relaciones entre
variables.\
- **Boxplot de churn vs cargos mensuales** → muestra que clientes con
cargos altos tienden a cancelar más.\
- **Distribución de tenure** → confirma que clientes con baja antigüedad
son más propensos a cancelar.

**Principales hallazgos:**\
- Contratos **mensuales (Month-to-month)** están fuertemente asociados
al churn.\
- La ausencia de servicios como `OnlineSecurity` y `TechSupport`
incrementa el riesgo de cancelación.\
- Internet con **Fiber Optic** está correlacionado con mayor churn
(posible efecto de precios más altos).\
- Clientes que pagan con **Electronic Check** presentan mayor churn.\
- **Tenure alto y contratos largos (Two year)** reducen
significativamente la cancelación.

------------------------------------------------------------------------

##  Estrategias de retención

-   Incentivar migración de contratos mensuales → contratos de 1--2 años
    con beneficios.\
-   Promover bundles con servicios de seguridad en línea y soporte
    técnico.\
-   Ofrecer descuentos o programas de lealtad para clientes con alto
    riesgo de cancelación.\
-   Migrar clientes de **Electronic Check** a pagos automáticos con
    beneficios promocionales.

------------------------------------------------------------------------

## Instrucciones de ejecución

1.  Clonar este repositorio o abrir el cuaderno en **Google Colab** /
    Jupyter.\
2.  Asegurarse de tener el archivo **`datos_tratados.csv`** en el mismo
    directorio del cuaderno.\
3.  Instalar las librerías necesarias (si no están ya en el entorno):

``` bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

4.  Ejecutar las celdas en orden para:
    -   Preparar y explorar los datos.\
    -   Entrenar los modelos.\
    -   Visualizar resultados y métricas de desempeño.

------------------------------------------------------------------------
 En resumen, el proyecto demuestra que las variables contractuales,
los métodos de pago, los servicios adicionales y la antigüedad del
cliente son los principales determinantes del churn en *Telecom X*.
