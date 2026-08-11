## Project Highlights

- Analyzed **7,043 customer records** to identify major churn patterns.
- Compared **5 classification approaches** including Logistic Regression, Decision Tree, and Random Forest models.
- Used **GridSearchCV and 5-fold cross-validation** for model tuning.
- Final Random Forest achieved **0.843 ROC-AUC** on the held-out test set.
- Achieved **76.7% recall** for the churn class.
- Used **permutation importance** to interpret the final model.

# Customer Churn Prediction & Retention Risk Analysis

An end-to-end machine learning project that analyzes customer churn patterns and develops a predictive model to identify customers at higher risk of churn.

## Business Problem

Customer churn is an important challenge for subscription-based businesses. The objective of this project is to identify factors associated with churn, build predictive classification models, and identify customer segments that may require retention attention.

## Dataset

The dataset contains 7,043 customer records with demographic, service, contract, payment, and billing information.

The target variable is `Churn`.

- No: 5,174 customers
- Yes: 1,869 customers

## Exploratory Data Analysis

Key findings included:

- Month-to-month customers showed substantially higher churn than customers on one- and two-year contracts.
- Shorter-tenure customers showed higher churn.
- Fiber optic customers had 41.89% observed churn.
- Fiber optic + month-to-month customers had 54.61% observed churn.
- Electronic-check customers had 45.29% observed churn.
- Customers without OnlineSecurity or TechSupport showed higher observed churn.

## Data Preparation

- Converted `TotalCharges` to numeric.
- Handled blank values.
- Removed `customerID` from modeling.
- Used an 80/20 stratified train-test split.
- Standardized numerical variables.
- One-hot encoded categorical variables.
- Used a Scikit-learn preprocessing pipeline.

## Models Evaluated

- Logistic Regression
- Decision Tree
- Tuned Decision Tree
- Random Forest
- Tuned Random Forest

## Model Performance

| Model | Accuracy | Churn Recall | Churn F1 | ROC-AUC |
|---|---:|---:|---:|---:|
| Logistic Regression | 81% | 55.9% | 60.4% | 0.8420 |
| Decision Tree | 72% | 49.2% | 48.0% | 0.6477 |
| Tuned Decision Tree | 80% | 56.7% | 60.0% | 0.8275 |
| Random Forest | 79% | 48.7% | 55.0% | 0.8185 |
| Tuned Random Forest | 76% | 76.7% | 62.9% | 0.8431 |

## Final Model

The final candidate model was a tuned Random Forest with:

- `n_estimators = 300`
- `class_weight = balanced`
- `max_features = sqrt`
- `min_samples_leaf = 10`
- `max_depth = None`

### Performance

- **Test ROC-AUC:** 0.8431
- **5-fold CV ROC-AUC:** 0.8490 ± 0.0129
- **Churn Recall:** 76.7%
- **Churn F1:** 62.9%

The Random Forest was selected because the project prioritizes identifying customers at risk of churn. It achieved substantially higher churn recall than the Logistic Regression baseline while maintaining a similar ROC-AUC.

## Model Interpretation

Permutation importance identified the following as the strongest original features:

1. Contract
2. Tenure
3. InternetService
4. TotalCharges
5. OnlineSecurity
6. TechSupport
7. PaymentMethod

Feature importance represents predictive association and should not be interpreted as causal evidence.

## Business Recommendations

1. **Prioritize month-to-month customers** for retention efforts.
2. **Focus on early-tenure customers** through stronger onboarding and engagement.
3. **Investigate the fiber optic + month-to-month segment**, which showed 54.61% observed churn.
4. **Investigate customers without OnlineSecurity or TechSupport** as potentially higher-risk segments.
5. **Investigate electronic-check customers** while controlling for other customer characteristics.

## Limitations

- Findings represent predictive associations, not causal relationships.
- Production performance may differ from the held-out test results.
- Retention strategies should be validated through controlled business experiments.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
