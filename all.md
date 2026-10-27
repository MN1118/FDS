# TYBCA Sem-V — Fundamentals of Data Science Practical Programs

**Savitribai Phule Pune University**  
**T.Y.BCA (SEM-V) NEP Practical Examination — OCT / NOV**  
**Course:** CA-305-MJP: Fundamentals of Data Science  
**Duration:** 3 Hours  
**Marks:** 35

---

Savitribai Phule Pune University

T.Y.BCA (SEM-V) NEP Practical Examination OCT / NOV

CA-305-MJP: Fundamentals of Data Science

Duration: 3 Hours                                                                                                              Marks:35

## Slip 1

### Q1 [A] DataFrame & Head [10 Marks]

```python
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

### Q2 [B] Encoding Student Data [20 Marks]

```python
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

### Q2 [B - OR] Random Integer Plotting [20 Marks]

```python
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

## Slip 2

### Q1 [A] Descriptive Statistics [10 Marks]

```python
import pandas as pd
marks = pd.Series([72, 85, 91, 68, 85, 79, 94])
print(f"Sum: {marks.sum()}")
print(f"Average: {marks.mean():.2f}")
print(f"Median: {marks.median()}")
print(f"Mode: {marks.mode()[0]}")
print(f"Minimum: {marks.min()}")
print(f"Maximum: {marks.max()}")
print(f"Std Dev: {marks.std():.2f}")
```

### Q2 [B] Pie Chart & Bar Chart [20 Marks]

```python
import matplotlib.pyplot as plt
names = ['Alice', 'Bob', 'Charlie', 'David', 'Eva']
percentages = [85, 92, 78, 65, 88]
fig, axes = plt.subplots(1, 2, figsize=(12, 5))

# Pie Chart
axes[0].pie(percentages, labels=names, autopct='%1.1f%%', startangle=90)
axes[0].set_title('Student Percentages (Pie Chart)')

# Bar Chart
axes[1].bar(names, percentages, color='skyblue')
axes[1].set_title('Student Percentages (Bar Chart)')
axes[1].set_ylabel('Percentage')

plt.tight_layout()
plt.show()
```

### Q2 [B - OR] Euclidean Distance [20 Marks]

```python
Python
import pandas as pd
import numpy as np

# Create 2D coordinates DataFrame
df = pd.DataFrame({
    'X': [2, 5, 8, 12, 3],
    'Y': [3, 7, 1, 9, 10]
})

# Select point 0 and point 1
p1 = df.iloc[0].to_numpy()
p2 = df.iloc[1].to_numpy()

diff_vector = p2 - p1
distance = np.linalg.norm(diff_vector)

print(f"Point 1: {p1}")
print(f"Point 2: {p2}")
print(f"Difference Vector: {diff_vector}")
print(f"Euclidean Distance: {distance:.4f}")
```

## Slip 3

### Q1 [A] Fillna and Duplicates [10 Marks]

```python
import pandas as pd
import numpy as np

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'Alice', 'Eve'],
    'Attendance': [90, 80, 85, 90, 95],
    'Score': [88, np.nan, 75, 88, np.nan]
}

df = pd.DataFrame(data)

# Identify duplicate records
print("Duplicate Rows Mask:")
print(df.duplicated())

# Fill missing scores with mean
mean_score = df['Score'].mean()
df['Score'] = df['Score'].fillna(mean_score)

print("\nDataFrame after fillna:")
print(df)
```

### Q2 [B] Random Array Plots [20 Marks]

```python
Refer to Slip 1 -> Q2 [B - OR].
PDF
```

### Q2 [B - OR] Histogram with Custom Bins [20 Marks]

```python
Python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)
ages = np.random.randint(22, 60, 15)

custom_bins = [20, 30, 40, 50, 60]

# Compute frequencies
counts, bin_edges = np.histogram(ages, bins=custom_bins)
for i in range(len(counts)):
    print(f"Bin {bin_edges[i]}-{bin_edges[i+1]}: {counts[i]} employees")

