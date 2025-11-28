# mi-portfolio-ma2003b

This portfolio showcases three end-to-end multivariate analytics projects completed as part of an applied data science program.
It includes advanced statistical techniques such as Factor Analysis, Discriminant Analysis, and Cluster Analysis, demonstrating the ability to solve real business problems using multivariate methods.

Across the three cases, this portfolio highlights the process of:

- Understanding business challenges
- Preparing and validating datasets
- Applying the appropriate multivariate technique
- Interpreting insights
- Transforming statistical findings into actionable business recommendations

Each case includes full documentation, reproducible notebooks, and executive-level summaries. The work is implemented in Python, using standard machine learning and statistical libraries such as pandas, numpy, scikit-learn, factor_analyzer, scipy, and matplotlib.

• Badges de GitHub (status, language, license)

## Información del equipo 
Armando Atanasio Navarrete Yepez - 
Helena Eridani Escandon Lopez - 
Ofelia Gabriela Góngora Méndez - A01666131

## Tabla de contenidos navegable 
- **Información del equipo:** [Información del equipo](#información-del-equipo)
- **Resumen de casos de estudio:** [Resumen de casos de estudio](#resumen-de-casos-de-estudio)
- **Instrucciones de reproducibilidad:** [Instrucciones de reproducibilidad](#instrucciones-de-reproducibilidad)
- **Estructura del repositorio:** [Estructura del repositorio](#estructura-del-repositorio)
- **Casos de estudio:**
	- [Caso 01 — Factor Analysis](case-01-factor-analysis/README.md)
	- [Caso 02 — Discriminant Analysis](case-02-discriminant-analysis/README.md)
	- [Caso 03 — Cluster Analysis](case-03-cluster-analysis/README.md)

## Resumen de casos de estudio
| Caso | Método | Pregunta de negocio | Hallazgo clave (1 oración) | Link al caso |
|---|---|---|---|---|
| TechnoServe Customer Satisfaction | Factor Analysis | What latent dimensions drive customer satisfaction and renewal? | 5 latent factors explain ~60% of variance; Technical Excellence is the strongest predictor. | [Caso 01 — Factor Analysis](case-01-factor-analysis/README.md) |
|LendSmart Credit Risk | Discriminant Analysis | How can we classify loan applicants into risk categories? | Perfect separation; LDA achieves AUC = 1.0, credit score is the top predictor. | [Caso 02 — Discriminant Analysis](case-02-discriminant-analysis/README.md) |
| MegaMart Customer Segmentation | Cluster Analysis | What natural customer segments exist in the database? | 4 clusters found; “Loyal Customers” represent 18% but drive 45% of revenue. | [Caso 03 — Cluster Analysis](case-03-cluster-analysis/README.md) |


## Instrucciones de reproducibilidad 

Estas instrucciones permiten reproducir los análisis y ejecutar los notebooks en un entorno Windows (PowerShell). Las rutas son relativas a la raíz del repositorio.

- **Requisitos mínimos**:
	- Python 3.10 o 3.11 (se recomienda usar la misma versión durante la reproducción).
	- Espacio en disco suficiente para los datos y notebooks.

- **Paquetes principales** (versión orientativa):
	- `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `jupyterlab` o `notebook`, `factor_analyzer`, `scipy`

- **Pasos para preparar el entorno (PowerShell)**:
	1. Crear un entorno virtual en la raíz del proyecto:

		 ```powershell
		 python -m venv .venv
		 ```

	2. Activar el entorno virtual (PowerShell):

		 ```powershell
		 .\.venv\Scripts\Activate.ps1
		 ```

	3. Actualizar pip e instalar dependencias (instalación mínima):

		 ```powershell
		 python -m pip install --upgrade pip
		 pip install pandas numpy scikit-learn matplotlib seaborn jupyterlab factor_analyzer scipy
		 ```

	4. (Opcional) Si prefieres instalar desde un archivo `requirements.txt`, crea uno y ejecuta:

		 ```powershell
		 pip install -r requirements.txt
		 ```

- **Ejecutar los notebooks (interactivo)**:
	- Iniciar Jupyter Lab/Notebook desde la raíz del repositorio:

		```powershell
		jupyter lab
		# o
		jupyter notebook
		```

	- Abrir el notebook deseado en la interfaz y ejecutar las celdas en orden (recomiendo ejecutar las primeras celdas de setup antes que las de análisis).

- **Ejecutar un notebook de forma no interactiva (reproducible)**:
	- Para ejecutar un notebook y sobrescribirlo con las salidas ejecutadas:

		```powershell
		pip install nbconvert
		jupyter nbconvert --to notebook --execute case-02-discriminant-analysis/notebooks/discriminant_analysis.ipynb --inplace
		```

- **Rutas de datos**:
	- Los datos para cada caso están en las carpetas `case-0X-.../data/`. Por ejemplo, el notebook de discriminant analysis carga `../data/credit_risk_data-1.csv` (ruta relativa desde `case-02-discriminant-analysis/notebooks`).

- **Notas y recomendaciones**:
	- Si usas PowerShell y recibes un error de ejecución al activar el venv, ejecuta `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` en una sesión con privilegios adecuados.

## Estructura del repositorio 
mi-portfolio-ma2003b/
│
├── README.md # Descripción general del portfolio
├── LICENSE # Licencia MIT o similar
├── .gitignore # Configuración para Python
├── requirements.txt # Dependencias del proyecto
│
├── case-01-factor-analysis/
│ ├── README.md # Descripción del caso y hallazgos clave
│ ├── data/
│ │ ├── customer_satisfaction_data.csv
│ │ └── DATA_DICTIONARY.md
│ ├── notebooks/
│ │ └── factor_analysis.ipynb # Notebook mejorado
│ ├── reports/
│ │ ├── executive_summary.pdf
│ │ └── technical_report.pdf
│ ├── src/ # Scripts de Python reutilizables
(opcional)
│ │ └── utils.py
│ └── visualizations/
│ ├── correlation_heatmap.png
│ ├── scree_plot.png
│ └── factor_loadings.png
│
├── case-02-discriminant-analysis/
│ ├── README.md
│ ├── data/
│ ├── notebooks/
│ ├── reports/
│ └── visualizations/
│
├── case-03-cluster-analysis/
│ ├── README.md
│ ├── data/
│ ├── notebooks/
│ ├── reports/
│ └── visualizations/
│
├── portfolio-summary/
│ ├── PORTFOLIO_OVERVIEW.md # Resumen integrador
│ ├── LESSONS_LEARNED.md # Reflexiones críticas
│ └── METHODOLOGY_COMPARISON.md # Comparación de métodos
│
└── presentation/
└── final_portfolio_presentation.pdf

