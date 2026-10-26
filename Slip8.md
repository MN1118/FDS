Q1 [A] Book DataFrame [10 Marks]
```py 
import pandas as pd

books = {
    'title': [f'Book_{i}' for i in range(1, 9)],
    'author': [f'Author_{i}' for i in range(1, 9)],
    'category': ['Fiction', 'Non-Fiction'] * 4,
    'rating': [4.5, 3.8, 4.2, 4.9, 4.0, 3.5, 4.7, 4.1]
}

df = pd.DataFrame(books)
print(df.head(5))
```


Q2 [B] Missing Value and One-Hot Encoding [20 Marks]
```py 
import pandas as pd

data = {
    'Name': ['Shyama', 'Shreeji', 'Ramya', 'Radha', 'Satya'],
    'Address': ['Pune', 'Mumbai', 'Delhi', 'Mumbai', 'Pune'],
    'Age': [20, 19, None, 21, 22],
    'Class': ['BSc (Chemistry)', 'BSc (Physics)', 'BSc (Biology)', 'BSc (Zoology)', 'BSc (CS)']
}
df = pd.DataFrame(data)

# Mean Age Imputation
df['Age'] = df['Age'].fillna(df['Age'].mean())

# One-Hot Encoding on Address
df = pd.get_dummies(df, columns=['Address'])

print(df)
```
Q2 [B - OR] Quartiles & Outliers [20 Marks] 

```py 

import numpy as np
import matplotlib.pyplot as plt

# Given data
data = [10, 12, 14, 15, 18, 20, 22, 24, 25, 30, 100]

# Calculate quartiles
Q1 = np.percentile(data, 25)
Q2 = np.percentile(data, 50)
Q3 = np.percentile(data, 75)

# Calculate IQR
IQR = Q3 - Q1

# Calculate lower and upper limits
lower = Q1 - 1.5 * IQR
upper = Q3 + 1.5 * IQR

# Find outliers
outliers = [x for x in data if x < lower or x > upper]

# Display results
print("Data:", data)
print("Q1 (First Quartile):", Q1)
print("Q2 (Median):", Q2)
print("Q3 (Third Quartile):", Q3)
print("IQR:", IQR)
print("Lower Limit:", lower)
print("Upper Limit:", upper)
print("Outliers:", outliers)

# Draw box plot
plt.boxplot(data, patch_artist=True)
plt.title("Quartiles and Outliers")
plt.ylabel("Values")
plt.grid(True)
plt.show()
```
    