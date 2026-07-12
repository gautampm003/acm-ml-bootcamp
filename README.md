# ACM ML Bootcamp

This repository contains my submissions for the ACM AI/ML Bootcamp.

## Repository Structure

```
task1-regression/
    regression_pipeline.ipynb

feature-engineering-challenge/
    notebook.ipynb
    experiment_log.md
    report.md
```

---

## Task 1

Implemented and compared regression models on the California Housing dataset.

Techniques used:

- Exploratory Data Analysis (EDA)
- Data Preprocessing
- Ridge Regression
- Random Forest Regressor
- GridSearchCV
- Model Evaluation

---

## Feature Engineering Challenge

Objective:

Improve the Recall score of a Logistic Regression model on the Santander Customer Transaction Prediction dataset.

Experiments performed:

- Logistic Regression (Baseline)
- Class Weighting
- GridSearchCV
- Feature Selection (SelectKBest)
- SMOTE Oversampling
- SMOTE + GridSearchCV
- Decision Threshold Tuning

---

## Dataset

The Santander Customer Transaction Prediction dataset is not included in this repository.

Download the dataset from Kaggle and place the files in:

```
feature-engineering-challenge/santanderdataset/
    train.csv
    test.csv
```

before running the notebook.

---

## Requirements

- Python 3.11
- pandas
- numpy
- matplotlib
- scikit-learn
- imbalanced-learn