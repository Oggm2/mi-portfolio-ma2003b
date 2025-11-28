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

• GitHub Badges (status, language, license)

## Team Information
Armando Atanasio Navarrete Yepez - A01658529
Helena Eridani Escandon Lopez - A01659511
Ofelia Gabriela Góngora Méndez - A01666131

## Table of Contents
- **Team Information:** [Team Information](#team-information)
- **Case Study Summary:** [Case Study Summary](#case-study-summary)
- **Reproducibility Instructions:** [Reproducibility Instructions](#reproducibility-instructions)
- **Repository Structure:** [Repository Structure](#repository-structure)
- **Case Studies:**
	- [Case 01 — Factor Analysis](case-01-factor-analysis/README.md)
	- [Case 02 — Discriminant Analysis](case-02-discriminant-analysis/README.md)
	- [Case 03 — Cluster Analysis](case-03-cluster-analysis/README.md)

## Case Study Summary
| Case | Method | Business Question | Key Finding (1 sentence) | Link to Case |
|---|---|---|---|---|
| TechnoServe Customer Satisfaction | Factor Analysis | What latent dimensions drive customer satisfaction and renewal? | 5 latent factors explain ~60% of variance; Technical Excellence is the strongest predictor. | [Case 01 — Factor Analysis](case-01-factor-analysis/README.md) |
|LendSmart Credit Risk | Discriminant Analysis | How can we classify loan applicants into risk categories? | Perfect separation; LDA achieves AUC = 1.0, credit score is the top predictor. | [Case 02 — Discriminant Analysis](case-02-discriminant-analysis/README.md) |
| MegaMart Customer Segmentation | Cluster Analysis | What natural customer segments exist in the database? | 4 clusters found; "Loyal Customers" represent 18% but drive 45% of revenue. | [Case 03 — Cluster Analysis](case-03-cluster-analysis/README.md) |

Fill in the _Business Question_ and _Key Finding_ columns with the corresponding content from each case.


## Reproducibility Instructions

These instructions allow you to reproduce the analyses and run the notebooks in a Windows (PowerShell) environment. All paths are relative to the repository root.

- **Minimum Requirements**:
	- Python 3.10 or 3.11 (recommended to use the same version throughout reproduction).
	- Sufficient disk space for data and notebooks.

- **Main Packages** (indicative versions):
	- `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `jupyterlab` or `notebook`, `factor_analyzer`, `scipy`

- **Steps to Prepare the Environment (PowerShell)**:
	1. Create a virtual environment at the root of the project:

		 ```powershell
		 python -m venv .venv
		 ```

	2. Activate the virtual environment (PowerShell):

		 ```powershell
		 .\.venv\Scripts\Activate.ps1
		 ```

	3. Update pip and install dependencies (minimal installation):

		 ```powershell
		 python -m pip install --upgrade pip
		 pip install pandas numpy scikit-learn matplotlib seaborn jupyterlab factor_analyzer scipy
		 ```

	4. (Optional) If you prefer to install from a `requirements.txt` file, create one and run:

		 ```powershell
		 pip install -r requirements.txt
		 ```

- **Run Notebooks (Interactive)**:
	- Start Jupyter Lab/Notebook from the repository root:

		```powershell
		jupyter lab
		# or
		jupyter notebook
		```

	- Open the desired notebook in the interface and run cells in order (recommended to run setup cells before analysis cells).

- **Run a Notebook Non-Interactively (Reproducible)**:
	- To execute a notebook and overwrite it with executed outputs:

		```powershell
		pip install nbconvert
		jupyter nbconvert --to notebook --execute case-02-discriminant-analysis/notebooks/discriminant_analysis.ipynb --inplace
		```

- **Data Paths**:
	- Data for each case is in the `case-0X-.../data/` folders. For example, the discriminant analysis notebook loads `../data/credit_risk_data-1.csv` (relative path from `case-02-discriminant-analysis/notebooks`).

- **Notes and Recommendations**:
	- If you use PowerShell and receive an execution error when activating the venv, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` in a session with appropriate privileges.

## Repository Structure 
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

