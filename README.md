# 🚢 Predicción de Supervivencia en el Titanic: Análisis y Preprocesamiento Avanzado

Este repositorio contiene el código y el informe de una práctica de Máster centrada en la **calidad de los datos, el preprocesamiento y la ingeniería de características (Feature Engineering)** utilizando el clásico dataset del Titanic.

El objetivo principal de este proyecto no es solo aplicar un algoritmo de Machine Learning, sino demostrar cómo un tratamiento inteligente de los datos mejora tanto la precisión como la **interpretabilidad** de las reglas de decisión generadas por el modelo.

## 🛠️ Tecnologías Utilizadas
* **Lenguaje:** Python 3
* **Análisis y Manipulación de Datos:** Pandas, NumPy
* **Visualización:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Decision Trees, IterativeImputer)

## 📊 Pipeline del Proyecto

El proyecto sigue una metodología rigurosa dividida en las siguientes fases:

1. **Exploración de Datos (EDA):** Identificación de valores nulos críticos (ej. `Cabin` con 77% de nulos) y análisis de la distribución de la supervivencia.
2. **Tratamiento de Valores Perdidos:** * Aplicación de imputación avanzada multivariante (**MICE**) para la variable `Age`, evitando la alteración de la varianza que produce una mediana simple.
3. **Ingeniería de Características (Feature Engineering):**
   * Extracción de **Títulos sociales** (`Mr`, `Mrs`, `Miss`, `Master`) a partir del nombre para capturar implícitamente género, edad y estatus social.
   * Creación de la métrica `Tamano_Familia` unificando `SibSp` y `Parch`.
4. **Discretización y Transformación:** * Categorización de la tarifa (`Fare`) en cuartiles para minimizar el ruido de los valores atípicos.
   * Aplicación estricta de **One-Hot Encoding** para preparar una matriz matemática limpia (0 y 1).
5. **Modelado y Evaluación:** Comparación de un modelo "Baseline" (sin preprocesar) frente a un modelo "Optimizado" utilizando Árboles de Decisión.

## 📈 Resultados Destacados

Al comparar el modelo base con el modelo preprocesado sobre los mismos 891 pasajeros, se observó no solo una mejora en la precisión métrica (*Accuracy*), sino un salto cualitativo en la **lógica del algoritmo**:

* **Interpretabilidad Semántica:** El modelo optimizado basó sus decisiones principales en la nueva variable `Titulo` (detectando, por ejemplo, que los niños varones bajo el título "Master" tenían prioridad de supervivencia), alineando el modelo matemático con la realidad histórica ("mujeres y niños primero").
* **Robustez:** La discretización de las tarifas evitó el sobreajuste que provocaban las variables continuas extremas en el modelo base.




## 🚀 Cómo ejecutar este proyecto

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/Teodosiodg2002/titanic-preprocessing.git](https://github.com/Teodosiodg2002/titanic-preprocessing.git)