# Plot Histogram
plt.hist(ages, bins=custom_bins, edgecolor='black', color='orange')
plt.xlabel('Age Range')
plt.ylabel('Frequency')
plt.title('Employee Age Distribution')
plt.show()
```

## Slip 4

### Q1 [A] Product DataFrame [10 Marks]

```python
Python
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

### Q2 [B] Outlier Detection (IQR & Z-Score) [20 Marks]

```python
Python
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

### Q2 [B - OR] Missing Value Imputation [20 Marks]

```python
Python
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

## Slip 5

### Q1 [A] Laptops DataFrame [10 Marks]

```python
Python
import pandas as pd

laptop_data = {
    'Laptop_Model': ['MacBook Pro', 'Dell XPS', 'Lenovo ThinkPad', 'HP Spectre', 'Asus ROG'],
    'Cost': [150000, 120000, 95000, 110000, 130000]
}

df = pd.DataFrame(laptop_data)
print(df)
```

### Q2 [B] Pie Chart & Bar Chart [20 Marks]

```python
Refer to Slip 2 -> Q2 [B].
PDF
```

### Q2 [B - OR] Range, Variance, Standard Deviation [20 Marks]

```python
Python
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

## Slip 6

### Q1 [A] Student DataFrame Head [10 Marks]

```python
import pandas as pd

students = {
    'Name': ['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H'],
    'Age': [20, 21, 19, 22, 20, 21, 23, 20],
    'Course': ['BCA'] * 8,
    'Marks': [85, 78, 92, 66, 74, 88, 91, 82]
}

df = pd.DataFrame(students)
print(df.head(5))
```

### Q2 [B] DataFrame Exploration & Modification [20 Marks]

```python
Python
import pandas as pd
import numpy as np

# 1. Create DataFrame with 10 rows
data = {
    'emp_name': [f'Emp_{i}' for i in range(1, 11)],
    'age': np.random.randint(25, 50, 10),
    'salary': np.random.randint(30000, 80000, 10)
}
df = pd.DataFrame(data)

# 2. Apply shape() and describe()
print("Shape:", df.shape)
print("\nDescription:\n", df.describe())

# 3. Add 5 rows with duplicates & missing values, and a 'Department' column
extra_rows = pd.DataFrame({
    'emp_name': ['Emp_1', 'Emp_2', None, 'Emp_11', 'Emp_12'],
    'age': [df['age'].iloc[0], None, 30, 40, 45],
    'salary': [df['salary'].iloc[0], 50000, None, 60000, 70000]
})

df = pd.concat([df, extra_rows], ignore_index=True)
df['Department'] = np.nan

print("\nUpdated DataFrame:")
print(df)
```

### Q2 [B - OR] Student Exploration [20 Marks]

```python
Python
import pandas as pd

raw_data = {
    'Name': ['Smaran', 'Sachin', 'Samarpan', 'Spandan', 'Shaman'],
    'Address': ['Pune', 'Mumbai', 'Delhi', 'Chennai', 'Madurai'],
    'Age': [20, 23, 19, 21, 22],
    'Class': ['ME', 'MSc (CA)', 'MVOC', 'MCom', 'MSc']
}
pd.DataFrame(raw_data).to_csv('StudentData.csv', index=False)

df = pd.read_csv('StudentData.csv')

print("a) Statistical Description:\n", df.describe(include='all'))
print("\nb) Shape of dataset:", df.shape)
print("\nc) First two rows:\n", df.head(2))
```

## Slip 7

### Q1 [A] CSV Reading [10 Marks]

```python
Python
import pandas as pd

staff_data = {
    'staff_id': [101, 102, 103, 104, 105],
    'employee_name': ['John', 'Jane', 'Alex', 'Emily', 'Chris'],
    'department': ['HR', 'IT', 'Finance', 'IT', 'Marketing'],
    'monthly_salary': [45000, 65000, 55000, 60000, 50000]
}
pd.DataFrame(staff_data).to_csv('staff.csv', index=False)

df = pd.read_csv('staff.csv')
print(df)
```

### Q2 [B] Histogram Custom Bins [20 Marks]

Refer to Slip 3 -> Q2 [B - OR].

### Q2 [B - OR] Mean, Median, Mode [20 Marks]

```python
import pandas as pd

