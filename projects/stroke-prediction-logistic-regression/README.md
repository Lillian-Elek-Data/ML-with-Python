# Stroke Prediction Using Logistic Regression

## Overview
Predict stroke risk using patient health indicators with an
emphasis on recall and interpretability.

## Data
- Source: [Kaggle Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
- Size: 5,109 rows, 11 features
- Class imbalance: ~5% positive

## Modeling Approach
- Logistic Regression (statsmodels + sklearn)
- Class weighting
- Feature selection via statistical significance
- Threshold optimization (Youden’s J)

**Workflow:**
I used a hybrid workflow utilizing statistical analysis and machine learning to run a Healthcare Risk Assessment. 
I performed an early train/test split to prevent leakage. I fit a Logistic Regression model on training data using 
statsmodels for feature selection and assumption validation. After selecting statistically significant features, 
I refit the model with scikit-learn and evaluated assumptions and generalization performance on held-out test data 
as well as performed threshold optimization.

## Results
- ROC-AUC: 0.837
- Recall (stroke): 80% - The model successfully identifies 4 out of 5 patients who will actually experience a stroke—critical for early intervention
- Precision: 13% - When the model flags a patient as high-risk, it's correct 13% of the time, resulting in false alarms for preventive screening

## Key Takeaways
- Age, glucose, and hypertension are dominant risk drivers
- Threshold tuning materially improved clinical recall
- The model is designed as a **screening tool** rather than a diagnostic system, optimized to identify high-risk patients for further evaluation while minimizing missed cases.

## Documentation
- [Model Card](model_card.md)
