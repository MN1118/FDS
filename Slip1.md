Q1 [A] DataFrame & Head [10 Marks]

```py
import pandas as pd

# Create Dictionary
data = {
    'Employee_Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva', 'Frank', 'Grace', 'Henry'],
    'Department': ['HR', 'IT', 'Finance', 'IT', 'HR', 'Finance', 'IT', 'Marketing'],
    'Designation': ['Manager', 'Developer', 'Analyst', 'Developer', 'Executive', 'Manager', 'Lead', 'Executive'],
    'Salary': [60000, 75000, 50000, 70000, 45000, 80000, 90000, 48000]
}

# Create DataFrame
df = pd.DataFrame(data)

# Display first 5 records
print("First 5 Records:")
print(df.head(5))
```

Q2 [B] Encoding Student Data [20 Marks]

```py
import pandas as pd
from sklearn.preprocessing import LabelEncoder

# Save initial data to StudentData.csv
raw_data = {
    'Name': ['Smaran', 'Sachin', 'Samarpan', 'Spandan', 'Shravan'],
    'Address': ['Pune', 'Mumbai', 'Delhi', 'Chennai', 'Madurai'],
    'Age': [20, 23, 19, 21, 22],
    'Class': ['BE', 'BSc(CS)', 'BVOC', 'BCom', 'BSc']
}
pd.DataFrame(raw_data).to_csv('StudentData.csv', index=False)

# Import Dataset
df = pd.read_csv('StudentData.csv')

# a) One-Hot Encoding on Name column
df_encoded = pd.get_dummies(df, columns=['Name'])

# b) Label Encoding on Class column
le = LabelEncoder()
df_encoded['Class_Encoded'] = le.fit_transform(df['Class'])

print(df_encoded)
```

Q2 [B - OR] Random Integer Plotting [20 Marks]

```py 
import numpy as np
import matplotlib.pyplot as plt

# Generate random array of 25 integers
np.random.seed(42)
data = np.random.randint(1, 100, 25)

fig, axes = plt.subplots(2, 2, figsize=(10, 8))

# Line chart
axes[0, 0].plot(data, color='blue', marker='o')
axes[0, 0].set_title('Line Chart')

# Scatter plot
axes[0, 1].scatter(range(len(data)), data, color='red')
axes[0, 1].set_title('Scatter Plot')

# Histogram
axes[1, 0].hist(data, bins=5, color='green', edgecolor='black')
axes[1, 0].set_title('Histogram')

# Box plot
axes[1, 1].boxplot(data, patch_artist=True)
axes[1, 1].set_title('Box Plot')

plt.tight_layout()
plt.show()
```