Q1 [A] Iris Box Plot Distribution [10 Marks]
```py
import matplotlib.pyplot as plt
from sklearn.datasets import load_iris

# Load Iris dataset
iris = load_iris()

# Create box plot
plt.boxplot(iris.data, labels=iris.feature_names)

# Add title and labels
plt.title("Iris Dataset Box Plot Distribution")
plt.xlabel("Features")
plt.ylabel("Measurement (cm)")
plt.xticks(rotation=15)

# Display graph
plt.tight_layout()
plt.show()
```
Q2 [B] Missing Value Imputation and Encoding [20 Marks]
```py
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
Q2 [B - OR] Plotting with Outliers [20 Marks]
```py
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
