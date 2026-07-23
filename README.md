# Impact of Data Splitting on Machine Learning Performance for Predicting Gestational Diabetes

A fully reproducible machine learning framework investigating how alternative train–test data splitting strategies influence predictive performance, robustness, and generalization in gestational diabetes mellitus (GDM) prediction.

This repository accompanies my MSc thesis in **Biostatistics** (CGPA: **4.00/4.00**, Best Graduating Student) at **Near East University**.

---

# Research Motivation

Machine learning has become increasingly important for early prediction of gestational diabetes mellitus (GDM). However, one methodological question is rarely investigated:

> **How much does the choice of train–test split influence predictive performance?**

Many published studies report model accuracy without examining whether their reported performance depends on arbitrary data partitioning decisions.

This study systematically evaluates how different data-splitting strategies affect the predictive performance of multiple machine learning algorithms under a standardized analytical pipeline.

---

# Study Objectives

The study aimed to:

- investigate the effect of train–test split ratios on machine learning performance;
- compare multiple statistical learning algorithms under identical preprocessing conditions;
- establish a reproducible analytical workflow for biomedical prediction;
- identify the optimal data partition for gestational diabetes prediction.

---

# Dataset

The study analysed data from the **Cambridge Baby Growth Study (CBGS)**, a longitudinal pregnancy cohort conducted at the Rosie Maternity Hospital, Cambridge, United Kingdom.

Characteristics include:

- Prospective pregnancy cohort
- Clinical and demographic variables
- Gestational diabetes outcome
- Biomedical risk factors
- Real-world missing data requiring multiple imputation

---

# Methodological Pipeline

The complete workflow consists of:

```
Raw Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Multiple Imputation (MICE)
      │
      ▼
Class Imbalance Correction (ROSE)
      │
      ▼
Train-Test Splitting
      │
      ▼
Machine Learning Models
      │
      ▼
Model Evaluation
      │
      ▼
ROC Curve Comparison
```

---

# Statistical Methods

## Missing Data

- Multiple Imputation by Chained Equations (MICE)
- Predictive Mean Matching (PMM)
- Five imputations

---

## Class Imbalance

To prevent bias toward the majority class, the training data were balanced using:

- ROSE (Random Over-Sampling Examples)

Importantly, balancing was performed **only on the training set**, preventing information leakage.

---

## Machine Learning Models

Six supervised learning algorithms were evaluated.

| Model |
|--------|
| Logistic Regression (Elastic Net) |
| Support Vector Machine (SVM) |
| Random Forest |
| Naïve Bayes |
| K-Nearest Neighbours (KNN) |
| Extreme Gradient Boosting (XGBoost) |

---

# Experimental Design

Four independent train–test splits were investigated.

| Training | Testing |
|-----------|---------|
| 66% | 34% |
| 70% | 30% |
| 75% | 25% |
| 80% | 20% |

Each algorithm was evaluated under every splitting strategy.

---

# Evaluation Metrics

Models were compared using

- Accuracy
- Precision
- Recall
- F1-score
- ROC Curves
- Area Under the ROC Curve (ROC-AUC)

---

# Key Findings

The study demonstrated that machine learning performance is influenced by data partitioning strategy.

Major findings include:

- Random Forest achieved the highest predictive performance.
- The **70/30 split** produced the strongest overall model performance.
- Random Forest achieved an **AUC of 0.804** using the 70/30 split.
- XGBoost and Support Vector Machine also performed best under the 70/30 split.
- Logistic Regression, Naïve Bayes, and K-Nearest Neighbours showed optimal performance under the 75/25 split.
- Performance differences across splitting ratios highlight the importance of evaluating methodological decisions rather than relying on a single arbitrary partition.

---

# Reproducibility

The repository implements a fully reproducible workflow using R.

Major packages include

- tidyverse
- mice
- caret
- pROC
- ROSE
- randomForest
- glmnet
- xgboost
- e1071
- naivebayes

---

# Repository Structure

```text
.
├── data/
│   ├── clean_data.rds
│   └── imputed_data.rds
│
├── results/
│   ├── auc_results.csv
│   ├── model_results.rds
│   └── roc_curves.png
│
├── main.R
├── README.md
└── LICENSE
```

---

# Running the Analysis

Install required packages.

```r
install.packages(c(
  "tidyverse",
  "mice",
  "caret",
  "pROC",
  "ROSE",
  "randomForest",
  "glmnet",
  "xgboost",
  "e1071",
  "naivebayes"
))
```

Run the complete workflow.

```r
source("main.R")
```

The pipeline automatically performs:

- Data preprocessing
- Multiple imputation
- Class balancing
- Model training
- Performance evaluation
- ROC curve generation
- Results export

---

# Research Contributions

This work contributes by

- providing one of the few systematic evaluations of train–test splitting strategies in gestational diabetes prediction;
- demonstrating the importance of methodological reproducibility in biomedical machine learning;
- presenting a leak-proof analytical pipeline that avoids information leakage;
- establishing a reproducible framework that can be adapted to other clinical prediction studies.

---

# Author

**Ikechukwu Okechi Kamalu**

MSc Biostatistics (CGPA: 4.00/4.00)

Near East University

ORCID: https://orcid.org/0009-0008-3922-6310

GitHub: https://github.com/ikechukwukamalu8
