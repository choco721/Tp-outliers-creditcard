*tp-outliers-creditcard*

Trabajo Práctico de detección y manejo de outliers sobre el dataset de fraude en tarjetas de crédito, desarrollado para la materia Inteligencia Artificial y Aprendizaje Automático I.
Autores: Chocobares Juan Cruz — Formenti Agustín

Descripción
El dataset contiene 284.807 transacciones de tarjetas de crédito realizadas por titulares europeos en septiembre de 2013, de las cuales solo 492 (0,17%) son fraudes. El objetivo del trabajo es aplicar técnicas de detección y manejo de outliers en un contexto donde los outliers son precisamente los casos de interés, por lo que eliminarlos sería un error.

Estructura del notebook
Paso 1 — Carga y Exploración del Dataset

Descarga del dataset desde Kaggle
Análisis de shape, tipos de datos y valores nulos
Distribución de clases y desbalance
Estadísticas descriptivas de Amount y Time
Visualizaciones: histogramas y boxplot de Amount por clase

Paso 2 — Detección de Outliers

IQR sobre Amount: límites, máscara y análisis de fraudes detectados
Z-Score sobre Amount: comparación con IQR
Isolation Forest sobre todas las variables numéricas (V1-V28 + Amount)
Reporte de clasificación de Isolation Forest vs etiquetas reales

Paso 3 — Estrategias de Tratamiento

Estrategia A — Winsorización: recorte al percentil 1 y 99 sin eliminar filas
Estrategia B — Transformación logarítmica: log1p(Amount) para comprimir la escala
Visualización comparativa de las tres versiones de Amount

Paso 4 — Comparación de Estrategias

Entrenamiento de Regresión Logística con cada versión de Amount
Reportes de clasificación para clase Fraude
Tabla y gráfico comparativo de precision, recall y F1-Score

Preguntas de Reflexión

¿Por qué no eliminar outliers en este dataset?
¿Isolation Forest es útil para detectar fraudes?
¿Qué estrategia de tratamiento de Amount mejora más la detección?


Dataset

Fuente: Kaggle — Credit Card Fraud Detection
Tamaño: 284.807 transacciones
Variables: Time, V1–V28 (componentes PCA), Amount, Class
Desbalance: 0,17% de fraudes


Tecnologías

Python 3.11
pandas, numpy, scipy
scikit-learn (IsolationForest, LogisticRegression)
matplotlib, seaborn
kagglehub


Cómo ejecutar

Clonar el repositorio
Instalar las dependencias
Abrir el notebook Metodos_avanzados_para_tratamiento_de_outliers.ipynb en Jupyter
Ejecutar las celdas en orden — el dataset se descarga automáticamente desde Kaggle
