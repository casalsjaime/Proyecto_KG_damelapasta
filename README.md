# Predicción de Riesgo Financiero — Kaggle "¡Enséñame la Pasta!"

**Autor:** *Jaime García Casals*
**Proyecto:** Clasificación binaria — Reto Kaggle
**Métrica principal:** AUC-ROC

---

## 🎯 Objetivo del Proyecto

El objetivo es predecir la probabilidad de que un cliente incurra en un impago financiero (`SeriousDlqin2yrs`) en los próximos dos años, utilizando datos históricos de crédito.

Este modelo puede ayudar a entidades financieras a tomar decisiones de aprobación de créditos con mayor precisión.

---

## 📌 Dataset

Competición de Kaggle: *"Give Me Some Credit"* (¡Enséñame la Pasta!)

**Tamaño:**

* Train: 150.000 registros
* Test: 101.503 registros

**Variable objetivo:**

* `SeriousDlqin2yrs` — 1 = alto riesgo / 0 = bajo riesgo

**Principales variables predictoras:**

* `RevolvingUtilizationOfUnsecuredLines`: Ratio de utilización de crédito
* `DebtRatio`: Relación deuda/ingreso
* `MonthlyIncome`: Ingreso mensual
* `NumberOfOpenCreditLinesAndLoans`: Número de líneas de crédito
* `NumberOfDependents`: Personas a cargo

---

## 🛠️ Pipeline de Machine Learning

1️⃣ **Carga de datos** (`train.csv`, `test.csv`)

2️⃣ **Análisis exploratorio (EDA)**

* Distribución de variables
* Heatmap de correlaciones
* Revisión de outliers y skewness

3️⃣ **Limpieza de datos**

* Reemplazo de nulos en `MonthlyIncome` mediante mediana
* Imputación de `NumberOfDependents`

4️⃣ **Normalización / Escalado**

* `StandardScaler()` en las features numéricas

5️⃣ **Modelado inicial**
Se probaron varios algoritmos:

* Logistic Regression
* Ridge Classifier
* Lasso
* ElasticNet

6️⃣ **Mejor modelo elegido** → **Gradient Boosting Classifier**

* Optimizado con `GridSearchCV`

---

## ✅ Resultados del Modelo

| Modelo                        |    AUC-ROC |        MAE |
| ----------------------------- | ---------: | ---------: |
| **Gradient Boosting (Final)** | **0.8601** | **0.0627** |

🔹 El modelo presenta un rendimiento competitivo para clasificación de riesgo financiero.
🔹 El AUC-ROC > 0.85 indica buena capacidad discriminativa.

### 🔧 Hiperparámetros finales del mejor modelo

```json
{"learning_rate": 0.1, "max_depth": 3, "n_estimators": 200}
```

---

## 📁 Estructura del Repositorio

```
Proyecto_KG_damelapasta/
│── proyecto_damelapasta.ipynb
│── submission.csv
│── sample_submission.csv
│── README.md  ← este archivo
│
├── train/
├── test/
└── images/   ← (opcional para visualizar EDA)
```

---

## ▶️ Cómo Ejecutar el Proyecto

### Requisitos

```
pip install -r requirements.txt
```

### Ejecución

Ejecutar el notebook por celdas en orden:

✅ Preprocesamiento
✅ Entrenamiento del modelo
✅ Generación de predicciones (`submission.csv`)

```bash
jupyter notebook proyecto_damelapasta.ipynb
```

---

## 📌 Próximas Mejoras

✅ Añadir técnicas de **balanceo de clases** (SMOTE / Class Weights)
✅ Feature Engineering avanzado para ingresos y deuda
✅ Visualizaciones del EDA en el README
✅ Comparación con modelos ensemble más avanzados (XGBoost / CatBoost / LightGBM)

---

## 📎 Competición Kaggle

