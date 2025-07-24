Project Overview
This project develops regression models to predict wine quality based on various physicochemical features in the White Wine Quality dataset from UCI Machine Learning Repository. The modeling process includes:
Feature engineering to enhance predictive signals.


Building and evaluating both OLS (Ordinary Least Squares) and Ridge Regression models.


Assessing model performance using R², MSE, RMSE, and 5-fold Cross-Validation.


Visualizing actual vs predicted values and residuals.



 Dataset Summary
Source: UCI Wine Quality Dataset


Observations: 3,627 (after cleaning)


Features: 14 numeric variables (original + engineered)


Feature Engineering
total_acidity = fixed + volatile + citric acid


so2_ratio = free sulfur dioxide / total sulfur dioxide


sugar_alcohol_ratio = residual sugar / alcohol


 Modeling Process
 Model 1: Linear Regression (OLS)
Built using statsmodels.OLS


R² (Train): 0.323 | R² (Test): 0.299


Cross-Validation RMSE: 0.7318


 Model 2: Ridge Regression
Built using sklearn.linear_model.Ridge


R² (Train): 0.323 | R² (Test): 0.299


Cross-Validation RMSE: 0.7318


Visualizations:
Actual vs Predicted Quality for both models


 Residual Plots to assess error patterns



Key Observations
OLS and Ridge performed almost identically due to similar underlying structure and minimal overfitting.


Feature Engineering added value, with engineered features like so2_ratio and total_acidity contributing positively.


Multicollinearity was detected in OLS (as indicated by eigenvalue warnings), but Ridge handled it smoothly.


Both models have moderate predictive power, indicating potential need for nonlinear models or additional data.



 Challenges Encountered
Multicollinearity Warning: OLS regression flagged very small eigenvalues. Ridge helped mitigate this.


Visualization Bug: Incorrect use of 'r--' for color argument in hlines() caused a rendering error. Fixed using color='r', linestyles='--'.


Regularized Summary Issue: statsmodels.fit_regularized() does not support .summary(). Ridge model evaluation was completed using sklearn.



 Evaluation Metrics Summary
| Model       | R² (Train) | R² (Test) | RMSE (Test) | CV RMSE |
| ----------- | ---------- | --------- | ----------- | ------- |
| OLS         | 0.323      | 0.299     | 0.7621      | 0.7318  |
| Ridge (α=1) | 0.323      | 0.299     | 0.7622      | 0.7318  |



 Repository Contents
MSCS_634_ProjectDeliverable_2.ipynb – Full notebook with code, outputs, and comments.
README.md – This file summarizing the work.



