Q1 [A] Fillna and Duplicates [10 Marks]
```py 
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

Q2 [B] Random Array Plots [20 Marks]

```py 

import numpy as np
import matplotlib.pyplot as plt

# Generate random array of 25 integers
np.random.seed(10)
data = np.random.randint(1, 101, 25)

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
Q2 [B - OR] Histogram with Custom Bins [20 Marks]

```py
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