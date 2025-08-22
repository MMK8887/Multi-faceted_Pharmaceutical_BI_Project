📊 Multi-Faceted Pharmaceutical Business Intelligence Project

This project demonstrates a comprehensive Business Intelligence (BI) pipeline for the pharmaceutical domain, integrating data analysis, machine learning, time-series forecasting, and natural language processing (NLP) to deliver actionable insights across clinical, commercial  areas.

🚀 Project Overview

The project leverages Python libraries such as Pandas, NumPy, Scikit-learn, and Statsmodels to analyze multiple datasets from an SQLite database (pharma.db).

It covers:

👥 Patient segmentation & heart disease risk prediction

💊 Drug sales forecasting

📑 Adverse Event (AE) classification with NLP

This multi-faceted approach helps pharmaceutical stakeholders in clinical decision-making, commercial planning, and pharmacovigilance.

📂 Datasets

Five datasets are used in this project:

patients – Demographic & health info for 5,000 patients (age, sex, BMI, conditions like diabetes, heart disease).

labs – Lab test results (LDL, HDL, HbA1c) with 10,000+ entries.

prescriptions – Drug prescriptions (drug name, dose, therapeutic area, class) with 7,500+ records.

sales_monthly – Monthly drug sales over time (165 entries).

ae_reports – 2,000 adverse event reports labeled as serious or nonserious.

✅ Initial checks confirmed no missing values or duplicates.

🛠️ Data Preparation & Feature Engineering

Lab data merge – Added latest LDL, HDL, HbA1c results per patient.

Prescription feature – Created a binary variable ever_statin to indicate statin history.

Categorical encoding – Converted sex (M/F) to numeric values.

Outlier handling – Used Z-score detection & capping at 1st/99th percentiles to mitigate extreme values.

❤️ Heart Disease Risk Prediction

A classification pipeline was built to predict heart disease (heart_disease column).

Challenge: Highly imbalanced target → addressed using SMOTE oversampling.

Models Trained:

Logistic Regression → Accuracy: 74%, Recall (positive class): 79%

Random Forest → Accuracy: 94%, Balanced F1-score: 0.58

Gradient Boosting → Accuracy: 85%, Recall (positive class): 52%

🔎 Explainability:
Used SHAP values → Key predictors: Age, Cholesterol, BMI.

📈 Drug Sales Forecasting

SARIMA models were applied on monthly sales data for drugs with ≥24 months history.

Seasonal order: (1,1,1,12) → capturing yearly trends.

Metrics used: RMSE, MAE, MAPE.

Results:

ATORVASTATIN → MAPE: 3.7% (high accuracy)

METFORMIN → MAPE: 5.6%

ALBURX → MAPE: 11.5%

📊 Insight: Reliable sales forecasts support inventory & demand planning.

🧠 NLP for Adverse Event Classification

Built an NLP pipeline to classify AE reports as serious or nonserious.

Preprocessing: Lowercasing, tokenization, lemmatization.

Vectorization: TF-IDF features.

Model: Logistic Regression (class weights balanced).

Performance:

Accuracy: 86%

F1 Score: 0.87

ROC-AUC: 0.88

⚕️ Insight: Automating AE triage helps prioritize urgent safety cases.

✅ Key Outcomes

Patient Risk Prediction – Identified critical risk factors for heart disease.

Sales Forecasting – Produced accurate demand predictions for key drugs.

Pharmacovigilance NLP –  AE classification model with strong performance.

🛠️ Tech Stack

Data Handling: Pandas, NumPy, SQLite

Modeling: Scikit-learn, Imbalanced-learn (SMOTE), Statsmodels (SARIMA)

Explainability: SHAP

Visualization: Matplotlib, Seaborn

NLP: TF-IDF, Logistic Regression

📌 Conclusion

This project demonstrates how integrating ML, time-series forecasting, and NLP into a unified BI pipeline can create a powerful decision-support system for pharmaceutical companies.