student_data = {
    'Roll No': [1, 2, 3, 4, 5],
    'Name': ['A', 'B', 'C', 'D', 'E'],
    'Percentage': [85.5, 90.0, 85.5, 78.0, 92.5]
}
df = pd.DataFrame(student_data)

print(f"Mean Percentage: {df['Percentage'].mean():.2f}")
print(f"Median Percentage: {df['Percentage'].median()}")
print(f"Mode Percentage: {df['Percentage'].mode()[0]}")
```

## Slip 8

### Q1 [A] Book DataFrame [10 Marks]

```python
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

### Q2 [B] Missing Value and One-Hot Encoding [20 Marks]

```python
Python
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

### Q2 [B - OR] Quartiles & Outliers [20 Marks]

```python
Refer to Slip 4 -> Q2 [B].
PDF
```

## Slip 9

### Q1 [A] Iris Frequency [10 Marks]

```python
Python
import pandas as pd

# Load or generate dummy iris dataset if file missing
try:
    df = pd.read_csv('iris.csv')
except FileNotFoundError:
    from sklearn.datasets import load_iris
    iris = load_iris()
    df = pd.DataFrame(iris.data, columns=iris.feature_names)
    df['species'] = [iris.target_names[i] for i in iris.target]

print(df['species'].value_counts())
```

### Q2 [B] 50 Integer Visualization [20 Marks]

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)
data = np.random.randint(1, 100, 50)

fig, axes = plt.subplots(2, 2, figsize=(10, 8))

axes[0, 0].plot(data, color='purple')
axes[0, 0].set_title('Line Chart')

axes[0, 1].scatter(range(len(data)), data, color='coral')
axes[0, 1].set_title('Scatter Plot')

axes[1, 0].hist(data, color='teal', edgecolor='black')
axes[1, 0].set_title('Histogram')

axes[1, 1].boxplot(data)
axes[1, 1].set_title('Box Plot')

plt.tight_layout()
plt.show()
```

### Q2 [B - OR] Complete Descriptive Statistics [20 Marks]

```python
Python
import pandas as pd
import numpy as np

# Create employee.csv if absent
pd.DataFrame({'Salary': [30, 45, 50, 60, 70, 80, 90, 100]}).to_csv('employee.csv', index=False)

df = pd.read_csv('employee.csv')
salary = df['Salary']

stats_data = {
    'Mean': salary.mean(),
    'Median': salary.median(),
    'Variance': salary.var(),
    'Std Dev': salary.std(),
    'Min': salary.min(),
    'Max': salary.max(),
    'Q1 (25%)': salary.quantile(0.25),
    'Q2 (50%)': salary.quantile(0.50),
    'Q3 (75%)': salary.quantile(0.75),
    'Count': salary.count()
}

for k, v in stats_data.items():
    print(f"{k}: {v}")
```

## Slip 10

### Q1 [A] Mean, Median, Mode [10 Marks]

Refer to Slip 7 -> Q2 [B - OR].

### Q2 [B] DataFrame Exploration & Missing Values [20 Marks]

Refer to Slip 6 -> Q2 [B].

### Q2 [B - OR] Data Discretization [20 Marks]

```python
Python
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

## Slip 11

### Q1 [A] Sales Metrics [10 Marks]

```python
Refer to Slip 5 -> Q2 [B - OR].
PDF
```

### Q2 [B] Iris Bar Plot & Histogram [20 Marks]

```python
Python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.datasets import load_iris

iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df['species'] = [iris.target_names[i] for i in iris.target]

fig, axes = plt.subplots(1, 2, figsize=(12, 5))

# Bar Plot
df['species'].value_counts().plot(kind='bar', ax=axes[0], color='skyblue')
axes[0].set_title('Species Frequency (Bar Plot)')

# Histogram
sns.histplot(data=df, x='sepal length (cm)', hue='species', ax=axes[1], kde=True)
axes[1].set_title('Sepal Length Histogram across Species')

plt.tight_layout()
plt.show()
```

### Q2 [B - OR] Iris Box Plots [20 Marks]

```python
Python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris

iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df['species'] = [iris.target_names[i] for i in iris.target]

fig, axes = plt.subplots(2, 2, figsize=(10, 8))
features = iris.feature_names

