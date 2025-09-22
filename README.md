# 1. Import libraries
import pandas as pd
from google.colab import files

# 2. Load dataset
try:
    df = pd.read_csv("Mall_Customers.csv")
except FileNotFoundError:
    print("Mall_Customers.csv not found. Please upload the file.")
    uploaded = files.upload()
    if 'Mall_Customers.csv' in uploaded:
        with open('Mall_Customers.csv', 'wb') as f:
            f.write(uploaded['Mall_Customers.csv'])
        df = pd.read_csv("Mall_Customers.csv")
        print("File uploaded and loaded successfully.")
    else:
        print("Failed to upload Mall_Customers.csv.")
        exit()


# 3. Quick view
print(df.shape)
print(df.head())

# 4. Standardize column names
df.columns = ["customer_id", "gender", "age", "annual_income_k", "spending_score"]

# 5. Check duplicates
print("Duplicates:", df.duplicated().sum())
df = df.drop_duplicates()

# 6. Check missing values
print("Missing values:\n", df.isnull().sum())

# 7. Fix data types
df["customer_id"] = df["customer_id"].astype(int)
df["age"] = pd.to_numeric(df["age"], errors="coerce")
df["annual_income_k"] = pd.to_numeric(df["annual_income_k"], errors="coerce")
df["spending_score"] = pd.to_numeric(df["spending_score"], errors="coerce")

# 8. Standardize categorical values
df["gender"] = df["gender"].str.strip().str.title()

# 9. Outlier check
print(df.describe())

# Optional: remove extreme ages if found
df = df[df["age"].between(10, 90)]

# 10. Save cleaned dataset
df.to_csv("mall_customers_cleaned.csv", index=False)
print("Cleaned dataset saved!")
