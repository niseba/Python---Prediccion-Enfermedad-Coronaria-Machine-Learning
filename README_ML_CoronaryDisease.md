# 🫀 Predicción de Enfermedad Coronaria con Machine Learning — KNN vs Regresión Logística

## 📌 Descripción General

Proyecto de clasificación supervisada aplicado al **Framingham Heart Study Dataset**, uno de los estudios epidemiológicos más reconocidos de la historia médica. El objetivo es predecir la probabilidad de que un paciente desarrolle enfermedad coronaria en los próximos 10 años, comparando el desempeño de dos modelos estadísticos: **K-Nearest Neighbors (KNN)** y **Regresión Logística**.

---

## 📁 Dataset

- **Fuente:** [Framingham Heart Study Dataset (Kaggle)](https://www.kaggle.com/datasets/aasheesh200/framingham-heart-study-dataset)
- **Descripción:** Estudio longitudinal iniciado en 1948 en Framingham, Massachusetts, con datos médicos y demográficos de adultos entre 30 y 62 años
- **Variable objetivo:** `TenYearCHD` (1 = desarrolló enfermedad coronaria en los 10 años siguientes, 0 = no)

---

## ⚙️ Tecnologías

Python · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

---

## 🔍 Análisis Exploratorio (EDA)

El EDA fue el punto de partida para entender la estructura estadística del dataset antes de modelar:

- **Distribución de variables:** histogramas con KDE para evaluar la forma de cada distribución
- **Asimetría (skewness):** cálculo cuantitativo para detectar variables con colas pronunciadas que pudieran afectar el desempeño de los modelos
- **Correlaciones:** heatmap para identificar relaciones lineales entre variables predictoras y con la variable objetivo
- **Valores faltantes:** evaluación del patrón de missingness y tratamiento mediante imputación para preservar el tamaño muestral sin introducir sesgo

Este análisis estadístico guió directamente las decisiones de preprocesamiento, garantizando que los modelos recibieran datos de calidad.

---

## 🧪 Preprocesamiento y Modelado

### Preprocesamiento
- Imputación de valores faltantes con criterio estadístico
- Normalización de variables numéricas para garantizar equidad en la métrica de distancia del KNN

### Modelos implementados
| Modelo | Descripción |
|---|---|
| Regresión Logística | Modelo estadístico lineal para clasificación binaria |
| K-Nearest Neighbors (KNN) | Clasificador basado en distancia; no paramétrico |

### Selección de hiperparámetros
Se aplicó **validación cruzada con 5 folds** usando **ROC-AUC** como métrica de evaluación para encontrar el valor óptimo de `k` (n_neighbors). Este enfoque garantiza una estimación robusta del desempeño, minimizando el riesgo de sobreajuste al dato de entrenamiento.

**Valor óptimo encontrado: k = 1**

---

## 📊 Resultados

| Métrica | Valor |
|---|---|
| AUC-ROC en Validación cruzada | 0.9247 |
| AUC-ROC en Test | 0.9565 |

El modelo KNN superó a la Regresión Logística, logrando un AUC-ROC de **0.9565 en test** — indicando excelente capacidad discriminativa entre pacientes de alto y bajo riesgo coronario.

### Evaluación adicional
- Reporte de clasificación completo (precision, recall, F1-score por clase)
- Matriz de confusión para análisis de errores tipo I y tipo II
- Evaluación sobre muestra aleatoria del dataset original para verificar consistencia

---

## 📌 Conclusión

El modelo KNN con k=1 optimizado mediante validación cruzada demostró un desempeño superior en la predicción del riesgo de enfermedad coronaria a 10 años. Este proyecto integra razonamiento estadístico, preprocesamiento riguroso, selección de modelos basada en evidencia y evaluación robusta — reflejando un flujo de trabajo de Machine Learning aplicado a datos reales con implicaciones clínicas.

---

## 🚀 Habilidades Demostradas

✔️ Análisis exploratorio estadístico (distribuciones, skewness, correlaciones)
✔️ Tratamiento estadístico de valores faltantes (imputación)
✔️ Normalización y preprocesamiento de datos para modelos de distancia
✔️ Implementación y comparación de modelos supervisados (KNN, Regresión Logística)
✔️ Validación cruzada k-fold y optimización de hiperparámetros
✔️ Evaluación con ROC-AUC, matriz de confusión y métricas de clasificación
✔️ Visualización estadística con Matplotlib y Seaborn
✔️ Documentación reproducible en Jupyter Notebook

---

> 🎯 **Nota:** Este proyecto fue desarrollado con énfasis en el razonamiento estadístico detrás de cada decisión — desde el EDA hasta la selección del modelo — no solo en la ejecución técnica del código.
