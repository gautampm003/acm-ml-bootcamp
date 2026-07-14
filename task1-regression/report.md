# Task 1 Report

## Objective

Perform Exploratory Data Analysis (EDA), engineer new features, and build regression models to predict housing prices using the California Housing dataset.

---

## Dataset

- California Housing Dataset
- 20,640 samples
- 8 original input features
- Target: Median House Value

---

## Exploratory Data Analysis

The following EDA steps were performed:

- Examined the dataset using `head()`, `info()`, and `describe()`.
- Verified that there were no missing values.
- Visualized feature distributions using histograms.
- Generated a correlation heatmap to study feature relationships.
- Plotted Median Income vs House Price to analyze their relationship.

---

## Feature Engineering

Three new features were created to improve model performance:

- RoomsPerHousehold
- BedroomRatio
- IncomePerPerson

An updated correlation heatmap was generated to analyze the engineered features.

---

## Models Implemented

The following regression models were trained and evaluated:

- Ridge Regression
- Random Forest Regressor
- XGBoost Regressor

Hyperparameter tuning was performed using:

- GridSearchCV for Random Forest
- RandomizedSearchCV for XGBoost

---

## Evaluation Metrics

The models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score

Actual vs Predicted plots were generated for visual evaluation, and feature importance was analyzed for the tuned Random Forest model.

---

## Results

- Ridge Regression provided a strong baseline model.
- Random Forest significantly improved prediction accuracy by capturing non-linear relationships.
- Hyperparameter tuning further improved both ensemble models.
- The tuned XGBoost model achieved the best overall performance with the highest R² score and the lowest prediction errors.

---

## Conclusion

Exploratory Data Analysis and feature engineering helped identify meaningful patterns within the dataset. Ensemble learning methods outperformed the linear baseline model, and hyperparameter tuning further improved predictive performance. Among all evaluated models, the tuned XGBoost Regressor produced the best overall results for predicting California housing prices.