# 📊 Customer Churn Prediction & Retention Risk Analysis

An end-to-end machine learning project for identifying telecom customers at higher risk of churn and understanding the factors associated with customer retention.

## 📌 Project Overview

Customer churn is an important business problem for subscription-based companies. This project analyzes customer behavior, identifies major churn patterns, compares classification models, and develops a model that can support proactive customer retention efforts.

The project covers:

- Data cleaning
- Exploratory Data Analysis (EDA)
- Feature preparation
- Categorical encoding
- Numerical feature scaling
- Classification modeling
- Model comparison
- Hyperparameter tuning
- Threshold analysis
- 5-fold cross-validation
- Feature importance
- Business recommendations

## 🎯 Objective

Build a machine learning classification model capable of identifying customers at higher risk of churn while understanding the customer characteristics most strongly associated with churn.

## 📊 Dataset

The project uses a telecom customer churn dataset containing **7,043 customer records**.

The target variable is:

- `Churn` — whether the customer discontinued the service

Important customer attributes include:

- Contract
- Tenure
- MonthlyCharges
- TotalCharges
- InternetService
- OnlineSecurity
- TechSupport
- PaymentMethod
- PaperlessBilling
- Partner
- Dependents

## 🧹 Data Cleaning

`TotalCharges` was stored as a text/object variable and contained blank values.

The blanks were converted to numeric values and handled as `0.0`, consistent with the observation that these records had zero tenure.

The `customerID` column was removed before model development because it is an identifier rather than a predictive customer characteristic.


## 🔍 Exploratory Data Analysis

Several customer characteristics were analyzed to understand observed churn patterns.

### Key observations

- **Contract type** showed a strong relationship with churn, with month-to-month customers representing an important high-risk segment.
- **Tenure** was an important predictive feature, with customers in the early stages of their relationship showing higher observed churn.
- **Internet service** was associated with different churn patterns across customer segments.
- **Internet service + contract combinations** were analyzed to identify higher-risk customer groups.
- **Monthly charges** were compared across different internet service categories.
- Additional churn rates were analyzed across services such as:
  - OnlineSecurity
  - OnlineBackup
  - DeviceProtection
  - TechSupport
  - StreamingTV
  - StreamingMovies
  - PaymentMethod

### Important segment finding

The combination of **Fiber Optic internet service + Month-to-Month contract** showed an observed churn rate of **54.61%** in the analysis.

> These findings represent observed/predictive associations and should not be interpreted as causal relationships.
