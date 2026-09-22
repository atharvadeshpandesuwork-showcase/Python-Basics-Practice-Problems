Q1. What is Pandas ? 

Ans: Pandas is a open source built on top of NumPy that is primarily used for data manipulation and analysis. It provides data structures such as Series as DataFrame, which make 
it easier to load, clean, transform, analyze, and summarize structured data. Pandas is widely used in Data Analytics because many operations that can be performed in tools like excel can 
also be automated using pandas and python. 

Q2. What is series and data frame ?

Ans: The two main data structures in Pandas are Series and DataFrame. A Series is one diamensional labelled data strucutre that can contain values along with an index. A DataFrame is
two-diamensional labelled data structure consisting of rows and columns.

Example:

Series 
```Text
import pandas as pd
sales = pd.Series([1000, 2000, 1500])
```

A DataFrame
```Text
df = pd.DataFrame({
    "Product": ["Laptop", "Phone", "Tablet"],
    "Sales": [1000, 2000, 1500]
})
```

Q3. What is the difference between data frame and a series in python ?

Ans: A series in pandas returns a single column using a single column label. A dataframe in pandas returns a list of column based on the list of column labels being passed.

Example:
```Text
df["Salary"]            # Series
df[["Salary"]]          # DataFrame
df[["Name", "Salary"]]  # DataFrame
```

Q4. How do you check the datatype of the columns ?

Ans: The dtypes attribute is used to view the data type of each column in a Data Frame. The info() method provides a summary of the dataframe including column names, non-null values 
and data types.

Q5. What is the difference between iloc and loc?

Ans: loc is used for label based indexing with iloc is used for integer-position based indexing. loc selects the data using row and column labels whereas iloc selects 
based on numerical positions.

Problem 1: You are working as a junior data analyst for a company. The HR department has provided with employee salary information and wants quick analysis of the current workforce. The HR manager wants to identify employees with higher salaries, understand the average salary of employees and examine the salary differences between departments. You have been given the following employee data:

| Employee_ID | Employee_Name | Department | Experience | Salary |
|-------------:|---------------|------------|-----------:|-------:|
| 101 | Amit   | IT      | 2 | 35000 |
| 102 | Rahul  | Finance | 5 | 52000 |
| 103 | Sneha  | IT      | 4 | 48000 |
| 104 | Priya  | HR      | 3 | 40000 |
| 105 | Rohan  | Finance | 7 | 65000 |
| 106 | Neha   | IT      | 6 | 72000 |
| 107 | Karan  | HR      | 5 | 55000 |
| 108 | Anjali | IT      | 3 | 42000 |
| 109 | Vikas  | Finance | 2 | 38000 |
| 110 | Meera  | HR      | 8 | 68000 |

Business Questions

- Create a pandas dataframe for the above data?
- Display basic information about the dataframe?
- Display the employee name, department, and salary?
- Find all employees whose salary is greater than 50,000
- Find all the employees working in the IT deaprtment?
- Find all employees working in IT department and have experience greater than 5 years?
- Find the employee with highest salary?
- Find the employee with lowest salary?
- Calculate the average salary of all the employees?
- Sort the employees from highest salary to lowest saalry?

Solution:
```Python
# Creating data frame
import pandas as pd

df = pd.DataFrame({
    "Employee_ID":[
        101,102,103,104,105,
        106,107,108,109,110
    ],
    "Employee_Name":[
        "Amit","Rahul","Sneha","Priya","Rohan",
        "Neha","Karan","Anjali","Vikas","Meera"
    ],
    "Department":[
        "IT","Finance","IT","HR","Finance",
        "IT","HR","IT","Finance","HR"
    ],
    "Experience":[
        2,5,4,3,7,
        6,5,3,2,8
    ],
    "Salary":[
        35000,52000,48000,40000,65000,
        72000,55000,42000,38000,68000
    ]
})

# Basic information about the dataset.
df.info()
df.shape

# Display employee name salary and department columns.
df.loc[:,["Employee_Name","Department","Salary"]]

# Employee whose salary is greater than 50,000.
df.loc[df['Salary'] > 50000]

# Employees working in IT department.
df.loc[df['Department'] == 'IT']

# Employee working in IT department and have experience greater than 5 years.
df.loc[(df['Department'] == 'IT') & (df['Experience'] > 5)]

# Employee with highest salary.
df.loc[df['Salary'] == df['Salary'].max()]

# Employee with lowest salary.
df.loc[df['Salary'] == df['Salary'].min()]

# Calculate average salary of employees
df['Salary'].mean()

# Sort employee salaries from highest to lowest
sorted_df = df.sort_values(by = ['Salary'], ascending = [False])
sorted_df
```

Problem 2:  
