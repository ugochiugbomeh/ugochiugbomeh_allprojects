# Credit Card Customer Churn Prediction Dashboard

This project presents a full end-to-end credit card customer churn analysis using machine learning and visual storytelling. Built in just four days, the goal was to predict which customers are likely to churn, understand why, and communicate those insights through a compelling Power BI dashboard.

---

## Dataset

**Source**: IBM Sample Dataset (BankChurners.csv)  
**Records**: 10,000 credit card customers  
**Churned Customers**: ~16% of total  
Note: The dataset was pre-cleaned. Class imbalance was preserved during initial analysis and later addressed with **SMOTE** during model training.

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)
- Outlier detection
- Churn breakdown by age, income, education, and card category
- Behavioural analysis (transactions, spend, inactivity)

### 2. Feature Engineering
- `Avg_Transaction_Value` = Total_Trans_Amt / Total_Trans_Ct
- `Revolving_Bal_Per_Limit` = Total_Revolving_Bal / Credit_Limit
- Binned `Age_Group`, created loyalty and activity flags
- Removed highly correlated fields to improve model interpretability

### 3. Modelling
- Models tested: Logistic Regression, Decision Tree, Random Forest, XGBoost
- Final model: **XGBoost**
  - Accuracy: **97%**
  - F1-score (Churn): **0.89**
  - AUC-ROC: **0.99**
- Feature importance and SHAP values used for transparency

### 4. Power BI Dashboard
Built using a **star schema** with:
- `fact_customer_transactions`
- `dim_income`, `dim_card`, `dim_marital`, `dim_education`

#### Dashboard Pages:
1. **Overview** – High-level churn metrics
2. **Demographics** – Loyalty scoring across segments
3. **Behaviour** – Usage patterns and churn risk
4. **Model Insights** – ML-driven drivers of churn

---

## Top Churn Predictors (XGBoost + SHAP)
- Fewer transactions (Total_Trans_Ct)
- High revolving balance
- Low product relationship count
- Low-income customers (< $40K)
- Single customers
- Platinum cardholders with unmet expectations

---

## Tools Used

- Python (Jupyter Notebook)
  - pandas, XGBoost, SHAP, matplotlib, SMOTE (imblearn)
- Power BI (DAX, slicers, custom visuals)
- Excel (dimension mapping & preprocessing)

---

## Some Files Included

- `Credit_Card_Churn.pdf` – Python modelling & analysis  
- `Data_for_BI.pdf` – Feature engineering + schema logic  
- `Page_1–4_BI_Churn.png` – Dashboard screenshots  
- 'created_datasets folder' - Datasets that were generated
- 'powerBIdata folder' - Datasets used in building the PowerBI dashboard

---

## 👋 Contact

Feel free to reach out if you're working on customer retention, churn prevention, or BI storytelling — always happy to connect!
