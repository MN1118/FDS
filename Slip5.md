Q1 [A] Laptops DataFrame [10 Marks]
```py 
import pandas as pd

laptop_data = {
    'Laptop_Model': ['MacBook Pro', 'Dell XPS', 'Lenovo ThinkPad', 'HP Spectre', 'Asus ROG'],
    'Cost': [150000, 120000, 95000, 110000, 130000]
}

df = pd.DataFrame(laptop_data)
print(df)
```

Q2 [B] Pie Chart & Bar Chart [20 Marks]
```py

import matplotlib.pyplot as plt

# Data
subjects = ['Python', 'Java', 'AI', 'Data Science', 'Web Development']
marks = [80, 70, 85, 75, 90]

# Pie Chart
plt.figure(figsize=(6, 6))
plt.pie(marks, labels=subjects, autopct='%1.1f%%', startangle=90)
plt.title('Pie Chart of Subject Marks')
plt.show()

# Bar Chart
plt.figure(figsize=(8, 5))
plt.bar(subjects, marks, color='skyblue', edgecolor='black')
plt.title('Bar Chart of Subject Marks')
plt.xlabel('Subjects')
plt.ylabel('Marks')
plt.xticks(rotation=20)
plt.show()
```

Q2 [B - OR] Range, Variance, Standard Deviation [20 Marks]
```py
import pandas as pd

sales = [12.5, 14.0, 15.2, 11.8, 16.5, 18.0, 17.2, 19.1, 15.0, 13.4, 16.8, 20.1]
sales_series = pd.Series(sales)

sales_range = sales_series.max() - sales_series.min()
variance = sales_series.var()
std_dev = sales_series.std()

print(f"Range: {sales_range:.2f} Lakh")
print(f"Variance: {variance:.2f}")
print(f"Standard Deviation: {std_dev:.2f}")
```
