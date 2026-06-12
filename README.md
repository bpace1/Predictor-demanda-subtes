# 🚇 Análisis de la Demanda del Subte de Buenos Aires

> **Proyecto Integrador — Metodología de la Investigación**  
> Licenciatura en Ciencia de Datos · Universidad Guillermo Brown  
> Grupo 5: Antolini · Avecilla · Bianciotto · Calcia · Pace · Zorzolo

---

## 📋 Descripción

Este proyecto aplica técnicas de **Ciencia de Datos y Machine Learning** para analizar la demanda de pasajeros en la red de subterráneos de la Ciudad Autónoma de Buenos Aires (CABA). A partir de registros históricos de flujo de pasajeros, datos de tarifas y variables temporales, se construyeron modelos capaces de estimar la elasticidad-precio de la demanda, detectar cambios estructurales en la serie y segmentar estaciones según sus perfiles horarios de uso.

El estudio surge en el contexto de una caída sin precedentes regionales: el subte de Buenos Aires transportó en abril de 2025 un **39% menos de pasajeros** que en abril de 2019, presentando el peor desempeño relativo del continente respecto a su nivel pre-pandemia.

---

## ❓ Hipótesis

> **H5:** Los aumentos sostenidos en la tarifa del subte, especialmente a partir de 2024, podrían constituir uno de los principales factores explicativos de la caída en la demanda —por encima de variables estructurales como el teletrabajo— y su efecto varía significativamente entre líneas, siendo la **Línea D** la más sensible al precio y las **Líneas A y E** las menos elásticas.

---

## 🎯 Objetivos

### General
Desarrollar modelos de análisis que permitan estudiar la demanda de pasajeros en la red de subtes de Buenos Aires, aplicando técnicas de Machine Learning y siguiendo un enfoque metodológico riguroso orientado a la validación de hipótesis.

### Específicos
- Realizar un análisis exploratorio (EDA) para identificar patrones de uso, estacionalidad y correlaciones entre variables.
- Pre-procesar y transformar el dataset garantizando su calidad para el modelado.
- Construir modelos de **regresión lineal múltiple** (log-log) para estimar la elasticidad-precio de la demanda.
- Implementar modelos de **series temporales SARIMA/SARIMAX** para capturar tendencias y patrones estacionales.
- Aplicar **clustering K-Means** para identificar grupos de estaciones con comportamientos similares.
- Realizar **Test de Chow** para evaluar posibles quiebres estructurales en la serie.
- Contrastar resultados con la hipótesis y derivar recomendaciones para la gestión del sistema.

---

## 🧪 Metodología

El trabajo adopta un enfoque **cuantitativo, explicativo y predictivo**, con diseño no experimental sobre datos históricos observados. El proceso completo comprende cuatro etapas:

| Etapa | Descripción |
|-------|-------------|
| **1 – EDA** | Análisis exploratorio: evolución temporal, estacionalidad (diaria/semanal/mensual), diferencias entre líneas, correlación tarifa-pasajeros |
| **2 – Limpieza** | Tratamiento de nulos, outliers y duplicados; construcción de variables temporales derivadas |
| **3 – Modelado** | Regresión log-log, SARIMA/SARIMAX, K-Means y Test de Chow |
| **4 – Evaluación** | Validación out-of-sample, comparación de métricas, contraste de hipótesis |

### Modelos utilizados

- 📈 **Regresión Lineal Múltiple (log-log)** — Estimación de elasticidad-precio, con efectos fijos por línea y controles mensuales
- ⏱️ **SARIMA / SARIMAX** — Series temporales con componentes estacionales y tarifa real como variable exógena
- 🔵 **K-Means Clustering** — Segmentación de estaciones por perfil horario de demanda
- 🔬 **Test de Chow** — Detección de quiebres estructurales (COVID-19, tarifazo mayo 2024)

---

## 📊 Resultados Principales

| Modelo / Análisis | Resultado |
|---|---|
| **Elasticidad-precio** | **−0,219** (inelástica y estadísticamente significativa) |
| **Interpretación** | Un aumento del 10% en la tarifa real reduce la demanda ~2,2% |
| **SARIMA (pre-COVID)** | R² out-of-sample = **0,465** — capacidad predictiva razonable en período estable |
| **SARIMAX (serie completa)** | R² out-of-sample = **−0,451** — limitado por shocks estructurales post-pandemia |
| **K-Means (clustering)** | Silhouette score ≈ **0,332** — 2 grupos de estaciones con perfiles horarios diferenciados |
| **Test de Chow (mayo 2024)** | Sin quiebre estructural significativo atribuible exclusivamente al tarifazo |

