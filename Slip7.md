Q1 [A] CSV Reading [10 Marks]
```py 
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
Q2 [B] Histogram Custom Bins [20 Marks]
```py

import numpy as np
import matplotlib.pyplot as plt

# Generate random data
np.random.seed(20)
data = np.random.randint(1, 101, 30)

# Define custom bins
bins = [0, 20, 40, 60, 80, 100]

# Create histogram
plt.hist(data, bins=bins, color='skyblue', edgecolor='black')

# Add title and labels
plt.title('Histogram with Custom Bins')
plt.xlabel('Marks Range')
plt.ylabel('Frequency')
plt.xticks(bins)
plt.grid(axis='y', linestyle='--', alpha=0.5)

# Display histogram
plt.show()
```

Q2 [B - OR] Mean, Median, Mode [20 Marks]
```py
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

