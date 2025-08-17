# Multi-faceted_Pharmaceutical_BI_Project
This project provides a multi-faceted data analysis pipeline for the pharmaceutical domain, integrating machine learning, time-series forecasting, and NLP to solve real-world business problems
# 📊 Multi-faceted Pharmaceutical Business Intelligence Project

## Project Overview
This project provides a comprehensive data analysis pipeline for the pharmaceutical domain, addressing **patient risk stratification, sales forecasting, and pharmacovigilance**.
By leveraging **machine learning, time-series forecasting, and natural language processing (NLP)**, the project delivers actionable insights to:

- Improve **patient outcomes**
- Optimize **sales and inventory planning**
- Enhance **drug safety monitoring**

---

## Business Questions Addressed
1. **Patient Risk:** What are the key risk factors for heart disease, and can we predict high-risk patients?
2. **Sales Forecasting:** What are the forecasted monthly sales for key drugs like *Atorvastatin*?
3. **Drug Safety:** Can adverse drug event (AE) reports be automatically classified into *serious* vs. *non-serious*?

---

## Data Sources
The analysis uses a relational database (`pharma.db`) containing five interconnected tables:

- **patients** → demographic & clinical data
- **labs** → lab test results (e.g., LDL, HDL)
- **prescriptions** → drug prescription records
- **sales_monthly** → monthly sales data for drugs
- **ae_reports** → patient-reported adverse event text data

---

## Methodology

### 1. Heart Disease Prediction 🩺
- Combined patient, lab, and prescription data into a feature set
- Preprocessed & balanced data using **SMOTE**
- Trained models: **Logistic Regression, Random Forest, Gradient Boosting**
- **Random Forest** performed best
- Applied **SHAP** to identify top predictors

### 2. Sales Forecasting 📈
- Built **SARIMA (Seasonal ARIMA)** model for Atorvastatin sales
- Achieved **MAPE = 3.71%**
- Provided **12-month forecasts with seasonal peaks** for inventory planning

### 3. Adverse Event Classification ⚕️
- Implemented **NLP pipeline: TF-IDF + Logistic Regression**
- Classified AE reports into *serious* / *non-serious*
- Performance: **ROC-AUC = 0.88, F1-score = 0.87**

---

## Key Insights & Results
- **Heart Disease Risk Factors (via SHAP):**
  - ↑ LDL cholesterol, ↑ age, ↑ systolic BP, ↑ cholesterol → higher risk
  - ↑ HDL and prior statin use → protective factors

- **Sales:** Reliable SARIMA forecasts enable proactive supply chain planning

- **Pharmacovigilance:** Automated AE classification accelerates safety reporting

---

## Technologies & Libraries
- **Data Handling:** Pandas, SQLite
- **ML Models:** Scikit-learn, Imbalanced-learn
- **Time Series:** Statsmodels (SARIMA)
- **NLP:** NLTK, TF-IDF
- **Model Explainability:** SHAP
- **Visualization:** Matplotlib, Seaborn

---

## Setup & Execution

1. Clone the repository.
2. Ensure you have **Python 3.8+** installed.
3. Install the required libraries:
   ```bash
   pip install pandas numpy scikit-learn statsmodels shap nltk matplotlib seaborn notebook
   ```
4. Download NLTK data:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('wordnet')
   ```
5. Place the **`pharma.db`** database in the `/db` directory.
6. Run the **`final.ipynb`** Jupyter Notebook to replicate the analysis.
