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

Problem 2: You are working as Junior data analyst at a retail company that operates stores across different cities. The sales manager wants to understand how different products are performing and which transactions are generating significant revenue. You have been given a small dataset containing information about customer purchases. Your task is to analyze the data using pandas and answer the questions given below:

| Transaction_ID | Customer | City   | Product    | Category     | Quantity | Unit_Price |
|---------------:|----------|--------|------------|--------------|---------:|-----------:|
| 201 | Amit   | Mumbai | Laptop     | Electronics  | 1 | 55000 |
| 202 | Priya  | Pune   | Mouse      | Accessories  | 3 | 800 |
| 203 | Rahul  | Delhi  | Mobile     | Electronics  | 2 | 25000 |
| 204 | Sneha  | Mumbai | Keyboard   | Accessories  | 2 | 1500 |
| 205 | Karan  | Pune   | Laptop     | Electronics  | 1 | 55000 |
| 206 | Neha   | Delhi  | Headphones | Accessories  | 4 | 2000 |
| 207 | Rohan  | Mumbai | Mobile     | Electronics  | 1 | 25000 |
| 208 | Anjali | Pune   | Monitor    | Electronics  | 2 | 18000 |
| 209 | Vikas  | Delhi  | Mouse      | Accessories  | 5 | 800 |
| 210 | Meera  | Mumbai | Tablet     | Electronics  | 1 | 30000 |

Business Questions
- The manager wants to see only the following information: Customer, City, Product, Quantity. Display these columns?
- The manager wants to investigate the transactions that occurred in mumbai?
- Find all the transactions where the customer purchased a laptop?
- The manager wants to identify customers who have purchased more than 2 units in a single transaction. Display those transactions?
- The manager wants to identify electronic transactions from Mumbai where the quantity purchased is greater than 1. Display the matching transactions?
- The company defines total_sales = quantity * unit price create a new column called as total sales?
- After creating Total_Sales identify the transaction that generated highest total sales amount. Return the complete transaction information?
- The manager wants to see transactions arranged from highest total_sales to lowest total_sales. Sort the dataframe accordingly?
- The manager asks: "Which customer generated the highest value single transaction and what product did they purchase?". Provide the answer using the dataframe?

Solution:
```Python
# Creating Data Frame
import pandas as pd
df = pd.DataFrame({
    "Transaction_ID":[
        201,202,203,204,205,
        206,207,208,209,210
    ],
    "Customer":[
        "Amit","Priya","Rahul","Sneha","Karan",
        "Neha","Rohan","Anjali","Vikas","Meera"
    ],
    "City":[
        "Mumbai","Pune","Delhi","Mumbai","Pune",
        "Delhi","Mumbai","Pune","Delhi","Mumbai"
    ],
    "Product":[
        "Laptop","Mouse","Mobile","Keyboard","Laptop",
        "Headphones","Mobile","Monitor","Mouse","Tablet"
    ],
    "Category":[
        "Electronics","Accessories","Electronics","Accessories","Electronics",
        "Accessories","Electronics","Electronics","Accessories","Electronics"
    ],
    "Quantity":[
        1,3,2,2,1,
        4,1,2,5,1
    ],
    "Unit_Price":[
        55000,800,25000,1500,55000,
        2000,25000,18000,800,30000
    ]
})

# Displaying data from Customer, City, Poroduct, Quantity columns
df.loc[:,['Customer','City','Product','Quantity']]

# Transactions done in mumbai
df.loc[df['City']=='Mumbai',:]

# Customers who purchased a laptop
df.loc[df['Product'] == 'Laptop',:]

# Customer who purchased more than 2 quantity in a single transaction
df.loc[df['Quantity'] > 2,:]

# Customers who purchased electonics from mumbai greater than 1 quantity
df.loc[(df['City'] == 'Mumbai')& (df['Category'] == 'Electronics') & (df['Quantity'] > 1),:]

# Adding total sales column
df['Total_Sales'] = df['Quantity'] * df['Unit_Price']
df

# Transaction that generated highest sales
df.loc[df['Total_Sales'] == df['Total_Sales'].max()]

# Transaction that generated lowest sales
df.loc[df['Total_Sales'] == df['Total_Sales'].min()]

# Sorted data frame from highest to lowest sales
sorted_df = df.sort_values(by = ['Total_Quantity'], ascending = [False])
sorted_df

# Which customer generated the highest value single transaction and what product did they purchase?
df.loc[df['Total_Sales'] == df['Total_Sales'].max(),['Customer','Product','Category','Total_Sales']]
```

Problem 3: 
