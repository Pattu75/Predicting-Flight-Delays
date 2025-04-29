# Predicting Flight Delays: Helping Customers Make Smarter Travel Decisions

Objective:
This project aims to predict flight arrival delays using historical flight data from the Airline Reporting Carrier On-Time Performance dataset. The goal is to provide travelers with data-driven insights for minimizing the risk of delays.

Part 1: Data Understanding

Dataset: Contains 2,855 flights from LAX to JFK, with 21 features including delays, carriers, date, and flight timings.

Exploratory analysis showed high correlation (~0.88) between DepDelay and ArrDelay, indicating the feasibility of predicting arrival delays from departure delays.

Some features (e.g., DivDistance, DivArrDelay) were mostly missing and dropped.

Missing delay components (e.g., CarrierDelay, WeatherDelay) were imputed with 0.

Categorical variables (e.g., Reporting_Airline) were encoded using one-hot encoding.

Part 2: Exploratory Data Analysis (EDA)

Boxplots and scatterplots helped visualize the distribution and correlation of delay variables.

Significant variance observed in delay behavior across airlines and days.

ANOVA confirmed statistically significant differences between some airline groups (e.g., AA vs. PA(1)).

Part 3: Model Development

Simple Linear Regression using DepDelayMinutes showed strong predictive power (R² ~ 0.78).

Multiple Linear Regression incorporating CarrierDelay, LateAircraftDelay, and DepDelayMinutes improved explanatory power.

Predictions were made on new data and validated through confidence intervals.

Part 4: Model Evaluation

Data split: 80% training, 20% testing.

Baseline Linear Regression model:

Training RMSE: 14.17, R²: 0.86

Testing RMSE: 14.07, R²: 0.78

Polynomial Regression (Degree 3) improved performance:

RMSE: 13.54 (train), 13.98 (test), R²: 0.87 (train), 0.78 (test)

10-Fold Cross-Validation:

RMSE: 13.71, R²: 0.84 (mean values)

Part 5: Regularization Models

Ridge Regression (L2):

Coefficients shrunk but retained most features.

DepDelayMinutes had the highest influence.

Lasso Regression (L1):

Set less impactful features (e.g., DayOfWeek) to 0.

Promotes feature selection and simplicity.

Grid Search for Lasso:

Best lambda: 1.463

Best RMSE: 12.58 (CV)

Final Lasso Model Evaluation:

RMSE: 12.84, R²: 0.82, MAE: 7.32

Conclusion:

DepDelayMinutes is the most reliable predictor of arrival delays.

Regularized models (Ridge, Lasso) improve generalization and reduce overfitting.

The final Lasso model balances accuracy and interpretability, making it ideal for deployment.

Data science tools can effectively enhance travel planning by transforming raw flight records into predictive insights.

Recommendations:

Travelers should be cautious when booking flights with consistently high DepDelay history.

Airlines and airports can leverage these models for real-time delay predictions and operational adjustments.
