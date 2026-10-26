Q1 [A] Iris Frequency [10 Marks]
```py 
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
Q2 [B] 50 Integer Visualization [20 Marks]
```py 
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
Q2 [B - OR] Complete Descriptive Statistics [20 Marks]

```py 
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