for i, col in enumerate(features):
    ax = axes[i // 2, i % 2]
    sns.boxplot(x='species', y=col, data=df, ax=ax)
    ax.set_title(f'{col} by Species')

plt.tight_layout()
plt.show()
```

## Slip 12

### Q1 [A] Iris Box Plot Distribution [10 Marks]

Refer to Slip 11 -> Q2 [B - OR].

### Q2 [B] Missing Value Imputation and Encoding [20 Marks]

```python
Python
import pandas as pd
from sklearn.preprocessing import LabelEncoder

data = {
    'Student_name': ['A', 'B', 'C', 'D'],
    'City': ['Pune', 'Mumbai', 'Pune', 'Delhi'],
    'Age': [20, None, 22, 21],
    'Fees': [50000, 60000, None, 55000],
    'Admitted': ['Yes', 'No', 'Yes', 'No']
}
df = pd.DataFrame(data)

# Mean Imputation
df['Age'] = df['Age'].fillna(df['Age'].mean())
df['Fees'] = df['Fees'].fillna(df['Fees'].mean())

# One-Hot Encoding
df = pd.get_dummies(df, columns=['City'])

# Label Encoding
le = LabelEncoder()
df['Admitted'] = le.fit_transform(df['Admitted'])

print(df)
```

### Q2 [B - OR] Plotting with Outliers [20 Marks]

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)
data = np.random.randint(10, 50, 50)

# Display normal Box Plot
plt.figure(figsize=(8, 4))
plt.subplot(1, 2, 1)
plt.boxplot(data)
plt.title('Original Boxplot')

# Add Outliers
data_with_outliers = np.append(data, [150, -50])

plt.subplot(1, 2, 2)
plt.boxplot(data_with_outliers)
plt.title('Boxplot with Outliers')

plt.tight_layout()
plt.show()
```

## Slip 13

### Q1 [A] Dataset Exploration [10 Marks]

```python
import pandas as pd

df = pd.DataFrame({
    'A': [1, 2, 3, None, 5],
    'B': ['x', 'y', 'z', 'w', 'v']
})

print("Shape:", df.shape)
print("Size:", df.size)
print("Data Types:\n", df.dtypes)
print("Statistical Details:\n", df.describe())
print("Missing Values:\n", df.isnull().sum())
```

### Q2 [B] Encoding Country and Purchased [20 Marks]

```python
import pandas as pd
from sklearn.preprocessing import LabelEncoder

data = {
    'Country': ['India', 'USA', 'India', 'France', 'USA'],
    'Purchased': ['No', 'Yes', 'Yes', 'No', 'Yes']
}
df = pd.DataFrame(data)

# OneHot Encoding
df_encoded = pd.get_dummies(df, columns=['Country'])

# Label Encoding
le = LabelEncoder()
df_encoded['Purchased_Encoded'] = le.fit_transform(df['Purchased'])

print(df_encoded)
```

### Q2 [B - OR] Random Integer Visualization with Outliers [20 Marks]

Refer to Slip 12 -> Q2 [B - OR].

## Slip 14

### Q1 [A] Dictionary to DataFrame [10 Marks]

```python
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Marks': [85, 90, 78],
    'City': ['Pune', 'Mumbai', 'Delhi']
}

df = pd.DataFrame(data)
print(df)
```

### Q2 [B] Complete Descriptive Statistics [20 Marks]

Refer to Slip 9 -> Q2 [B - OR].

### Q2 [B - OR] Iris Visualizations [20 Marks]

Refer to Slip 11 -> Q2 [B].

## Slip 15

### Q1 [A] Subject Marks Charts [10 Marks]

Refer to Slip 2 -> Q2 [B].

### Q2 [B] Basic Pandas Operations [20 Marks]

```python
import pandas as pd

# Create dummy data.csv
pd.DataFrame({'A': [10, 20, 30, 40, 50]}).to_csv('data.csv', index=False)

df = pd.read_csv('data.csv')

print("DataFrame:\n", df)
print("\ndescribe():\n", df.describe())
print("\nhead():\n", df.head(2))
print("\ntail():\n", df.tail(2))
print("\nmax():\n", df.max())
print("\nmin():\n", df.min())
```

### Q2 [B - OR] Missing Values and Line Plot [20 Marks]

```python
import pandas as pd
import matplotlib.pyplot as plt

data = {
    'Name': ['A', 'B', 'C', 'D'],
    'Salary': [50000, None, 70000, 60000],
    'Age': [25, 30, None, 40]
}
df = pd.DataFrame(data)

df['Salary'] = df['Salary'].fillna(df['Salary'].mean())
df['Age'] = df['Age'].fillna(df['Age'].mean())

plt.plot(df['Name'], df['Salary'], marker='o', color='purple')
plt.xlabel('Name')
plt.ylabel('Salary')
plt.title('Name vs Salary')
plt.show()
```

## Slip 16

### Q1 [A] Student DataFrame Operations [10 Marks]

```python
Python
import pandas as pd

data = {
    'rollno': [1, 2, 3],
    'name': ['A', 'B', 'C'],
    'mark1': [80, 70, 90],
    'mark2': [85, 75, 95],
    'mark3': [88, 78, 98]
}

df = pd.DataFrame(data)

print("Max:\n", df[['mark1', 'mark2', 'mark3']].max())
print("Min:\n", df[['mark1', 'mark2', 'mark3']].min())
print("Describe:\n", df.describe())
print("Shape:", df.shape)
```

### Q2 [B] Weighted Means (Arithmetic, Harmonic, Geometric) [20 Marks]

```python
import numpy as np

data = np.array([[10, 20, 30], [40, 50, 60]])
weights = np.array([0.2, 0.3, 0.5])

# Weighted Arithmetic Mean
weighted_arithmetic = np.average(data, axis=1, weights=weights)

# Weighted Geometric Mean
weighted_geometric = np.exp(np.average(np.log(data), axis=1, weights=weights))

# Weighted Harmonic Mean
weighted_harmonic = 1 / np.average(1 / data, axis=1, weights=weights)

print("Weighted Arithmetic Mean:", weighted_arithmetic)
print("Weighted Geometric Mean:", weighted_geometric)
print("Weighted Harmonic Mean:", weighted_harmonic)
```

### Q2 [B - OR] Encoding Country and Purchased [20 Marks]

Refer to Slip 13 -> Q2 [B].

## Slip 17

### Q1 [A] NumPy Employee Age Statistics [10 Marks]

```python
Python
import numpy as np

ages = np.array([23, 45, 31, 35, 29, 52, 40, 26, 38, 48])

print("Minimum Age:", np.min(ages))
print("Maximum Age:", np.max(ages))
print("Average Age:", np.mean(ages))
```

### Q2 [B] Read UCI CSV Dataset [20 Marks]

```python
import pandas as pd

# Download / read directly via URL
url = "https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data"
cols = ['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'class']
df = pd.read_csv(url, names=cols)

print("Description:\n", df.describe())
print("\nNumeric Means:\n", df.mean(numeric_only=True))
print("\nMissing Values Count:\n", df.isnull().sum())
```

### Q2 [B - OR] Sampling Methods [20 Marks]

```python
import pandas as pd

df = pd.DataFrame({
    'Employee_ID': range(1, 13),
    'Department': ['HR', 'IT', 'Finance', 'HR', 'IT', 'Finance', 'HR', 'IT', 'Finance', 'HR', 'IT', 'Finance'],
    'Age': [25, 30, 35, 40, 28, 32, 45, 29, 34, 38, 42, 27],
    'Salary': [50, 60, 70, 80, 55, 65, 75, 85, 58, 68, 78, 88]
})

# Simple Random Sampling
srs = df.sample(n=5, random_state=42)

# Systematic Sampling (every 3rd element)
sys_sample = df.iloc[::3]

# Stratified Sampling (1 per department)
strat_sample = df.groupby('Department', group_keys=False).apply(lambda x: x.sample(1))

print("Random Sampling:\n", srs)
print("\nSystematic Sampling:\n", sys_sample)
print("\nStratified Sampling:\n", strat_sample)
```

## Slip 18

### Q1 [A] NumPy Statistics [10 Marks]

```python
Python
import numpy as np

arr = np.array([12, 45, 67, 89, 23, 56, 78, 90, 34, 11])

print("Sum:", np.sum(arr))
print("Mean:", np.mean(arr))
print("Minimum:", np.min(arr))
print("Maximum:", np.max(arr))
```

### Q2 [B] Iris Sampling and Statistics [20 Marks]

```python
import pandas as pd
from sklearn.datasets import load_iris

iris = load_iris()
df = pd.DataFrame(iris.data, columns=iris.feature_names)
df['class'] = [iris.target_names[i] for i in iris.target]

sample_df = df.sample(n=20, random_state=42)

print("Min Numeric:\n", df.min(numeric_only=True))
print("\nMax Numeric:\n", df.max(numeric_only=True))
print("\nClass Value Counts:\n", df['class'].value_counts())
```

### Q2 [B - OR] Euclidean and Manhattan Distance [20 Marks]

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({
    'X': [2, 6, 8, 10],
    'Y': [3, 9, 12, 15]
})

p1 = df.iloc[0].values
p2 = df.iloc[1].values

diff = p2 - p1
euclidean = np.linalg.norm(diff)
manhattan = np.sum(np.abs(diff))

print(f"Difference Vector: {diff}")
print(f"Euclidean Distance: {euclidean:.4f}")
print(f"Manhattan Distance: {manhattan:.4f}")
```

## Slip 19

### Q1 [A] Sort Array Top 3 Marks [10 Marks]

```python
Python
import numpy as np

marks = np.array([78, 85, 62, 90, 95, 88, 71, 99, 82, 65])
sorted_marks = np.sort(marks)
top_3 = sorted_marks[-3:][::-1]

print("Sorted Marks:", sorted_marks)
print("Top 3 Marks:", top_3)
```

### Q2 [B] Weighted Means [20 Marks]

```python
Refer to Slip 16 -> Q2 [B].
PDF
```

### Q2 [B - OR] Normalized Cross-Correlation [20 Marks]

```python
Python
import numpy as np

a = np.array([1, 2, 3, 4, 5], dtype=float)
b = np.array([0, 1, 2, 3, 4], dtype=float)

# Normalize
a_norm = (a - np.mean(a)) / (np.std(a) * len(a))
b_norm = (b - np.mean(b)) / np.std(b)

# Cross Correlation
corr = np.correlate(a_norm, b_norm, mode='full')
lags = np.arange(-len(a) + 1, len(a))
max_lag = lags[np.argmax(corr)]

print(f"Correlation Values: {corr}")
print(f"Lag of Maximum Correlation: {max_lag}")
```

## Slip 20

### Q1 [A] Variance and Standard Deviation [10 Marks]

```python
Python
import numpy as np

arr = np.array([10, 20, 30, 40, 50, 60, 70, 80, 90, 100])

print("Variance:", np.var(arr))
print("Standard Deviation:", np.std(arr))
```

### Q2 [B] Outliers Impact Analysis [20 Marks]

```python
Python
import numpy as np
import pandas as pd
from scipy import stats

data = np.array([10, 12, 14, 15, 16, 18, 20, 22, 100]) # 100 is outlier

def stats_report(arr, label):
    print(f"--- {label} ---")
    print(f"Mean: {np.mean(arr):.2f}, Median: {np.median(arr):.2f}, Std Dev: {np.std(arr):.2f}\n")

stats_report(data, "Original Data")

# IQR Filter
Q1 = np.percentile(data, 25)
Q3 = np.percentile(data, 75)
IQR = Q3 - Q1
filtered_iqr = data[(data >= Q1 - 1.5 * IQR) & (data <= Q3 + 1.5 * IQR)]
stats_report(filtered_iqr, "After IQR Removal")

# Z-score Filter
z_scores = np.abs(stats.zscore(data))
filtered_z = data[z_scores < 2]
stats_report(filtered_z, "After Z-Score Removal")
```

### Q2 [B - OR] Salary Outliers and Percentiles [20 Marks]

Refer to Slip 4 -> Q2 [B].

## Slip 21

### Q1 [A] Conditional Grouping [10 Marks]

```python
Python
import numpy as np

marks = np.array([45, 88, 92, 67, 30, 75, 82, 55, 95, 40])

group1 = np.sum(marks < 50)
group2 = np.sum((marks >= 50) & (marks < 75))
group3 = np.sum(marks >= 75)

print(f"Group 1 (<50): {group1} students")
print(f"Group 2 (50-74): {group2} students")
print(f"Group 3 (>=75): {group3} students")
```

### Q2 [B] 50 Integers Visualizations with Outliers [20 Marks]

```python
Refer to Slip 12 -> Q2 [B - OR].
PDF
```

### Q2 [B - OR] Overlapping Normal Distribution Histograms [20 Marks]

```python
Python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)
d1 = np.random.normal(loc=50, scale=10, size=500)
d2 = np.random.normal(loc=60, scale=15, size=500)

