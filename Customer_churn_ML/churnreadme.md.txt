# Model Performance Summary (Verified)

## Decision Tree
- **Gini:** 88% accuracy  
  - Churn → Precision: 0.48 | Recall: 0.62 | F1: 0.54  
  - Good on non-churn but weak churn detection.
- **Entropy:** 90% accuracy  
  - Churn → Precision: 0.59 | Recall: 0.64 | F1: 0.61  
  - More balanced and fewer misclassifications.

## Random Forest
- **Gini:** 90% accuracy  
  - Churn → Precision: 0.57 | Recall: 0.62 | F1: 0.59  
  - High performance but slightly overfitting.
- **Entropy:** 91% accuracy  
  - Churn → Precision: 0.64 | Recall: 0.62 | F1: 0.63  
  - Best model overall — accurate, stable, and balanced.

##  Final Choice
**Random Forest (Entropy)**  
- Best test accuracy (91%)  
- Strong churn detection with balanced precision & recall  
- Minimal overfitting — ideal for deployment  