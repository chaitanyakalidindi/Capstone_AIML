#  Housing Price Prediction – Capstone Project  

**Author**: Sathwika Varma Kalidindi Chaitanya
**Notebook**: https://github.com/chaitanyakalidindi/Capstone_AIML/blob/main/Capstone_Project_AIML.ipynb

## 1. Research Question  
**How do macroeconomic factors (mortgage rates, interest rates, lumber prices) and demographic trends (population distribution by age) influence housing prices in the U.S., and can regression and machine learning models accurately predict future price movements?**

---

## 2. Why This Question Is Important  

The U.S. housing market is undergoing a structural shift.  
- In 2004, nearly **3.2 million first-time homebuyers** entered the market.  
- By 2024, that number had fallen by almost **two-thirds to just 1.14 million** (National Association of Realtors).  
- Only **25% of home purchases last year** were by first-time buyers — a **historic low**.  

At the same time, builders remain eager to break ground, creating tension between **demand affordability** and **supply expansion**.  

Understanding how **macroeconomic conditions** (interest rates, mortgage rates, construction costs) and **demographic dynamics** (age distribution, household formation) shape housing prices is critical for:  
- **Younger generations** – planning for long-term financial stability in housing markets  
- **Builders and developers** – adjusting supply strategies to align with shifting demand  
- **Financial institutions** – managing lending risk amid changing economic conditions  

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

## 3. Exploratory Data Analysis (EDA) – Key Insights  

- **Demographics as Drivers**  
  - **Adults 35–54 and 26–34**: strong positive impact on prices — prime home-buying cohorts  
  - **Adults 19–25**: negative impact — this group often rents instead of buys  
  - **High house ownership rates**: associated with weaker new demand  

- **Macroeconomic Factors**  
  - **Mortgage & interest rates**: influence affordability and borrowing capacity  
  - **GDP and imports of goods**: positively linked to stronger housing markets  
  - **Export of goods**: negatively correlated, possibly reflecting capital outflows  

---

## 4. Evaluation Metric — RMSE (Derived from MSE)

**Reported metric:** RMSE (Root Mean Squared Error), which is the square root of Mean square error.  

### Why RMSE?
- RMSE is in the **same units as housing prices (dollars)**, making it more intuitive for interpretation.  
- A **lower RMSE** means the model predictions are closer to actual housing prices on average.  


## 4. Model Comparison – Predictive Performance  

| Model                   | Train RMSE | Test RMSE |
|--------------------------|-----------:|----------:|
| Decision Tree            | 3,655      | 10,144    |
| SVM                      | 64,431     | 57,724    |
| Linear Regression        | 3,123      | 5,700     |
| Ridge Regression         | 3,305      | 5,952     |
| Lasso (Feature Selection)| 3,199      | 5,817     |
| Lasso                    | 7,937      | 9,817     |

### Interpretation  
- **Linear, Ridge, and Lasso (feature selection)** give the best balance of accuracy and generalization  
- **Decision Tree** shows overfitting — strong training results but weaker test accuracy  
- **SVM** performs poorly and is not suitable for this dataset  
- **Lasso (feature selection)** reduces irrelevant features while maintaining predictive power  

---

## 5. Investor Takeaways  

- **Demographics drive demand**: Middle-aged buyers (26–54) remain the strongest upward force on prices  
- **Macroeconomic conditions matter**: Mortgage rates and affordability are critical to predicting price movements  
- **Over-saturation risks**: High ownership rates and younger renters reduce new demand pressure  
- **Most reliable prediction models**: Ridge and Lasso (with feature selection) are best suited for forecasting housing prices  

---

## 6. Next Steps  

- Expand dataset with **regional housing data** and **supply-side variables** (new builds, land availability)  
- Develop **time-series forecasting** models to capture price movements over time  
- Deploy into a **dashboard** for real-time monitoring, enabling investors, builders, and lenders to make informed decisions  