plt.hist(d1, bins=20, alpha=0.5, label='Dataset 1', color='blue', edgecolor='black')
plt.hist(d2, bins=20, alpha=0.5, label='Dataset 2', color='red', edgecolor='black')

plt.title('Histograms of Two Normal Distributions')
plt.legend()
plt.show()
```

## Slip 22

### Q1 [A] List to DataFrame Conversion [10 Marks]

```python
Python
import pandas as pd

subjects = ['Data Science', 'OS', 'Java', 'Web Dev']
marks = [85, 78, 92, 88]

df = pd.DataFrame({'Subject': subjects, 'Marks': marks})
print(df)
```

### Q2 [B] CSV Basic Operations [20 Marks]

```python
Refer to Slip 15 -> Q2 [B].
PDF
```

### Q2 [B - OR] Custom Matplotlib Styling [20 Marks]

```python
Python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 20, 25, 30, 50]

fig, ax = plt.subplots(figsize=(8, 5))
ax.plot(x, y, linewidth=3, color='darkgreen', linestyle='--', marker='o')

ax.set_title("Customized Figure", fontsize=14)
ax.set_xlabel("X Axis Label", fontsize=12)
ax.set_ylabel("Y Axis Label", fontsize=12)
ax.grid(True)

plt.show()
```

## Slip 23

### Q1 [A] Product Price Summary [10 Marks]

```python
Python
import pandas as pd

