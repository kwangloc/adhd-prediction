# ADHD Prediction (WiDS Datathon 2025)

This repository (`adhd-prediction`) contains analysis and modeling code for the WiDS Datathon 2025 competition focused on predicting ADHD from functional MRI (fMRI) and metadata.

## Repository structure
- `eda/`
  - `transform_data.ipynb` - data transformation and source preparation
  - `eda_train.ipynb` - dataset exploratory data analysis

- `baseline_xgboost.ipynb` - full end-to-end notebook:
  - Data loading (train/test categorical, quantitative, and functional connectome matrices)
  - Missing value handling
  - One-hot encoding for categorical features
  - Data merging + preprocessing
  - PCA-based feature reduction (optional)
  - Train/validation split
  - XGBoost model training (ADHD outcome and sex prediction)
  - Prediction output and evaluation plots


## Baseline flow

- `# 0. Import`: imports libraries and dependencies.
- `# 1. Load data`: reads train/test categorical, quantitative, and functional connectome matrices.
- `# 2) Missing data`: imputes missing values (categorical by mode, numeric by median).
- `# 3) One-hot encoding`: encodes train/test categorical features with alignment.
- `# 4) Merge data for training`: merges categorical, FCM, and quantitative data into `train_df` and `test_df`.
- `# 5) Training`: optionally runs PCA, defines labels for ADHD and Sex models, trains two XGBoost models, 
- `# 6) Predict`: predict (`ADHD_Outcome`, `Sex_F`) separately on test data. 
- `# 7) Evaluate the Model`: computes accuracy, confusion matrix, and feature importance.