Enlace directo al reto original:
🔗 [https://www.kaggle.com/c/GiveMeSomeCredit](https://www.kaggle.com/c/GiveMeSomeCredit)

---

## 🧠 Conclusiones Técnicas

* El modelo seleccionado ofrece una muy buena capacidad para diferenciar perfil de riesgo
* El uso de Gradient Boosting fue clave para capturar relaciones no lineales
* El AUC-ROC de 0.86 demuestra un rendimiento sólido en clasificación desbalanceada

> Proyecto orientado a aplicación real en evaluación de solvencia crediticia.

---

**© 2025 — Proyecto de Machine Learning aplicado a riesgo financiero**# Predicción de Riesgo Financiero — Kaggle "¡Enséñame la Pasta!"

**Autor:** *Jaime García Casals*
**Proyecto:** Clasificación binaria — Reto Kaggle
**Métrica principal:** AUC-ROC

---

## 🎯 Objetivo del Proyecto

El objetivo es predecir la probabilidad de que un cliente incurra en un impago financiero (`SeriousDlqin2yrs`) en los próximos dos años, utilizando datos históricos de crédito.

Este modelo puede ayudar a entidades financieras a tomar decisiones de aprobación de créditos con mayor precisión.

---

## 📌 Dataset

Competición de Kaggle: *"Give Me Some Credit"* (¡Enséñame la Pasta!)

**Tamaño:**

* Train: 150.000 registros
* Test: 101.503 registros

**Variable objetivo:**

* `SeriousDlqin2yrs` — 1 = alto riesgo / 0 = bajo riesgo

**Principales variables predictoras:**

* `RevolvingUtilizationOfUnsecuredLines`: Ratio de utilización de crédito
* `DebtRatio`: Relación deuda/ingreso
* `MonthlyIncome`: Ingreso mensual
* `NumberOfOpenCreditLinesAndLoans`: Número de líneas de crédito
* `NumberOfDependents`: Personas a cargo

---

## 🛠️ Pipeline de Machine Learning

1️⃣ **Carga de datos** (`train.csv`, `test.csv`)

2️⃣ **Análisis exploratorio (EDA)**

* Distribución de variables
* Heatmap de correlaciones
* Revisión de outliers y skewness

3️⃣ **Limpieza de datos**

* Reemplazo de nulos en `MonthlyIncome` mediante mediana
* Imputación de `NumberOfDependents`

4️⃣ **Normalización / Escalado**

* `StandardScaler()` en las features numéricas

5️⃣ **Modelado inicial**
Se probaron varios algoritmos:

* Logistic Regression
* Ridge Classifier
* Lasso
* ElasticNet

6️⃣ **Mejor modelo elegido** → **Gradient Boosting Classifier**

* Optimizado con `GridSearchCV`

---

## ✅ Resultados del Modelo

| Modelo                        |    AUC-ROC |        MAE |
| ----------------------------- | ---------: | ---------: |
| **Gradient Boosting (Final)** | **0.8601** | **0.0627** |

🔹 El modelo presenta un rendimiento competitivo para clasificación de riesgo financiero.
🔹 El AUC-ROC > 0.85 indica buena capacidad discriminativa.

### 🔧 Hiperparámetros finales del mejor modelo

```json
{"learning_rate": 0.1, "max_depth": 3, "n_estimators": 200}
```

---

## 📁 Estructura del Repositorio

```
Proyecto_KG_damelapasta/
│── proyecto_damelapasta.ipynb
│── submission.csv
│── sample_submission.csv
│── README.md  ← este archivo
│
├── train/
├── test/
└── images/   ← (opcional para visualizar EDA)
```

---

## ▶️ Cómo Ejecutar el Proyecto

### Requisitos

```
pip install -r requirements.txt
```

### Ejecución

Ejecutar el notebook por celdas en orden:

✅ Preprocesamiento
✅ Entrenamiento del modelo
✅ Generación de predicciones (`submission.csv`)

```bash
jupyter notebook proyecto_damelapasta.ipynb
```

---

## 📌 Próximas Mejoras

✅ Añadir técnicas de **balanceo de clases** (SMOTE / Class Weights)
✅ Feature Engineering avanzado para ingresos y deuda
✅ Visualizaciones del EDA en el README
✅ Comparación con modelos ensemble más avanzados (XGBoost / CatBoost / LightGBM)

---

## 📎 Competición Kaggle

Enlace directo al reto original:
🔗 [https://www.kaggle.com/c/GiveMeSomeCredit](https://www.kaggle.com/c/GiveMeSomeCredit)

---

## 🧠 Conclusiones Técnicas

* El modelo seleccionado ofrece una muy buena capacidad para diferenciar perfil de riesgo
* El uso de Gradient Boosting fue clave para capturar relaciones no lineales
* El AUC-ROC de 0.86 demuestra un rendimiento sólido en clasificación desbalanceada

> Proyecto orientado a aplicación real en evaluación de solvencia crediticia.

---

**© 2025 — Proyecto de Machine Learning aplicado a riesgo financiero**