df = pd.DataFrame({
    'Product': ['A', 'B', 'C', 'D', 'E'],
    'Price': [100, 250, 400, 150, 300]
})

print("DataFrame:\n", df)
print(f"Max Price: {df['Price'].max()}")
print(f"Min Price: {df['Price'].min()}")
print(f"Avg Price: {df['Price'].mean():.2f}")
```

### Q2 [B] L1 Normalization [20 Marks]

```python
Python
import numpy as np
from sklearn.preprocessing import normalize

data = np.array([[10, 20, 30], [40, 50, 60]])
l1_normalized = normalize(data, norm='l1', axis=1)

print("Original Data:\n", data)
print("\nL1 Normalized Data (Row Sum = 1):\n", l1_normalized)
print("Row Sums:", np.sum(l1_normalized, axis=1))
```

### Q2 [B - OR] Rescaling & Normalization on Diabetes Dataset [20 Marks]

```python
Python
import pandas as pd
from sklearn.preprocessing import MinMaxScaler, StandardScaler, normalize

# Load dataset
url = "https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv"
df = pd.read_csv(url, header=None)
num_df = df.iloc[:, :-1]

# Min-Max Scaling
min_max = MinMaxScaler().fit_transform(num_df)

# Standardization
standardized = StandardScaler().fit_transform(num_df)

