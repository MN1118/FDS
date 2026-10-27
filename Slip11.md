Q1 [A] Sales Metrics [10 Marks]
```py

import pandas as pd

# Create sales data
data = {
    'Product': ['Laptop', 'Mobile', 'Tablet', 'Keyboard', 'Mouse'],
    'Sales': [50000, 30000, 20000, 5000, 2000],
    'Quantity': [5, 10, 8, 15, 20]
}

df = pd.DataFrame(data)

# Display sales data
print("Sales Data:")
print(df)

# Calculate total sales
print("\nTotal Sales:", df['Sales'].sum())

# Calculate average sales
print("Average Sales:", df['Sales'].mean())

# Find maximum sales
print("Maximum Sales:", df['Sales'].max())

# Find minimum sales
print("Minimum Sales:", df['Sales'].min())

# Calculate total quantity sold
print("Total Quantity Sold:", df['Quantity'].sum())

# Calculate total revenue
df['Revenue'] = df['Sales'] * df['Quantity']
print("\nSales with Revenue:")
print(df)

print("\nTotal Revenue:", df['Revenue'].sum())
```
Q2 [B] Iris Bar Plot & Histogram [20 Marks]
```py
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
Q2 [B - OR] Iris Box Plots [20 Marks]
```py
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
