# Data Science Salaries Analysis & Prediction

## Project Overview
This project analyzes **Data Science salaries** to find patterns and factors that affect pay.  
We explore job title, experience, company size, location, and remote work.  
Finally, we build models to **predict salaries in USD**.

---

## Dataset
The dataset (`ds_salaries.csv`) includes:

| Column | Description |
|--------|-------------|
| work_year | Year of the salary record (2020–2023) |
| experience_level | Entry, Mid, Senior, Executive |
| employment_type | Full-Time, Part-Time, Contract, Freelance |
| job_title | Employee designation |
| salary_in_usd | Salary in USD (Target column) |
| company_location | Country of company |
| employee_residence | Country of employee |
| company_size | Small, Mid, Large |
| remote_ratio | On-site, Hybrid, Fully remote |

---

## Key Findings

- Most data is from **2022–2023** (~90%).  
- 98% of employees work **full-time**.  
- 60% are **Senior**, 25% Mid, 10% Entry-level.  
- Common job titles: Data Scientist, Data Engineer, Data Analyst, ML Engineer.  
- Most companies are **mid-sized** (78%).  
- Remote work: 47% fully remote, 46% on-site, 7% hybrid.  
- Most companies and employees are **US-based** (~75%).  
- Average salary: **$133,000 USD** (50% earn between $85,000–$175,000).  

**Remote Work Insight:**  
Employees living in a different country than their company are mostly fully remote. On-site and hybrid employees outside the company location tend to earn less.

---

## Data Preparation

1. Remove duplicates and unnecessary columns (`salary`, `salary_currency`).  
2. Encode categorical columns:
   - **Target Encoding**: `job_title`, `employee_residence`, `company_location`.  
   - **One-Hot Encoding**: `experience_level`, `employment_type`, `remote_ratio`, `company_size`.  
3. Scale the data using **StandardScaler**.  
4. Split into **train and test sets** (80% train, 20% test).  

---

## Models Used

- Linear Regression  
- Ridge Regression  
- Random Forest Regressor  
- XGBoost Regressor  

**Evaluation Metrics**: RMSE, MAE, R²  

**Best Model**: **XGBoost**  
- Lowest RMSE and MAE  
- Highest R²  
- Best at predicting salaries

---

## Libraries

- pandas, numpy  
- matplotlib, seaborn  
- sklearn (LinearRegression, Ridge, RandomForestRegressor, train_test_split, GridSearchCV)  
- category_encoders  
- xgboost  

---
# Key Takeaways

- Salary depends on job title, experience, company size, and remote work.
- Fully remote employees often earn more if living in a different country.
- XGBoost is the recommended model for salary prediction.