# Unit-Length Normalization (L2)
unit_length = normalize(num_df, norm='l2')

print("Min-Max Scaled (First Row):", min_max[0])
print("Standardized (First Row):", standardized[0])
print("Unit Length (First Row):", unit_length[0])
```

## Slip 24

### Q1 [A] Study Hours Head, Tail, Shape [10 Marks]

```python
Python
import pandas as pd

df = pd.DataFrame({
    'Student': ['A', 'B', 'C', 'D', 'E', 'F'],
    'Study_Hours': [2, 4, 6, 8, 5, 7],
    'Marks': [50, 60, 75, 90, 70, 85]
})

print("First 3 Rows:\n", df.head(3))
print("\nLast 3 Rows:\n", df.tail(3))
print("\nShape:", df.shape)
```

### Q2 [B] Numerical Binarization [20 Marks]

```python
Python
import pandas as pd
from sklearn.preprocessing import Binarizer

url = "https://raw.githubusercontent.com/jbrownlee/Datasets/master/pima-indians-diabetes.data.csv"
df = pd.read_csv(url, header=None)

binarizer = Binarizer(threshold=30.0)
binary_data = binarizer.fit_transform(df.iloc[:, [2, 3]]) # Binarize specific columns

print("Original Data:\n", df.iloc[:, [2, 3]].head())
print("\nBinarized Data:\n", binary_data[:5])
```

### Q2 [B - OR] Discretize Marks [20 Marks]

```python
Refer to Slip 10 -> Q2 [B - OR].
PDF
```

## Slip 25

### Q1 [A] Total Quantity & Average Price [10 Marks]

```python
Python
import pandas as pd

