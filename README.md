# Proyecto Telecom X – Parte 2: Predicción de Cancelación (Churn)

## Propósito del Proyecto

Este proyecto tiene como objetivo principal **predecir la cancelación de clientes (churn)** en la empresa Telecom X, utilizando modelos de machine learning. A través del análisis de datos históricos de clientes, buscamos identificar patrones que indiquen una mayor probabilidad de cancelación, para así ayudar a la empresa a **anticiparse y desarrollar estrategias de retención efectivas**.

---

> ⚠️ **Nota**: La primera parte del código, correspondiente a la limpieza de datos y análisis exploratorio inicial, fue desarrollada previamente en el proyecto "Telecom X – Parte 1". Por tanto, el código actual **comienza a partir del preprocesamiento para Machine Learning**.

---

## Preparación y Tratamiento de Datos

### Clasificación de Variables

- **Numéricas**: `meses_contrato`, `cargo_mensual`, `cargo_total`, entre otras.
- **Categóricas**: `genero`, `tipo_contrato`, `metodo_pago`, `servicio_tv`, etc.
- **Booleanas**: `es_adulto_mayor`, `tiene_pareja`, `tiene_dependientes`, etc.

### Codificación

Se aplicaron diferentes técnicas según el tipo de variable:
- Para variables con respuestas `Yes/No`, se utilizaron valores booleanos o `0/1`.
- Para variables categóricas con múltiples valores, se usó **One-Hot Encoding** con `pd.get_dummies()`.

### Normalización

Se normalizaron las variables numéricas al aplicar **StandardScaler** solo para modelos sensibles a la escala de los datos, como la Regresión Logística. Modelos como Random Forest no requieren normalización.

### División de los Datos

Los datos fueron separados en:
- **Conjunto de entrenamiento**: 80%
- **Conjunto de prueba**: 20%
  
Esto permite entrenar los modelos y evaluar su capacidad de generalización.

---

## Modelos Predictivos

Se entrenaron dos modelos de clasificación:

1. **Regresión Logística (con normalización)**  
   Modelo lineal que se beneficia de la normalización de variables. Mostró un buen rendimiento general con:
   - Accuracy: 80.3%
   - Precision: 65.7%
   - Recall: 54.3%
   - F1-score: 59.5%

2. **Random Forest (sin normalización)**  
   Modelo basado en árboles, robusto ante escalas distintas. Sus resultados fueron:
   - Accuracy: 78.9%
   - Precision: 63.8%
   - Recall: 47.6%
   - F1-score: 54.5%

### Comparación y Elección del Modelo

Ambos modelos mostraron un rendimiento aceptable, pero la **regresión logística fue más equilibrada** en todas las métricas, mientras que Random Forest tuvo un menor recall, lo que implica que identificó menos clientes propensos a cancelar.

---

### Ejemplos de visualizaciones incluidas:
- Boxplots de meses_contrato vs cancelación.
- Matriz de correlación para variables numéricas.
- Gráficos de barras para proporción de cancelación.

---
Sofía Miranda

