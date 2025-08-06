# Análisis de la Tasa de Cancelación de Clientes (Churn Rate)

## Resumen del Proyecto

Este proyecto se enfoca en el análisis y la predicción de la tasa de cancelación (Churn Rate) de clientes. El objetivo principal fue desarrollar un modelo de Machine Learning capaz de identificar a los clientes con alta probabilidad de cancelar su servicio. A través de este análisis, se han identificado los factores clave que influyen en la cancelación y se han propuesto estrategias de retención basadas en los hallazgos.

## Metodología

La segunda parte del proyecto se centró en la creación, evaluación y justificación de modelos de Machine Learning. El flujo de trabajo incluyó los siguientes pasos:

### 1. Preparación de Datos y Modelado

* **División de Datos:** El conjunto de datos se dividió en un 80% para entrenamiento y un 20% para prueba para una evaluación justa del rendimiento del modelo.
* **Normalización:** Se aplicó normalización a las variables numéricas para escalar los datos, un paso crucial para modelos sensibles a la escala como la Regresión Logística.

### 2. Entrenamiento y Evaluación de Modelos

Se entrenaron y evaluaron dos modelos principales: **Regresión Logística** y **Árbol de Decisión**.

* **Regresión Logística:**
    * **Rendimiento:** Logró una exactitud del 80%.
    * **Justificación:** Se demostró que es el modelo más equilibrado, con una exactitud en entrenamiento (79%) y en prueba (80%) muy similar, lo que indica una buena capacidad de generalización y no presenta overfitting.

* **Árbol de Decisión:**
    * **Rendimiento:** Obtuvo una exactitud del 72% en los datos de prueba.
    * **Justificación:** El modelo mostró un claro **overfitting**, con una exactitud del 99% en entrenamiento pero una caída a 72% en prueba, lo que indica que memorizó los datos de entrenamiento y no generalizó bien.

### 3. Análisis de la Importancia de las Variables

Se analizaron las variables más influyentes en la cancelación para ambos modelos.

* **Variables clave:** Tanto la Regresión Logística como el Árbol de Decisión coincidieron en que las variables relacionadas con el gasto del cliente (`Charges.Total`, `Charges.Monthly` y `Cuentas_Diarias`) y el tipo de contrato (`Contract`) son las más importantes para predecir el Churn.

### 4. Conclusión y Estrategias Propuestas

El modelo final seleccionado fue la **Regresión Logística** debido a su alto rendimiento y estabilidad.

Se propusieron estrategias de retención de clientes basadas en los hallazgos del modelo, tales como:
* Ofrecer valor agregado (ej. streaming o datos extra) a clientes con altos cargos mensuales para justificar el costo.
* Incentivar contratos a largo plazo, ya que están asociados con una menor probabilidad de cancelación.

## Archivos Relevantes

* `modelo_lr.pkl`: El modelo de Regresión Logística serializado con la librería `pickle`, listo para ser cargado y utilizado para nuevas predicciones.
