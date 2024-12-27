Walmart Weekly Sales Analysis: Summary
Objective:
Identify the deterministic factors influencing weekly sales at Walmart and evaluate the contribution of each feature to predictive model performance, focusing on variance and impurity.

Data Overview:
Variables: Includes numerical (e.g., Weekly Sales, Temperature, CPI, Unemployment) and categorical (e.g., Store, Holiday Flag).
Range: Data spans from May 2010 to October 2012.
Insights:
Numerical variables (e.g., Weekly Sales, Unemployment) exhibit skewness.
Temperature and fuel price are approximately normally distributed, consistent with seasonal patterns.
Assumptions and Variable Transformations:
Store Influence: Location impacts weekly sales.
Method: Group data by store and calculate mean weekly sales to observe differences.
Seasonal Effects: Seasons affect sales trends.
Method: Categorize dates into seasonal groups for analysis.
Model Choices:
Linear Regression:

Applied if data is normalized and assumptions are met (e.g., normality, no multicollinearity).
Normalization Techniques: Min-Max Scaling, Log Transformation, Box-Cox Transformation.
Diagnostic Tests: Shapiro Test for normality, checks for homoscedasticity.
Non-Linear Models:

Polynomial Regression: Suitable for curved relationships.
Cons: Susceptible to overfitting.
Random Forest:
Principle: Ensemble learning using bootstrapped data.
Challenge: Over-representation of dummy variables due to their correlations.
Solution: Analyze feature importance using normalized data.
Gradient Boosting (LightGBM, XGBoost):
Strength: Corrects errors iteratively.
Cons: Computationally intensive.
Approach: Grid search for parameter tuning.
Feature Analysis:
Initial correlation analysis revealed no highly correlated variables.
Feature importance analysis (via Random Forest and SHAP):
Top 5 features: Numerical variables dominated, with seasonal and holiday effects being less significant.
Feature interaction explored (e.g., holiday-season combinations).
Variance Inflation Factor (VIF) test applied to minimize redundancy.
Results:
Consistent feature importance observed across Random Forest and XGBoost.
Unemployment emerged as the most predictive variable for weekly sales.
Next Steps:
Conduct 5-fold cross-validation to evaluate model performance.
Optimize feature combinations to improve metrics (MSE, 
𝑅
2
R 
2
 ).
Confirm model stability by re-running feature importance analysis across different configurations.
Key Insight:
Unemployment is the strongest determinant of weekly sales, demonstrating a significant and consistent relationship with the target variable. Further model refinements can enhance predictive accuracy and interpretability.
