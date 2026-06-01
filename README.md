# credit-risk-scoring

# Credit Risk Scoring - Probability of Default (PD) Model

## Project Overview
Machine learning project focused on building a credit scoring model 
that estimates the Probability of Default (PD) for bank customers.
PD is a key parameter in credit risk management under Basel II/III frameworks,
used alongside LGD and EAD to calculate Expected Loss (EL = PD × LGD × EAD).

## Dataset
- Source: "Give Me Some Credit" (Kaggle)
- 104,805 customers, 11 input variables
- Target variable: SeriousDlqin2yrs (1 = default, 0 = no default)
- Class imbalance: 6.63% default rate (realistic for retail banking)

## Methodology
1. Exploratory Data Analysis (EDA)
2. Missing value imputation (median)
3. Train/test split (80/20)
4. Feature scaling (StandardScaler)
5. Logistic Regression - interpretable model preferred in banking
6. Handling class imbalance (class_weight='balanced')
7. Model evaluation and comparison

## Results

| Metric | Base Model | Balanced Model |
|--------|-----------|----------------|
| AUC-ROC | 0.7061 | 0.7974 |
| Recall (defaults) | 4% | 66% |
| Precision (defaults) | 53% | 16% |
| Accuracy | 94% | 76% |

## Key Findings
- Payment history (NumberOfTimes90DaysLate, NumberOfTime30-59DaysPastDueNotWorse) 
  is the strongest predictor of default
- Age and MonthlyIncome reduce default risk
- Balanced model detects 16x more defaults at the cost of lower precision
- In credit risk, high Recall is preferred to avoid undetected defaults

## Why Logistic Regression?
Logistic Regression is the industry standard for PD modeling in banks because:
- Fully interpretable - each variable has a clear coefficient
- Regulators (e.g. KNF) require banks to explain credit decisions
- Outputs true probabilities between 0 and 1

## Technologies
Python · Pandas · NumPy · Scikit-learn · Matplotlib · Seaborn
