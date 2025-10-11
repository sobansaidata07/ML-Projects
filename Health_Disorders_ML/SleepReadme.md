"""
------------------------------------------------------------------------------------
🛌 SLEEP DISORDER DETECTION USING MACHINE LEARNING
------------------------------------------------------------------------------------

- PROJECT OVERVIEW:
  Sleep disorders such as Insomnia and Sleep Apnea are influenced by factors like BMI,
  stress, physical activity, blood pressure, and occupation.
  This project uses machine learning models to predict whether a person suffers from:
    • Sleep Apnea
    • Insomnia
    • No Disorder

  (NOTE: Exploratory Data Analysis (EDA) is uploaded separately.)

------------------------------------------------------------------------------------
- OBJECTIVE:
  Build and evaluate ML models that classify individuals into one of three categories:
    1. Sleep Apnea
    2. Insomnia
    3. No Disorder

------------------------------------------------------------------------------------
- FEATURES USED FOR MODELING:
  • Gender
  • Age
  • Occupation
  • BMI Category
  • Stress Level
  • Sleep Duration
  • Quality of Sleep
  • Physical Activity Level
  • Daily Steps
  • Heart Rate
  • Blood Pressure (Systolic & Diastolic)

------------------------------------------------------------------------------------
- MACHINE LEARNING PIPELINE:

  1. DATA PREPROCESSING:
    • Handled class imbalance using SMOTE (on training data only)
    • Encoded categorical variables using OneHotEncoder
    • Encoded target using LabelEncoder
    • Scaled numerical features with StandardScaler
    • Train-Test Split: 70% training, 30% testing (test_size = 0.3)

  2. MODEL TRAINING & EVALUATION:
    Trained and tested the following classifiers:

    🔸 Decision Tree:
       - Accuracy: ~78%
       - Simple and interpretable but less accurate for minority classes

    🔸 Random Forest:
       - Accuracy: ~89%
       - Tuned using RandomizedSearchCV
       - High performance, balanced metrics

    🔸 XGBoost (Final Model):
       - Accuracy: 91%
       - Best performing overall
       - Tuned using RandomizedSearchCV
       - Handled complex patterns and imbalanced data effectively

  3. METRICS USED:
    • Accuracy
    • Precision, Recall, F1-score (Classification Report)
    • Confusion Matrix (Per-Class Performance Analysis)

------------------------------------------------------------------------------------
- KEY TECHNICAL HIGHLIGHTS:
  • SMOTE applied only on training data to prevent data leakage
  • OneHotEncoder set to handle unknown categories (handle_unknown='ignore')
  • Evaluated pipelines with/without scaling, with/without SMOTE
  • Final selected model: XGBoost + SMOTE + Scaled Data

------------------------------------------------------------------------------------
- CONCLUSION:
  • XGBoost performed best with 91% accuracy
  • BMI, Blood Pressure, Occupation, and Sleep Duration are key predictors
  • Balanced physical activity (~60 mins/day) and 7-8 hours sleep are ideal ranges
  • Gender and stress also influenced disorders but less than core health metrics

