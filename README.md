# Multi-faceted_Pharmaceutical_BI_Project
This project provides a multi-faceted data analysis pipeline for the pharmaceutical domain, integrating machine learning, time-series forecasting, and NLP to solve real-world business problems
# A Multi-faceted Data Analysis for Pharmaceutical Business Intelligence Project

## Project Overview

This project provides a comprehensive analysis of pharmaceutical data to drive business intelligence in three key areas: patient risk stratification, sales forecasting, and pharmacovigilance. By leveraging machine learning, time-series analysis, and natural language processing, this project delivers actionable insights to improve patient outcomes, optimize inventory, and enhance drug safety monitoring.

---

## Business Questions Addressed

1.  **Patient Risk:** What are the key risk factors for heart disease, and can we predict high-risk patients?
2.  **Sales:** What are the forecasted monthly sales for key drugs like Atorvastatin?
3.  **Safety:** Can we automate the classification of serious vs. non-serious adverse drug event reports?

---

## Data Sources

The analysis utilizes a relational database (`pharma.db`) containing five interconnected tables:
* `patients`: Demographic and basic clinical data.
* `labs`: Patient lab test results (e.g., LDL, HDL).
* `prescriptions`: Drug prescription records.
* `sales_monthly`: Monthly sales data for various drugs.
* `ae_reports`: Patient-reported adverse event text data.

---

## Methodology

The project follows a multi-pronged analytical approach:

1.  **Heart Disease Prediction:**
    * A consolidated feature set was created by merging patient, lab, and prescription data.
    * The dataset was preprocessed, scaled, and balanced using SMOTE.
    * Three models (Logistic Regression, Random Forest, Gradient Boosting) were trained and evaluated.
    * SHAP was used on the best model (Random Forest) to determine feature importance.

2.  **Sales Forecasting:**
    * A SARIMA (Seasonal Autoregressive Integrated Moving Average) model was implemented to forecast monthly unit sales for Atorvastatin.
    * The model was trained on historical data and validated against a test set to ensure accuracy (MAPE: 3.71%).

3.  **Adverse Event Classification:**
    * An NLP pipeline was built using `nltk` for text preprocessing (lemmatization).
    * `TfidfVectorizer` was used to convert text into a feature matrix.
    * A Logistic Regression model was trained to classify reports as "serious" or "non-serious".

---

## Key Insights & Results

* **Heart Disease Model:** The Random Forest classifier is highly effective. Key predictors are **LDL cholesterol, age, and systolic blood pressure**.
* **Sales Forecast:** The SARIMA model provides reliable 12-month sales forecasts, crucial for supply chain and financial planning.
* **AE NLP Model:** The model achieved a **ROC-AUC of 0.88**, demonstrating strong potential for automating pharmacovigilance tasks.

---

## Technologies & Libraries

* **Data Handling:** Pandas, SQLite
* **Machine Learning:** Scikit-learn, Imbalanced-learn
* **Time Series:** Statsmodels
* **Model Interpretation:** SHAP
* **NLP:** NLTK
* **Visualization:** Matplotlib, Seaborn

---

## Setup & Execution

1.  **Clone the repository.**
2.  **Ensure you have Python 3.8+ installed.**
3.  **Install the required libraries:**
    ```bash
    pip install pandas numpy scikit-learn statsmodels shap nltk matplotlib seaborn notebook
    ```
4.  **Download NLTK data:**
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('wordnet')
    ```
5.  **Place the `pharma.db` database in the `/db` directory.**
6.  **Run the `final.ipynb` Jupyter Notebook to replicate the analysis.**