df = pd.DataFrame({
    'Product': ['Pen', 'Notebook', 'Eraser'],
    'Quantity': [10, 5, 20],
    'Price': [15, 60, 5]
})

print("DataFrame:\n", df)
print(f"Total Quantity: {df['Quantity'].sum()}")
print(f"Average Price: {df['Price'].mean():.2f}")
```

### Q2 [B] Equal-Width Binning [20 Marks]

```python
Python
import pandas as pd

prices = [12, 45, 67, 89, 23, 56, 78, 90, 34, 100]
df = pd.DataFrame({'Price': prices})

df['Category'] = pd.cut(df['Price'], bins=3, labels=['Low', 'Medium', 'High'])

print(df)
```

### Q2 [B - OR] Unit-Length Normalization [20 Marks]

```python
Python
import numpy as np
from sklearn.preprocessing import normalize

data = np.array([[3, 4], [1, 2], [5, 12]])
norm_data = normalize(data, norm='l2', axis=1)

print("Original Data:\n", data)
print("\nUnit-Length Normalized Data:\n", norm_data)
```

## Slip 26

### Q1 [A] Standardization using preprocessing.scale [10 Marks]

```python
Python
import numpy as np
from sklearn.preprocessing import scale

arr = np.array([[1.0, -1.0, 2.0], [2.0, 0.0, 0.0], [0.0, 1.0, -1.0]])
scaled_arr = scale(arr)

print("Original Array:\n", arr)
print("\nStandardized Array:\n", scaled_arr)
```

### Q2 [B] Iris Box Plot Distribution [20 Marks]

```python
Refer to Slip 11 -> Q2 [B - OR].
PDF
```

### Q2 [B - OR] Seaborn Pair Plot [20 Marks]

```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
from sklearn.datasets import load_iris

iris = load_iris()

df = pd.DataFrame(
    iris.data,
    columns=[
        "sepal_length",
        "sepal_width",
        "petal_length",
        "petal_width"
    ]
)

df["species"] = iris.target_names[iris.target]

sns.pairplot(df, hue="species")

plt.show()
```

## Slip 27

### Q1 [A] Min-Max from DataFrame [10 Marks]

```python
Python
import pandas as pd

df = pd.DataFrame({
    'Category': ['A', 'B', 'C', 'D', 'E'],
    'Value': [45, 12, 89, 34, 67]
})

print("DataFrame:\n", df)
print("Maximum Value:", df['Value'].max())
print("Minimum Value:", df['Value'].min())
```

### Q2 [B] Seaborn Joint Plot with KDE [20 Marks]

```python
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
from sklearn.datasets import load_iris

iris = load_iris()

df = pd.DataFrame(
    iris.data,
    columns=["sepal_length", "sepal_width", "petal_length", "petal_width"]
)

df["species"] = iris.target_names[iris.target]

sns.jointplot(
    data=df,
    x="sepal_length",
    y="sepal_width",
    kind="kde",
    fill=True,
    color="teal"
)
plt.show()
```

### Q2 [B - OR] Iris Outliers Box Plot [20 Marks]

Refer to Slip 11 -> Q2 [B - OR].
