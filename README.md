# 📉 Telecom X – Predicción de Cancelación de Clientes (Churn Prediction)

Proyecto de análisis y modelado predictivo para anticipar la cancelación de clientes en una empresa de telecomunicaciones. Se aplicaron técnicas de *machine learning*, análisis exploratorio y herramientas de interpretabilidad para entender los factores que influyen en el abandono y proponer estrategias de retención efectivas.

---

## 📁 Estructura del Repositorio
```
📦 Telecom_X_2_challenge
 ├── Telecom_X_2_challenge.ipynb           # Notebook de análisis y modelado
 ├── champion_model.pkl                    # Modelos Champion entrenado
 └── README.md                             # Este archivo
```

---

## 🧠 Objetivo del Proyecto
Desarrollar un modelo capaz de predecir si un cliente cancelará su servicio, utilizando información sobre contrato, servicios contratados, historial de pagos y variables de uso.  
El propósito es que la empresa pueda implementar acciones proactivas para reducir la tasa de cancelación (*churn rate*).

---

## 🧪 Proceso de Desarrollo

### 1. Carga y limpieza de datos
- Eliminación de identificadores únicos irrelevantes  
- Normalización de variables numéricas con *StandardScaler*  
- Codificación de variables categóricas con *get_dummies*  
- Balanceo de clases con **SMOTE**  

### 2. Análisis Exploratorio (EDA)
- Histogramas, boxplots y gráficos de correlación  
- Análisis dirigido: relación entre **tiempo de contrato × cancelación** y **gasto total × cancelación**  
- Identificación de variables influyentes: tipo de contrato, método de pago, cargos mensuales  

### 3. Selección de características
- **SelectKBest con f_classif**  
- Selección de las variables más significativas para el modelado  

### 4. Entrenamiento de modelos
- Decision Tree  
- Random Forest  
- Logistic Regression  
- KNN  
- XGBoost  
- SVM  

### 5. Evaluación
- Métricas: Accuracy y ROC-AUC  
- Matrices de confusión  
- Importancia de variables (Random Forest + XGBoost)  

---

## 🏆 Resultados

| Modelo                | Accuracy | ROC-AUC |
|------------------------|----------|---------|
| **XGBoost**           | 0.782    | 0.830   |
| Random Forest          | 0.779    | 0.826   |
| SVM                    | 0.753    | 0.819   |
| Logistic Regression    | 0.750    | **0.842** |
| Decision Tree          | 0.735    | 0.674   |
| KNN                    | 0.685    | 0.751   |

✅ **Conclusión:**  
- El **mejor modelo en términos de Accuracy** fue **XGBoost** (78.2%).  
- El **mejor modelo en términos de ROC-AUC** fue **Logistic Regression** (0.842), destacándose en capacidad de discriminación.  
- Ambos modelos resultan complementarios: **XGBoost ofrece performance general sólida**, mientras que **Regresión Logística entrega interpretabilidad y AUC más alto**.

---

## 🔍 Principales Factores de Cancelación
Según la importancia de variables y el análisis dirigido:

- Clientes con contrato **mensual (Month-to-Month)** tienen mayor probabilidad de cancelar.  
- **Método de pago:** “electronic check” se asocia fuertemente al churn.  
- **Altos cargos mensuales** incrementan la cancelación.  
- Clientes con **bajo tiempo de permanencia** (nueva antigüedad) tienden a abandonar antes.  
- La falta de **servicios adicionales** (soporte técnico, seguridad, respaldo en la nube) aumenta el riesgo.  

---

## 💡 Estrategias de Retención Sugeridas
- Incentivar la migración a contratos anuales o de 2 años.  
- Promocionar métodos de pago automáticos con tarjeta o débito.  
- Diseñar bundles de servicios de valor agregado (seguridad + soporte + respaldo).  
- Ofrecer beneficios especiales a clientes nuevos para aumentar la fidelidad en los primeros meses.  
- Monitorear clientes con cargos elevados y ofrecer planes personalizados.  

---

## ⚙️ Requisitos
- Python 3.8+  
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- imblearn  
- shap  
- xgboost  

---

## ▶️ Cómo Ejecutar el Proyecto

Clona el repositorio:
```bash
git clone https://github.com/yudithl125/Telecom_X_2_challenge.git
cd Telecom_X_2_challenge
```

Crea un entorno virtual (opcional):
```bash
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate       # Windows
```

Instala dependencias:
```bash
pip install -r requirements.txt
```

Abre los notebooks:
```bash
jupyter notebook
```

---

## 📌 Notas Técnicas
- Se utilizó **SMOTE** para balancear las clases antes del entrenamiento.  
- División de datos: **70% train / 30% test**.  
- Métricas evaluadas sobre el *test set*.  
- Interpretabilidad basada en **feature importance** y coeficientes logísticos.  

---

## 📚 Archivos Relevantes
- **data/**: Datos tratados en formato CSV  
- **informe_cancelacion.md**: Informe técnico detallado  
- **notebooks/**: Paso a paso de análisis y modelado  

---

## ✅ Estado del Proyecto
✔️ **Finalizado** | 📅 Agosto 2025
