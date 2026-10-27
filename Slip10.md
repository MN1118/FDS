Q1 [A] Mean, Median, Mode [10 Marks]
```py

import numpy as np
from statistics import mode

# Accept data
data = [10, 20, 30, 20, 40, 50, 20]

# Calculate mean, median and mode
mean = np.mean(data)
median = np.median(data)
mode_value = mode(data)

# Display results
print("Data:", data)
print("Mean:", mean)
print("Median:", median)
print("Mode:", mode_value)

```
Q2 [B] DataFrame Exploration & Missing Values [20 Marks]
```py

import pandas as pd
import numpy as np

# Create DataFrame
data = {
    'Name': ['Amit', 'Rahul', 'Sneha', 'Priya', 'Rohit'],
    'Age': [20, 21, np.nan, 22, 23],
    'Marks': [85, np.nan, 90, 78, np.nan],
    'City': ['Pune', 'Mumbai', 'Pune', np.nan, 'Nashik']
}

df = pd.DataFrame(data)

# Display DataFrame
print("Original DataFrame:")
print(df)

# Display first five rows
print("\nFirst 5 Rows:")
print(df.head())

# Display DataFrame information
print("\nDataFrame Information:")
df.info()

# Display statistical summary
print("\nStatistical Summary:")
print(df.describe())

# Check missing values
print("\nMissing Values:")
print(df.isnull().sum())

# Fill missing numerical values with column mean
df['Age'] = df['Age'].fillna(df['Age'].mean())
df['Marks'] = df['Marks'].fillna(df['Marks'].mean())

# Fill missing city with a default value
df['City'] = df['City'].fillna('Unknown')

# Display cleaned DataFrame
print("\nDataFrame After Handling Missing Values:")
print(df)

# Check missing values again
print("\nMissing Values After Cleaning:")
print(df.isnull().sum())
```
Q2 [B - OR] Data Discretization [20 Marks]
```py
import pandas as pd
import numpy as np

# Sample Student_Marks.csv setup
pd.DataFrame({'Marks': [35, 55, 72, 88, 95, 42, 68]}).to_csv('Student_Marks.csv', index=False)

df = pd.read_csv('Student_Marks.csv')
print("Before Discretization:\n", df)

bins = [0, 40, 60, 80, 100]
labels = ['Poor', 'Average', 'Good', 'Excellent']

df['Performance'] = pd.cut(df['Marks'], bins=bins, labels=labels)

print("\nAfter Discretization:\n", df)
```
