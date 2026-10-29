# Cervical Cancer Mortality Prediction (Machine Learning)

Jupyter notebook that predicts **death within 1, 3, 5 and 10 years of diagnosis** in women with cervical cancer,
using hospital-based cancer registry data (Brazil).

## Methods
- **Predictors:** age at diagnosis, race, city of residence, education, histopathology type, stage at diagnosis
- **Models:** Logistic Regression and Random Forest, tuned by grid search with stratified 5-fold CV
- **Class imbalance:** each model is trained on the original data and with **SMOTE** (applied inside the CV folds to avoid leakage)
- **Evaluation (held-out 25% test set):** accuracy, balanced accuracy, precision (PPV), sensitivity, specificity, NPV,
  F1, MCC, AUROC, AUC-PR, Brier score, confusion matrices and ROC curves

## Data (not included)
Patient-level data are confidential and excluded by `.gitignore`. Place the Excel file at
`data/Mortality_CC_ML_Survival.xlsx` (or edit `DATA_FILE` in the notebook). Required columns:
`Idade, Race, City_residence, education, Categoria_Morfologia, Extensao, death_1yr, death_3yr, death_5yr, death_10yr`
(optional: `observed_1yr ... observed_10yr`).

## Run
```bash
pip install -r requirements.txt
jupyter notebook cervical_cancer_mortality_ml.ipynb
```
All settings (horizons, seed, grids, figure format) are in the **Configuration** cell. Results are saved to `output/`.
