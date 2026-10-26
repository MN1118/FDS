Q1 [A] Descriptive Statistics [10 Marks]
```py 
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

Q2 [B] Pie Chart & Bar Chart [20 Marks]

```py
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
Q2 [B - OR] Euclidean Distance [20 Marks]
```py 
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