### Conclusiones clave

- ✅ Se confirmó una **elasticidad-precio negativa, inelástica y estadísticamente significativa**.
- ⚠️ La pandemia de COVID-19 y los cambios en los hábitos de movilidad son los **factores estructurales dominantes** en la caída de pasajeros.
- 📉 La tarifa opera como un factor económico relevante de **efecto gradual e inelástico**.
- ❌ Se refutó la hipótesis fuerte: el tarifazo de mayo 2024 **no constituye el quiebre estructural dominante** de la demanda.
- 🌍 Comparativamente, Buenos Aires presenta el **peor desempeño relativo de la región** en recuperación post-pandemia.

---

## 🛠️ Tecnologías y Herramientas

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Statsmodels](https://img.shields.io/badge/Statsmodels-4B8BBE?style=flat-square&logo=python&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat-square&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

| Herramienta | Uso |
|---|---|
| **Python** | Lenguaje principal de análisis y modelado |
| **Pandas** | Manipulación y transformación de datos tabulares |
| **NumPy** | Cómputo numérico y operaciones sobre arrays |
| **Scikit-learn** | Regresión, clustering (K-Means) y métricas de evaluación |
| **Statsmodels** | Modelos SARIMA/SARIMAX, regresión con significancia estadística, Test de Chow |
| **Matplotlib / Seaborn** | Visualizaciones del EDA y resultados |
| **Jupyter Notebook** | Entorno interactivo reproducible |

---

## 📂 Estructura del Repositorio

```
📦 Predictor-demanda-subtes/
├── 📓 TP-Metodologia-Integrador-Antolini_Avecilla_Bianciotto_Calcia_Pace_Zorzolo.ipynb
│       └── Notebook completo con EDA, preprocesamiento, modelado y evaluación
├── 📄 Informe - Metodología de la investigación - Grupo 5 CCDD.pdf
│       └── Informe académico completo del proyecto
├── 📄 Grupo-5-Ciencia-de-Datos.pdf
│       └── Presentación del grupo
└── 📄 Enunciado.pdf
        └── Consignas del trabajo integrador
```

---

## 📏 Métricas de Evaluación

- **R² ajustado** — Proporción de varianza explicada por el modelo
- **MAE** (Mean Absolute Error) — Error absoluto medio
- **RMSE** (Root Mean Squared Error) — Raíz del error cuadrático medio
- **AIC / BIC** — Criterios de información para selección de parámetros SARIMA
- **Silhouette Score** — Calidad del agrupamiento K-Means
- **Coeficientes de elasticidad** con intervalos de confianza al 95%

---

## 🔭 Trabajo Futuro

- Incorporar datos completos y actualizados del período 2020–2025
- Mejorar la reconstrucción mensual de la serie tarifaria
- Incluir variables de calidad del servicio y frecuencia de formaciones
- Incorporar indicadores de teletrabajo y movilidad alternativa
- Reestimar la elasticidad con modelos de panel con errores estándar robustos o clusterizados por línea

---

## 👥 Autores

| Nombre |
|--------|
| Antolini |
| Avecilla |
| Bianciotto |
| Calcia |
| Pace |
| Zorzolo |

*Licenciatura en Ciencia de Datos — Universidad Guillermo Brown*  
*Materia: Metodología de la Investigación — 2025*

---

## 📚 Referencias

1. Chequeado (2025). *Cada vez menos gente viaja en el subte porteño: la cantidad de pasajeros cayó un 39% desde 2019.*
2. Chequeado (2025). *Aumentó el subte en CABA: ¿qué promociones ofrecen los bancos y billeteras virtuales?*
3. Centro de Estudios Metropolitanos (2025). *Cada vez menos gente viaja en subte.*
4. Infobae (2025). *Se desplomó 40% el uso del subte desde la pandemia: el impacto del teletrabajo y la suba del boleto.*
5. Observatorio del Derecho a la Ciudad (2025). *Informe sobre la evolución de pasajeros y la tarifa del subte de Buenos Aires (2015–2025).*
