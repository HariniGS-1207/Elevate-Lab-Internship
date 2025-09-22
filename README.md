# Mall Customer Segmentation - Data Cleaning

This project is part of my internship task on **Data Cleaning and Preprocessing**.  
The dataset used is the **Mall Customer Segmentation Data** from Kaggle.  
Link to dataset: [Mall Customers Dataset](https://www.kaggle.com/datasets/shwetabh123/mall-customers)

---

## 📊 Dataset Overview
- **Original File:** Mall_Customers.csv  
- **Rows:** 200  
- **Columns:** 5  
  - `CustomerID` : Unique customer ID  
  - `Gender` : Male / Female  
  - `Age` : Age of customer  
  - `Annual Income (k$)` : Annual income (in $1000s)  
  - `Spending Score (1-100)` : Score assigned by the mall based on customer behavior  

---

## 🧹 Data Cleaning Steps
1. **Removed duplicates** – no duplicate rows found.  
2. **Checked for missing values** – none found.  
3. **Standardized column names** – converted to snake_case (`customer_id`, `gender`, `age`, `annual_income_k`, `spending_score`).  
4. **Converted data types** – numeric columns converted to integers/floats where needed.  
5. **Standardized categorical values** – ensured `gender` has only `Male` and `Female`.  
6. **Outlier check** – unrealistic ages (>90) removed.  
7. **Final dataset saved as** `mall_customers_cleaned.csv`.  

---

## 📂 Repository Structure

mall-customer-cleaning/
├─ data/
│ ├─ Mall_Customers.csv # Original dataset
│ └─ mall_customers_cleaned.csv # Cleaned dataset
├─ notebooks/
│ └─ mall_cleaning.ipynb # Jupyter/Colab notebook
├─ summary.txt # Summary of cleaning steps
└─ README.md # Project documentation


