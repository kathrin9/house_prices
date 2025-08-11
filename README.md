**Data Science Report: House Price Prediction Analysis**

**Abstract**
This project focuses on analyzing real estate data stored in an SQLite database to predict house prices. The dataset includes information about house features, crime rates by city, and energy-related property taxes. After comprehensive data cleaning and feature engineering, both Linear Regression and Decision Tree models were trained to predict housing prices. Performance was evaluated using RMSE and R² metrics, along with 10-fold cross-validation. The results indicate that the Linear Regression model outperformed the Decision Tree model in both accuracy and generalization.

**Background**
Predicting housing prices is a classic problem in data science and real estate analytics. This project aims to evaluate how various features (e.g., size, number of rooms, city, energy class, taxes, and crime) impact house prices and to develop regression models for price prediction. The data, provided in a structured relational format (SQLite), allows for integration of multiple influencing factors, enabling a more comprehensive analysis.

**Methods**
1. Data Acquisition and Merging:
- Data was sourced from three tables: houses, cities, and energy_classes.
- Using SQL queries, the tables were joined to produce a unified dataset with all relevant features.

2. Preprocessing:
- Missing values were handled with median or mode imputation.
- Redundant columns were dropped and duplicate rows removed.
- Categorical variables like City and Energy Class were encoded numerically.
- Outliers and distribution characteristics were explored via visualizations.

3. Feature Analysis:
- Correlation analysis was performed to identify the influence of each feature on the Price.

4. Modeling:
- A Linear Regression model was trained using 80% of the data and tested on the remaining 20%.
- A Decision Tree Regressor was also trained for comparison.
- Model evaluation was conducted using RMSE and R² metrics.
- 10-fold cross-validation was performed to assess generalization.

5. Hyperparameter Tuning:
- Decision Tree parameters (max_depth, min_samples_split) were adjusted to mitigate overfitting.
- Heatmaps were used to visualize model performance across parameter combinations.
- 
**Results**
- Correlation Findings:
  - Strongest positive correlations with price: Area, Bedrooms, and Bathrooms.
  - Negative influence was observed for Crime.

- Model Evaluation:
  Linear Regression: RMSE = €10,172.76, R² = 0.9025
  Decision Tree: RMSE = €15,008.01, R² = 0.7877

- Cross-validation:
  The average RMSE across 10 folds for the Linear Regression model confirmed its stability and performance.

- Hyperparameter Tuning:
  Tuning improved Decision Tree performance slightly but it still lagged behind Linear Regression.
  Best tuning combinations reduced overfitting but at a cost of lower interpretability.
  
**Conclusions**
The Linear Regression model proved to be a robust and accurate method for predicting house prices in this dataset, outperforming Decision Trees in both accuracy and generalization. The data showed predominantly linear relationships, making linear models especially effective. While Decision Trees offer flexibility, their tendency to overfit was evident unless carefully tuned. Future improvements could involve ensemble methods (e.g., Random Forest, Gradient Boosting) and feature scaling or dimensionality reduction techniques.
