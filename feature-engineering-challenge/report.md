# Feature Engineering Challenge Report

## Objective

The objective of this challenge was to improve the Recall score of a Logistic Regression model on the Santander Customer Transaction Prediction dataset while keeping the model family unchanged. Since the dataset is highly imbalanced, Recall was chosen as the primary evaluation metric.

---

# Dataset

- Dataset: Santander Customer Transaction Prediction
- Training Samples: 200,000
- Features: 200 numerical features
- Target Variable: Binary classification (0 and 1)

Initial analysis showed:

- No missing values.
- The dataset was highly imbalanced, with approximately 90% of the samples belonging to class 0 and 10% belonging to class 1.

---

# Data Preprocessing

The following preprocessing steps were performed:

- Removed the `ID_code` column since it is only a unique identifier.
- Separated the feature matrix (`X`) and target variable (`y`).
- Performed an 80-20 train-test split using stratified sampling.
- Standardized the features using StandardScaler.
- The scaler was fitted only on the training data to prevent data leakage.

---

# Model Development

A Logistic Regression model was selected as required by the challenge.

The following experiments were conducted:

1. Baseline Logistic Regression
2. Logistic Regression with class balancing
3. Hyperparameter tuning using GridSearchCV
4. Feature selection using SelectKBest
5. SMOTE oversampling
6. SMOTE combined with GridSearchCV
7. Decision threshold tuning

---

# Results

| Experiment | Recall |
|------------|-------:|
| Baseline Logistic Regression | 0.259 |
| Class Weighting | 0.775 |
| GridSearchCV | 0.782 |
| SMOTE | 0.761 |
| SMOTE + GridSearchCV | **0.797** |
| Threshold = 0.35* | **0.905** |

\*Threshold tuning changes the probability cutoff from the default value of 0.50. This result is considered only if permitted within the challenge guidelines.

---

# Key Observations

- Class imbalance had a significant impact on the baseline model.
- Using `class_weight="balanced"` produced a major improvement in Recall.
- GridSearchCV further improved model performance by selecting the optimal hyperparameters.
- Feature selection using SelectKBest provided limited improvement.
- SMOTE alone did not outperform the class-balanced model.
- Combining SMOTE with GridSearchCV produced the best Recall among the default-threshold models.
- Lowering the classification threshold significantly increased Recall but reduced Precision, demonstrating the trade-off between the two metrics.

---

# Conclusion

A systematic experimentation process was followed to improve the Recall of the Logistic Regression model. Different preprocessing techniques, hyperparameter tuning methods, feature selection, oversampling, and threshold tuning were evaluated.

The best-performing model using the default decision threshold was Logistic Regression trained on SMOTE-balanced data and optimized using GridSearchCV.

Threshold tuning further increased Recall above 0.90 and will be considered for the final submission if permitted by the challenge rules.