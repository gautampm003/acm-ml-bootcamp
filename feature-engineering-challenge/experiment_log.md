# Experiment Log

## Objective

Improve the Recall score of a Logistic Regression model on the Santander Customer Transaction Prediction dataset while keeping the model family unchanged.

---

## Experiment 1: Baseline Logistic Regression

### Description
Trained a baseline Logistic Regression model using the standardized dataset.

### Observation
- High Accuracy due to class imbalance.
- Very low Recall, indicating that many positive samples were misclassified.

### Results

| Metric | Value |
|--------|------:|
| Accuracy | 0.9134 |
| Precision | 0.6822 |
| Recall | 0.2590 |
| F1 Score | 0.3754 |

---

## Experiment 2: Class Balancing

### Description
Applied `class_weight="balanced"` to assign greater importance to the minority class.

### Observation
Recall increased significantly, although Accuracy and Precision decreased due to the model predicting more positive samples.

### Results

| Metric | Value |
|--------|------:|
| Accuracy | 0.7834 |
| Precision | 0.2865 |
| Recall | 0.7754 |
| F1 Score | 0.4184 |

---

## Experiment 3: Hyperparameter Tuning (GridSearchCV)

### Description
Performed GridSearchCV using 5-fold cross-validation to determine the best Logistic Regression hyperparameters.

### Parameter Grid

- C: 0.001, 0.01, 0.1, 1, 10, 100
- Solver: liblinear, lbfgs
- Penalty: l2

### Best Parameters

- C = 0.001
- Solver = liblinear
- Penalty = l2

### Observation

GridSearchCV produced a small improvement in Recall over the class-balanced model.

Best Cross Validation Recall:

0.78088

---

## Experiment 4: Feature Selection (SelectKBest)

### Description

Selected the top scoring features using ANOVA F-score (`f_classif`) before training Logistic Regression.

### Observation

Feature selection was evaluated to determine whether reducing the feature space could improve Recall. The improvement was limited compared to previous experiments.

---

## Experiment 5: SMOTE

### Description

Applied SMOTE (Synthetic Minority Oversampling Technique) on the training dataset to balance the classes.

### Observation

The training dataset became balanced. However, SMOTE alone did not outperform the class-balanced Logistic Regression model.

---

## Experiment 6: SMOTE + GridSearchCV

### Description

Repeated GridSearchCV after applying SMOTE to identify the optimal hyperparameters for the balanced training dataset.

### Results

| Metric | Value |
|--------|------:|
| Accuracy | 0.7610 |
| Precision | 0.2681 |
| Recall | 0.7965 |
| F1 Score | 0.4012 |

### Observation

This produced the best Recall among all models using the default decision threshold.

---

## Experiment 7: Threshold Tuning

### Description

Instead of using the default probability threshold of 0.50, multiple thresholds were evaluated to study the Precision–Recall trade-off.

### Results

| Threshold | Recall |
|-----------|-------:|
| 0.50 | 0.797 |
| 0.45 | 0.838 |
| 0.40 | 0.874 |
| 0.35 | **0.905** |
| 0.30 | 0.931 |
| 0.25 | 0.953 |
| 0.20 | 0.971 |

### Observation

Lowering the classification threshold significantly improved Recall while reducing Precision.

This experiment will be included in the final solution only if threshold tuning is permitted within the challenge rules.

---

# Final Conclusion

Several techniques were evaluated to improve Recall:

- Class Weighting
- Hyperparameter Tuning
- Feature Selection
- SMOTE
- SMOTE + GridSearchCV
- Threshold Tuning

Among the default-threshold models, **SMOTE combined with GridSearchCV** achieved the highest Recall.

Threshold tuning further increased Recall above **0.90**, demonstrating the trade-off between Recall and Precision.