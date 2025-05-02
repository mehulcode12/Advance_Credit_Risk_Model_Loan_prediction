Advance Credit Risk Model for Loan Prediction

🌐 Live Streamlit App

🚀 Project Description

In the world of lending, accurately assessing the risk of a loan applicant defaulting is crucial to the sustainability and profitability of financial institutions. This project builds an end-to-end machine learning pipeline that helps a lending company predict whether a loan applicant will default, using advanced data preprocessing, feature engineering, and model evaluation techniques. The solution is also deployed as a web-based Streamlit app, allowing business stakeholders to interact with the model in real time.

📊 Problem Statement

Credit risk prediction involves classifying borrowers into high risk (default) and low risk (non-default) categories. Due to class imbalance and a need for interpretability, the task demands not just a high-performance model, but also one that is explainable, robust, and actionable.

👩‍💼 Business Impact

Mitigates Financial Risk: Helps reduce bad loans.

Enables Proactive Decision Making: High-risk customers can be flagged early.

Improves Operational Efficiency: Automated scoring model saves time in underwriting.

Regulatory Compliance: Ensures fairness and transparency with explainable models.

🔧 Technical Details

1. 🔎 Data Exploration and Cleaning

Missing Value Treatment: Used domain knowledge to impute or remove irrelevant/missing features.

Anomaly Detection: Boxplots revealed that in some rows, processing_fee > loan_amount. These were treated.

Data Leakage: Removed columns that leak future info (e.g., disbursal dates).

2. 📊 Exploratory Data Analysis (EDA)

Default vs. Age: Younger applicants had a higher tendency to default.

Predictor Insights:

Higher values in loan_tenure_months, delinquent_months, total_dpd, and credit_utilization correlated with defaults.

Loan to Income Ratio (LTI): Engineered feature showing higher LTI leads to higher risk.

3. ⚖️ Feature Engineering

Created:

loan_to_income = loan_amount / income

delinquency_ratio

avg_dpd_per_delinquency

Removed multicollinear features using VIF

Categorical variables were encoded using Weight of Evidence (WoE) and evaluated using Information Value (IV)

4. 🧶 Model Building

Algorithms tried:

Logistic Regression (preferred for explainability)

Random Forest

XGBoost (high-performing, not chosen for business due to explainability concerns)

Class Imbalance Handling:

Used SMOTE-Tomek resampling strategy

Model Metrics:

Logistic Regression: Recall = 0.95, Accuracy = 0.93

XGBoost: Recall = 0.99, Accuracy = 0.92

High AUC = 0.983, Gini Coefficient = 0.966

5. 📊 Evaluation Metrics

Confusion Matrix, ROC-AUC, Precision-Recall Curve

KS Statistic

Maximum KS value = 85.98% at Decile 8

“KS > 40 in top 3 deciles” indicates a strong model

Decile Table: Top deciles had highest event rates (defaults), showing good rank ordering.

6. 🌐 Deployment

Built and deployed a Streamlit app that takes user input and predicts default risk.

Files:

main.py — handles Streamlit frontend

prediction_helper.py — processes data and loads trained model

🌟 Performance Summary

Metric

Value

Accuracy

0.93

Recall (Positive)

0.95

AUC

0.983

Gini Coefficient

0.966

KS Statistic

85.98%

📷 Screenshots

KS Statistic Curve



Streamlit App



📁 Repository Structure

.
├── datasets/                # Raw and processed datasets
├── images/                  # Visual assets like graphs, screenshots
├── main.py                  # Streamlit application
├── prediction_helper.py     # Helper functions and model loading
├── Untitled.ipynb           # Exploratory notebook with model development
├── requirements.txt         # Environment dependencies
└── README.md                # Project documentation

🎯 Getting Started

# 1. Clone the repo
$ git clone https://github.com/mehulcode12/Advance_Credit_Risk_Model_Loan_prediction
$ cd Advance_Credit_Risk_Model_Loan_prediction

# 2. Install dependencies
$ pip install -r requirements.txt

# 3. Run the app
$ streamlit run main.py

🙌 Acknowledgements

This project was completed as part of the Codebasics Data Science Bootcamp.

Special thanks to mentors and the open-source community for libraries and frameworks.

🌍 Connect With Me

LinkedIn

GitHub

"A good model not only predicts well but also builds trust through explainability."

