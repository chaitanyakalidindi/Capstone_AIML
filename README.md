# Predicting Average House Prices by State

**Author**: Sathwika Varma Kalidindi Chaitanya

-----

## Executive Summary

This project aims to explore the factors influencing average house prices across different US states from 2008 to 2019 and to build predictive models. We combined various datasets, including state-level Zillow Home Value Index, import/export data, GDP, real per capita income, house ownership rates, and several other economic and demographic indicators. After thorough data cleaning, merging, and exploratory data analysis (EDA), we trained and evaluated several regression models, including Linear Regression, Ridge, Lasso, Decision Tree, Support Vector Regression (SVR), and K-Nearest Neighbors (KNN). The **Linear Regression** model demonstrated the best performance with the lowest test RMSE, as shown in our results.

-----

## Rationale

Understanding the key drivers of house prices is essential for various stakeholders, including potential homebuyers, investors, real estate developers, and policymakers. This project offers valuable insights into how state-level economic indicators, demographic shifts, and other factors correlate with and potentially influence average house values.

-----

## Research Question

What factors significantly influence the average house price at the state level in the United States between 2008 and 2019, and which regression model can best predict these prices?

-----

## Data Sources

  * `State_Zhvi_AllHomes.csv` (State Zillow Home Value Index)
  * `Import.csv` (State Import Data)
  * `Export.csv` (State Export Data)
  * `Gdp.csv` (State GDP Data)
  * `PerCap.csv` (State Real Per Capita Income Data)
  * `House_ownership.csv` (State House Ownership Data)
  * `PPI_Lumber.csv` (PPI Lumber Data)
  * `CPI_ALL.csv` (CPI All Data)
  * `NASDAQ.csv` (NASDAQ Index Data)
  * `MORTGAGE.csv` (Mortgage Rate Data)
  * `PPI_ALL.csv` (PPI All Data)
  * `State Demographics.csv` (State Demographics Data)
  * `historical_state_population_by_year.csv` (Historical State Population Data)
  * `combined_age_data.csv` (Generated during analysis)
  * Combined datasets from various CSVs in `/content/Output/`

-----

## Methodology

1.  **Data Loading and Cleaning**: Load data from various CSV files. Clean column names and convert data types as needed.
2.  **Data Transformation and Merging**: Melt wide-format datasets to a long format. Filter data for the 2008-2019 period. Merge all datasets using common keys like `StateName`, `year`, and `month`.
3.  **Exploratory Data Analysis (EDA)**:
      * Visualize the correlation matrix of numerical features.
      * Create time-series and scatter plots to analyze variable trends and relationships.
      * Generate choropleth maps to visualize the geographical distribution of key metrics.
4.  **Data Preprocessing for Modeling**:
      * Drop non-numerical columns.
      * Split the data into an 80/20 train-test set.
      * Scale numerical features using `StandardScaler`.
5.  **Model Training and Evaluation**:
      * Build and train pipelines for various regression models using `GridSearchCV` for hyperparameter tuning.
      * Evaluate model performance using Root Mean Squared Error (RMSE) on both training and testing sets.
      * Compare RMSE scores to identify the best-performing model.
      * Analyze feature importance and coefficients where applicable.

-----

## Results

Our analysis of the trained models yielded the following RMSE scores:

| Model                      | Train RMSE | Test RMSE  |
| -------------------------- | ---------- | ---------- |
| **Linear Regression** | 3123.22    | **5700.44**|
| Ridge                      | 3305.57    | 5952.09    |
| Lasso                      | 7937.02    | 9817.43    |
| Decision Tree              | 3741.40    | 9808.27    |
| Support Vector Machine (SVM) | 64430.83   | 57723.75   |
| Lasso Feature Selection    | 3198.82    | 5816.77    |

Based on this comparison, the **Linear Regression model** achieved the lowest test RMSE of **5700.44**, making it the best-performing model for predicting house prices in this dataset. The high RMSE of the SVM model suggests it was not a good fit.

-----

## Next Steps

1.  **Feature Engineering**: Create new features, such as lagged variables or interaction terms, to potentially improve model performance.
2.  **Explore Other Models**: Evaluate advanced regression algorithms like **Gradient Boosting** (e.g., XGBoost, LightGBM) or **Random Forest**.
3.  **Time Series Cross-Validation**: Implement a more robust evaluation strategy tailored for time-series data.
4.  **Investigate Weak Correlations**: Further analyze variables like mortgage rates to understand their limited correlation with house prices in this dataset.
5.  **Analyze Residuals**: Examine the residuals of the best model to identify any systematic errors in its predictions.



