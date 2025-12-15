# MSc Thesis: Impact of Data Splitting on Machine Learning Performance

This repository contains the complete reproducible code for my MSc thesis in
Biostatistics (Distinction), investigating how different train–test split ratios
affect the performance, robustness, and generalization of machine learning models
for gestational diabetes prediction.

## Stucture
MSc-Thesis-Gestational-Diabetes-ML/
│
├── README.md
├── data/
│   └── CBGS_dataset.xlsx
│
├── scripts/
│   ├── 01_data_preprocessing.R
│   ├── 02_multiple_imputation.R
│   ├── 03_modeling_and_evaluation.R
│   └── 04_visualization_and_results.R
│
├── results/
│   ├── auc_results.csv
│   └── roc_curves.png
│
└── session_info.txt


## Methods
- Multiple Imputation (MICE)
- Class Imbalance Handling (ROSE)
- Models:
  - Logistic Regression (Elastic Net)
  - Support Vector Machine
  - Random Forest
  - Naïve Bayes
  - K-Nearest Neighbors
  - XGBoost
- Evaluation Metric: ROC–AUC
- Data Splits: 66/34, 70/30, 75/25, 80/20

## Key Contributions
- Controlled experimental comparison
- No information leakage
- Robust statistical validation
- Emphasis on uncertainty and generalization

## Author
**Ikechukwu Okechi Kamalu**  
MSc Biostatistics  
ORCID: 0009-0008-3922-6310

