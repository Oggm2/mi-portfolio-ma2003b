# Descripción del caso y hallazgos clave

# LendSmart Credit Risk Analysis – Final Report

## 1. Business Context

### Client and Problem Description
LendSmart is a FinTech company specializing in personal and small business loans. The company is currently facing a **28% loan default rate**, which significantly threatens profitability and long-term sustainability. When a high-risk applicant is mistakenly approved, LendSmart suffers substantial financial losses.

To address this issue, LendSmart requested the development of a **statistical classification model** capable of identifying high-risk loan applicants prior to approval. This model will support the Credit Department by flagging risky clients for further review or rejection.

### Strategic Importance
Reducing the default rate is strategically critical for LendSmart because it:
- **Protects revenue** by preventing financial losses.
- **Improves portfolio quality** and financial stability.
- **Accelerates approvals** for low-risk applicants.
- Supports a **data-driven credit risk strategy** that can scale with the company.

---

## 2. Methodology

### Multivariate Method Applied
Two multivariate supervised learning methods were implemented:
- **Linear Discriminant Analysis (LDA)**
- **Quadratic Discriminant Analysis (QDA)**

Both techniques classify applicants as **default** or **non-default** based on multiple financial and demographic predictors.

### Justification for the Chosen Methods
- The dataset exhibits **perfect separability** between defaulting and non-defaulting applicants.
- LDA provides a simple, interpretable model that suits datasets with similar covariance structures.
- QDA allows more flexible classification when covariance differs between groups.
- Both methods are commonly used in credit scoring, making them appropriate for this analysis.

LDA is recommended due to its interpretability, stability, and equivalent performance to QDA on this dataset.

### Tools and Libraries Used
- **Python**
- **NumPy**, **Pandas**
- **Matplotlib**, **Seaborn**
- **Scikit-Learn** (LDA, QDA, model evaluation)
- **pypandoc** for documentation generation

---

## 3. Data

### Dataset Description
The dataset contains historical loan application information, including:
- Financial attributes (income, debt ratio, credit score)
- Demographic variables (education, employment status)
- Behavioral indicators (savings, assets)
- Target variable: `default` (1 = default, 0 = no default)

The dataset demonstrated **perfect class separability**, which is unusual in real-world credit risk data.

### Key Variables
- `credit_score`
- `debt_to_income_ratio`
- `employment_status`
- `education_level`
- `assets_owned`
- `savings`
- `default`

### Link to Data Dictionary
[Data Dictionary](data/DATA_DICTIONARY.md)

---

## 4. Main Findings

### Key Insights
- The dataset shows **perfect separability** between clients who default and those who do not.
- **Credit score** is the strongest predictor of repayment behavior.
- Defaulting clients tend to have:
  - Low credit scores  
  - High debt-to-income ratios  
  - Irregular employment  
  - Lower education levels  
  - Few assets and limited savings  
- Both LDA and QDA achieved **AUC = 1.0** and **Recall = 1.0**, meaning perfect classification.
- The perfect metrics suggest the data may be synthetic or overly clean.

### Model Performance Metrics

#### LDA Performance
- Accuracy: **1.0**
- Recall: **1.0**
- AUC: **1.0**
- False Positives: **0**
- False Negatives: **0**

#### QDA Performance
- Accuracy: **1.0**
- Recall: **1.0**
- AUC: **1.0**

---

## 5. Business Recommendations

### Actionable Recommendations
1. **Adopt the LDA model** as the primary risk-assessment tool.  
2. **Validate the model with new, real-world data** to test robustness.  
3. **Integrate the model into the credit approval workflow** for automated risk flags.  

### Expected Impact
- **Major reduction in default rate**, preventing significant financial losses.
- **Improved operational efficiency**, with faster approvals for low-risk clients.
- **Stronger financial stability**, strengthening the long-term lending strategy.

### Next Steps
- Gather new unclean real-world loan data for validation.
- Reassess model performance and compare LDA vs. QDA if needed.
- Deploy the final model through an automated scoring system.
- Train the credit team on model interpretation and decision thresholds.

