## Model Card

*Following Google's Model Cards framework for transparent ML documentation*

### Model Details
- **Model Type**: Binary Classification (Logistic Regression)
- **Version**: 1.0
- **Date**: December 2025
- **Developers**: Lillian Elek
- **License**: MIT (Educational/Non-commercial)

### Intended Use
- **Primary Use**: Stroke risk screening in clinical settings
- **Primary Users**: Healthcare providers, population health managers
- **Out-of-Scope Uses**: 
  - ❌ Definitive diagnosis (requires clinical confirmation)
  - ❌ Treatment decisions (supplementary tool only)
  - ❌ Insurance underwriting (ethical concerns)

### Training Data
- **Source**: Kaggle Healthcare Dataset (fedesoriano)
- **Size**: 5,110 patients (4,089 train, 1,021 test)
- **Time Period**: Not specified in source data
- **Geographic Coverage**: Not specified (likely US-based)
- **Class Distribution**: 95% non-stroke, 5% stroke cases

### Evaluation Data
- **Split Method**: Stratified random split (80/20)
- **Test Set Size**: 1,021 patients
- **Same Source**: Training and test from same dataset

### Metrics
| Metric | Value | Threshold |
|--------|-------|------------|
| ROC-AUC | 0.837 | - |
| Accuracy | 0.726 | 0.50 (default) |
| Recall | 0.80 | 0.50 |
| Precision | 0.13 | 0.50 |
| **Optimal Threshold** | **0.65** | **(recommended)** |
| Recall @ 0.65 | 0.74 | 0.65 |
| Precision @ 0.65 | 0.19 | 0.65 |

### Ethical Considerations
- **Bias**: Dataset demographics not fully documented; may not generalize to all populations
- **Fairness**: Should be validated across age, gender, and ethnic groups before deployment
- **Privacy**: Model uses aggregated health data; HIPAA compliance required for deployment
- **Transparency**: Model is fully interpretable (linear coefficients)

### Limitations
1. **Dataset Limitations**:
   - Unknown geographic/temporal coverage
   - Potential selection bias in data collection
   - Missing some clinical risk factors (family history, medications)

2. **Model Limitations**:
   - Low precision (80% of flagged cases are false positives)
   - Trained on imbalanced data (may struggle with edge cases)
   - Linear model may miss complex interactions

3. **Deployment Considerations**:
   - Requires clinical expertise for interpretation
   - Should not be sole basis for medical decisions
   - Needs regular retraining as population changes

### Recommendations
- Use as **first-line screening tool** to prioritize patient review
- Combine with clinical judgment and additional tests
- Monitor performance metrics monthly in production
- Retrain annually or when population characteristics shift
- Conduct fairness audits across demographic subgroups
