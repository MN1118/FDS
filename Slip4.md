Q1 [A] Product DataFrame [10 Marks]
```py 
import pandas as pd

products = {
    'Product_Name': ['Laptop', 'Phone', 'Tablet', 'Monitor', 'Mouse', 'Keyboard', 'Headphones', 'Printer'],
    'Brand': ['Dell', 'Apple', 'Samsung', 'LG', 'Logitech', 'HP', 'Sony', 'Canon'],
    'Category': ['Electronics'] * 8,
    'Price': [60000, 80000, 30000, 15000, 1200, 1500, 5000, 12000]
}

df = pd.DataFrame(products)
print(df.head(5))
```
Q2 [B] Outlier Detection (IQR & Z-Score) [20 Marks]
```py
import pandas as pd
import numpy as np
from scipy import stats

salaries = [30, 35, 40, 42, 45, 48, 50, 52, 55, 58, 60, 62, 65, 150, 180]
df = pd.DataFrame({'Salary': salaries})

# Quartiles and Percentiles
Q1 = df['Salary'].quantile(0.25)
Q2 = df['Salary'].quantile(0.50)
Q3 = df['Salary'].quantile(0.75)
p90 = df['Salary'].quantile(0.90)

print(f"Q1: {Q1}, Q2: {Q2}, Q3: {Q3}, 90th Percentile: {p90}")

# IQR Method
IQR = Q3 - Q1
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
iqr_outliers = df[(df['Salary'] < lower_bound) | (df['Salary'] > upper_bound)]
print("\nIQR Outliers:\n", iqr_outliers)

# Z-Score Method
df['Z_Score'] = stats.zscore(df['Salary'])
z_outliers = df[np.abs(df['Z_Score']) > 2]
print("\nZ-Score Outliers:\n", z_outliers)
```
Q2 [B - OR] Missing Value Imputation [20 Marks]
```py 
import pandas as pd

raw_data = {
    'Name': ['Shrikrishna', 'Shridhar', 'Mohan', 'Govind', 'Vasudev'],
    'Address': ['Trivendram', 'Madurai', 'Suchindram', 'Rameswaram', 'Kanyakumari'],
    'Age': [20, None, 19, 21, 22],
    'Class': ['BE', 'BSc(CA)', 'BVOC', 'BCom', 'BSc']
}
pd.DataFrame(raw_data).to_csv('StudentData.csv', index=False)

df = pd.read_csv('StudentData.csv')
df['Age'] = df['Age'].fillna(df['Age'].mean())

print(df)
```
