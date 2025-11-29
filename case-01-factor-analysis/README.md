# Case Description and Key Findings

---

## 1. Business Context

**Client and problem**

TechnoServe Solutions is a B2B technology provider that gathers feedback from enterprise clients through a structured **customer satisfaction survey**.  
The company wants to understand the **latent dimensions** that drive customer experience and how these hidden factors influence **satisfaction, loyalty, and renewal decisions**.

The main objective of this case is to apply **factor analysis** to the 23 satisfaction items and identify the **core themes** that shape how clients perceive the service.

**Strategic importance of the analysis**

- Allows the company to understand **what truly matters** to clients beneath surface-level survey responses.  
- Reduces a long list of 23 items into a **compact, actionable set of customer experience drivers**.  
- Provides a statistical foundation for improving **renewal likelihood**, **NPS**, and **customer retention**.  
- Enables the company to build **focused improvement plans** aligned with the strongest predictors of satisfaction.  
- Supports the creation of **factor-level dashboards** for ongoing monitoring and segmentation.

---

## 2. Methodology

**Multivariate method applied**

- **Maximum Likelihood Factor Analysis (ML)**
  - Used to identify the underlying latent structure.
  - Applied to the **correlation matrix** of the 23 satisfaction items.

- **Promax Rotation (oblique)**
  - Selected because satisfaction dimensions are conceptually and empirically correlated.
  - Produces more interpretable, business-aligned factor groupings.

**Justification of the choice**

- The business question is about **dimensionality reduction and uncovering latent structures**, not prediction → factor analysis is the correct multivariate tool.  
- Satisfaction items naturally form conceptual domains (technical, delivery, support, etc.), making factor analysis a strong fit.  
- The dataset shows **high factorability**:
  - **KMO = 0.959** (excellent)  
  - **Bartlett’s test** p-value < 0.0001 (significant)  
- Oblique rotation is warranted:
  - The estimated factor correlation matrix shows relationships up to **|0.62|**, confirming that factors are not independent.  
- A **five-factor solution** satisfies both the Kaiser criterion (eigenvalue > 1) and interpretability requirements.

**Tools and libraries used**

- **Python** (Jupyter Notebook: `factor_analysis.ipynb`)
- **Libraries**:
  - `pandas`, `numpy` for preprocessing and data handling  
  - `matplotlib`, `seaborn` for visualization  
  - `factor_analyzer` for KMO, Bartlett, ML extraction and rotations  
  - `scikit-learn` for imputation and regression  
  - `yellowbrick` (optional) for visual diagnostics  

---

## 3. Data

**Dataset description**

- **3,400 survey responses** from enterprise customers.  
- **23 satisfaction items** on a 1–7 scale covering technical quality, relationship, delivery, cost/value, and support.  
- **Outcome variables** such as:
  - `overall_satisfaction` (1–7)  
  - `nps_score` (0–10)  
  - `renewal_likelihood` (1–5)  
  - `revenue_growth_pct`  
  - `referrals_generated`  

**Key variables**

Examples of the satisfaction items analyzed:

- **Technical Excellence:**  
  `technical_expertise`, `problem_solving`, `innovation_solutions`,  
  `technical_documentation`, `system_integration`.  

- **Relationship Management:**  
  `account_manager_responsive`, `executive_access`,  
  `trust_reliability`, `communication_clarity`.  

- **Project Delivery:**  
  `project_management`, `timeline_adherence`,  
  `quality_deliverables`, `budget_control`.  

- **Value & Cost:**  
  `value_for_money`, `competitive_pricing`,  
  `billing_accuracy`, `roi_demonstration`.  

- **Support & Enablement:**  
  `support_responsiveness`, `training_quality`, `documentation_help`.  

The dataset contains **low missingness (<1%)**, handled with mean imputation using `SimpleImputer`.

**Link to data dictionary**
[Data Dictionary](data/DATA_DICTIONARY.md) 


---

## 4. Main Findings

### 4.1 Key findings (3–6 bullet points)

- Factorability tests confirm the suitability of factor analysis:  
  - **KMO = 0.959** (excellent)  
  - **Bartlett’s χ² = 33,163**, p < 0.0001  

- A **five-factor solution** balances statistical criteria and business interpretability, explaining **≈60% of total variance**.

- The five latent factors identified are:  
  1. **Technical Excellence** – expertise, innovation, integration.  
  2. **Value & Cost** – transparency, ROI, pricing fairness.  
  3. **Relationship Management** – trust, responsiveness, communication.  
  4. **Project Delivery** – timeline, budget, quality of deliverables.  
  5. **Support & Enablement** – support speed, training, documentation.

- **Project Delivery** and **Technical Excellence** are the **strongest drivers** of overall satisfaction and renewal intent (correlations up to **0.65**).

- **Relationship Management** contributes significantly to **NPS** and customer loyalty.

- Factor scores enable simple but meaningful segmentation (3 clusters):  
  - High-satisfaction, retained customers  
  - Neutral cluster  
  - At-risk customers with consistently low factor scores  

### 4.2 Highlight visualization

![Correlation Factor vs. Outcome Graph](.\image\factors_vs_outcomes.png)


### 4.3 Model performance metrics

- **Variance explained (Promax, 5 factors): ~60.4%**  
- **Factor 1 eigenvalue:** 8.66  
- **Factor correlation matrix:** strongest correlation ≈ |0.62|  
- **Regression (renewal_likelihood ~ factors):**  
  - R² train ≈ **0.39**  
  - R² test ≈ **0.38**  

These metrics confirm that the factor model is statistically stable and business-relevant.

---

## 5. Business Recommendations

### 5.1 Three actionable recommendations

1. **Prioritize improvements in Project Delivery**  
   - Strengthen project management, timeline adherence, and quality assurance.  
   - This factor has the strongest impact on both renewal and satisfaction.

2. **Reinforce Technical Excellence as a differentiator**  
   - Invest in documentation quality, integration stability, and advanced problem-solving capabilities.  
   - Drives confidence and long-term partnership perceptions.

3. **Operationalize factor-level monitoring**  
   - Build dashboards tracking the five latent dimensions over time.  
   - Use factor scores to identify at-risk customers and trigger proactive interventions.

### 5.2 Expected impact

- **Higher renewal rates** by addressing the main satisfaction drivers.  
- **Improved NPS** through stronger relationships and technical communication.  
- **Better resource allocation** by focusing on the factors with the highest predictive power.

### 5.3 Next steps

- Validate the factor structure with data from other quarters (cross-year stability).  
- Integrate factor scores into CRM systems for account-level monitoring.  
- Combine factors with transactional data for a full customer experience model.

---
