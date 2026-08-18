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
