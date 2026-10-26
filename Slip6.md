Q1 [A] Student DataFrame Head [10 Marks]
```py 
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
Q2 [B] DataFrame Exploration & Modification [20 Marks]
```py
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
Q2 [B - OR] Student Exploration [20 Marks]
```py
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