# Bankruptcy Prediction Project

## Overview
Predict company bankruptcy using financial indicators, ratios, and per-share metrics. The dataset is highly imbalanced, with very few bankrupt companies.

---

## Features
- Financial ratios (ROA, margins, growth rates, asset turnover, etc.)
- Per-share metrics (EPS, cash flow per share, revenue per share)
- Other financial indicators (debt ratio, current ratio, liquidity measures)

---

## Preprocessing
1. **Outlier Treatment** – Capped using IQR (excluding target column `Bankrupt`).
2. **Scaling** – StandardScaler for Random Forest; not applied for Logistic Regression when maximizing recall.
3. **Class Balancing** – SMOTE applied for Random Forest; not applied for Logistic Regression in high-recall setup.
4. **Train/Test Split** – 80% train, 20% test, stratified on target variable.

---

## Models
- **Random Forest Classifier**
- **Logistic Regression (L1 penalty)**
- Hyperparameter tuning with `RandomizedSearchCV` (ROC-AUC scoring).

---

## Evaluation Metrics
- **ROC-AUC** – ranking ability
- **Recall** – % of bankrupt companies detected
- **Precision** – % of predicted bankrupt companies correct
- **F1-Score** – harmonic mean of precision & recall
- **Accuracy** – overall correctness
- **Confusion Matrix** – TP, FP, TN, FN

---

## Results

| Goal | Model | Preprocessing | ROC-AUC | Recall | F1-Score |
|------|-------|---------------|---------|--------|----------|
| Balanced prediction | Random Forest | No Outliers + Scaling + SMOTE | 0.82 | 0.68 | 0.48 |
| Catch all bankrupt | Logistic Regression | No Outliers + No Scaling + No SMOTE | 0.88 | 0.89 | 0.31 |

**Observation:**  
- Random Forest is best for general balanced prediction.  
- Logistic Regression is best for early-warning detection (high recall).

---

## Conclusion

- Preprocessing choices (outlier removal, scaling, SMOTE) significantly affect performance.
- Random Forest is recommended for balanced predictions.
- Logistic Regression is recommended when catching all bankrupt companies is critical.

