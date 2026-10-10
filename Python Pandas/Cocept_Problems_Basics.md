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

Problem 3: You are working as a Junior Data Analyst for a retail company that sells electronics and accessories from different cities in India. The sales manager has provided you with transaction-level sales data. They want to analyze customer purchases, product performance, transaction values and sales patterns. Your task is to use Pandas to answer the business questions below:

| Order_ID | Customer | City      | Product    | Category    | Quantity | Unit_Price | Payment_Method |
|----------|----------|-----------|------------|-------------|----------|------------|----------------|
| 401 | Atharv | Mumbai    | Laptop     | Electronics | 1 | 62000 | UPI |
| 402 | Riya   | Pune      | Mobile     | Electronics | 2 | 30000 | Credit Card |
| 403 | Kunal  | Delhi     | Mouse      | Accessories | 4 | 850 | UPI |
| 404 | Sneha  | Mumbai    | Monitor    | Electronics | 2 | 24000 | Debit Card |
| 405 | Varun  | Bangalore | Keyboard   | Accessories | 3 | 2000 | UPI |
| 406 | Meera  | Pune      | Laptop     | Electronics | 1 | 62000 | Credit Card |
| 407 | Rahul  | Delhi     | Mobile     | Electronics | 3 | 30000 | UPI |
| 408 | Ananya | Mumbai    | Headphones | Accessories | 2 | 3200 | Cash |
| 409 | Arjun  | Bangalore | Tablet     | Electronics | 2 | 35000 | Credit Card |

Business Questions

- Create a pandas data frame for the above dataset?
- Display basic information about the dataset?
- Display only Customer, City, Product, Quantity?
- Find all transactions from Mumbai?
- Find all transactions where customer purchased more then 3 units?
- Find all electronics transactions where the unit price is greater than 30,000?
- Find the transactions from Mumbai where the customer purchased more than 1 unit?
- Create a new column called as total_sales?
- Find the transactions with highest total sales?
- Calculate the average total sales per transaction?
- Sort the data frame from highest total sales to lowest total sales?
- Find all the transactions where the total sales is greater than 50,000?
- Which customer made the highest value single transaction and which product did they purchase?

Solution:
```Python
import pandas as pd
df = pd.DataFrame({
    'Order_ID':[
        401,402,403,404,405,406,407,408,419,410,
        411,412,413,414,415,416,417,418,419,420,
        421,422,423,424,425,426,427,428,429,430
    ],
    'Customer':[
        'Atharv','Riya','Kunal','Sneha','Varun','Meera','Rahul','Ananya','Arjun','Priya',
        'Rohan','Neha','Yash','Kavya','Aditya','Ishita','Dev','Nisha','Manav','Pooja',
        'Sahil','Aisha','Varsha','Mohit','Simran','Harsh','Tanvi','Akash','Nandini','Vikram'
    ],
    'City':[
        'Mumbai','Pune','Delhi','Mumbai','Bangalore','Pune','Delhi','Mumbai','Bangalore','Delhi',
        'Pune','Mumbai','Bangalore','Delhi','Mumbai','Pune','Bangalore','Delhi','Mumbai','Pune',
        'Delhi','Bangalore','Mumbai','Pune','Delhi','Bangalore','Mumbai','Pune','Delhi','Bangalore'
    ],
    'Product':[
         "Laptop","Mobile","Mouse","Monitor","Keyboard","Laptop","Mobile","Headphones","Tablet","Mouse",
         "Laptop","Keyboard","Monitor","Mobile","Headphones","Laptop","Tablet","Mouse","Mobile","Keyboard",
         "Laptop","Monitor","Headphones","Tablet","Mobile","Mouse","Laptop","Keyboard","Monitor","Headphones"
    ],
    'Category':[
        "Electronics","Electronics","Accessories","Electronics","Accessories","Electronics","Electronics","Accessories","Electronics","Accessories",
        "Electronics","Accessories","Electronics","Electronics","Accessories","Electronics","Electronics","Accessories","Electronics","Accessories",
        "Electronics","Electronics","Accessories","Electronics","Electronics","Accessories","Electronics","Accessories","Electronics","Accessories"
    ],
    'Quantity':[
        1,1,4,2,3,1,3,2,2,6,
        2,4,3,1,5,1,3,5,2,3,
        1,2,3,2,2,7,2,5,2,4
    ],
    'Unit_Price':[
            62000,30000,850,24000,2000,62000,30000,3200,35000,850,
            62000,2000,24000,30000,3200,62000,35000,850,30000,2000,
            62000,24000,3200,35000,30000,850,62000,2000,24000,3200

    ],
    'Payment_Method':[
        "UPI","Credit Card","UPI","Debit Card","UPI","Credit Card","UPI","Cash","Credit Card","UPI",
        "Debit Card","Cash","UPI","Credit Card","Cash","Debit Card","UPI","Credit Card","UPI","Cash",
        "Debit Card","UPI","Credit Card","Cash","UPI","Cash","Credit Card","UPI","Debit Card","Cash"
    ]
})
df

# Basic Information of Dataset
df.info()
print('Shape of data')
df.shape

# Display Customer, City, Product, Quantity
df.loc[:,['Customer','City','Product','Quantity']]

# Transactions from Mumbai
df.loc[df['City'] == 'Mumbai']

# Tansactins where qty purchased is greater than 3 units
df.loc[df['Quantity'] > 3]

# Electronics with price above 30,000
df.loc[(df['Category'] =='Electronics') & (df['Unit_Price'] > 30000)]

# Customer from Mumbai purchased more than 1 unit
df.loc[(df['City'] == 'Mumbai') & (df['Quantity'] > 1)]

# Create new column total_Sales
df['Total_Sales'] = df['Quantity'] * df['Unit_Price']
df

# Highest Product Sold
df.loc[df['Total_Sales'] == df['Total_Sales'].max()]

# Lowest Product Sold
df.loc[df['Total_Sales'] == df['Total_Sales'].min()]

# Average sale per transaction
df['Total_Sales'].mean()

# Sorting the dataframe based on sales
sorted_df = df.sort_values(by=['Total_Sales'],ascending = [False])
sorted_df

# Transactions with sales greater than 50,000
df.loc[df['Total_Sales'] > 50000]

# Customers who made highest single value transaction
df.loc[df['Total_Sales'] == df['Total_Sales'].max(),['Order_ID','Customer','Product','Category','Quantity','Unit_Price']]
```

Problem 4: You are working as a data analyst in Credit department of a Bank. The bank receives loan applications from customers every day. Before approving a loan the credit team looks at several factors such as customers monthly income, credit score, existing loan, requested loan amount and loan tenure. The management team currently has a dataset containing information about 15 recent loan applicants. They want you to analyze this data using Pandas and provide useful insights about the banks lending activity.

| Customer_ID | Customer | City | Age | Monthly_Income | Credit_Score | Existing_Loan | Loan_Amount | Loan_Tenure | Loan_Status |
|-------------|----------|------|-----|----------------|--------------|---------------|-------------|-------------|-------------|
| 501 | Aarav | Mumbai | 28 | 55000  | 745 | No  | 400000  | 5  | Approved |
| 502 | Diya | Pune | 35 | 72000  | 680 | Yes | 600000  | 7  | Approved |
| 503 | Rohan | Delhi | 42 | 48000  | 610 | Yes | 300000  | 5  | Rejected |
| 504 | Anaya | Mumbai | 31 | 85000  | 790 | No  | 800000  | 10 | Approved |
| 505 | Kabir | Pune | 26 | 42000  | 655 | No  | 250000  | 5  | Rejected |

Your job is to help answer questions such as:
- Create a Pandas data frame for the dataset?
- Display the basic information and shape of the data frame?
- Display only: Customer, Monthly_Income, Credit_Score, Loan_Amount, Loan_Status?
- Find all the customers where the credit score is greater than 700?
- Find all customers whose monthly_Income > 60,000 and Credit_Score > 700?
- Find all customers whose loan status is rejected?
- Create a conditional column called as category:

      Credit_Score >= 750: "Excellent"
      Credit_Score >= 700: and <= 750: "Good"
      Credit_Score >= 650: and <= 700: "Average"
      Credit_Score <= 650: "Poor"
- Display Customer, Credit_Score, Credit_Category?
- Find the customers whose credit category is excellent?
- Find the customer with highest credit score?
- Calculate average monthly income of all customers?
- Calculate average loan amount of approved customers only?
- Sort the customers by credit score from highest to lowest?
- Find customers who: Existing loan =="Yes" and Loan Status =="Approved"
- Find customers who: Loan_Amount > 500000 and Loan_Status == "Approved"

Solution:
```Python
#Creating Data Frame
import pandas as pd
df = pd.DataFrame({
    'Customer_ID':[
        601,602,603,604,605,606,
        607,608,609,610,611,612
    ],
    'Customer':[
        'Ayaan','Diya','Rohan','Anaya','Kabir','Ishita',   
        'Vihaan','Sara','Arjun','Myra','Reyansh','Tara'
    ],
    'City':[
        'Mumbai','Pune','Delhi','Mumbai','Pune','Delhi',
         'Mumbai','Pune','Delhi','Mumbai','Pune','Delhi'
    ],
    'Monthly_Income':[
        65000,48000,42000,90000,55000,75000,
        38000,82000,61000,45000,95000,52000
    ],
    'Credit_Score':[
        735,680,620,790,710,760,
        590,775,695,640,805,660
    ],
    'Missed_Payment':[
        0,2,5,0,1,3,
        6,0,2,4,0,3
],
    'Loan_Amount':[
        500000,300000,250000,800000,450000,600000,
        200000,700000,400000,280000,1000000,350000
],
    'Loan_Status':[
        'Approved','Approved','Rejected','Approved','Approved','Approved',
        'Rejected','Approved','Approved','Rejected','Approved','Rejected'
    ],
})

# Basic information of the dataset
df.info()
df.shape

# Display columns Customer, Credit_Score, Missed_Paymets, Loan_Amount, & Loan_Status
df.loc[:,['Customer','Credit_Score','Missed_Payment','Loan_Amount','Loan_Status']]

# Customer whose credit_score >= 700
df.loc[df['Credit_Score'] >= 700]

# Create new column Payment Risk using the following conditions
def payment_risk(data):
    if data >= 5:
        return "Very High Risk"
    elif data >= 3 and data <= 4:
        return "High Risk"
    elif data >= 1 and data <= 2:
        return "Medium Risk"
    else:
        return "Low Risk"
df['Payment_Risk'] = df['Missed_Payment'].apply(payment_risk)

# Display Customer, Missed_Payments, and Payment_Risk
df.loc[:,['Customer','Missed_Payment','Payment_Risk']]

# Customers with High Risk
df.loc[df['Payment_Risk']== 'High Risk']

# Customers with Credit Score < 700 and Loan Status = "Rejected"
df.loc[(df['Credit_Score'] < 700) & (df['Loan_Status'] == 'Rejected'),['Customer_ID','Customer']]

# Customer with highest Missed Payments
df.loc[df['Missed_Payment'] == df['Missed_Payment'].max()]

# Calculate Average Loan Amount
df['Loan_Amount'].mean()

# Customer with loan greater than 500000 
df.loc[df['Loan_Amount'] > 500000]

# Sort Customers by missed payments in descenfing order
sorted_df = df.sort_values(by=['Missed_Payment'], ascending = [False])
sorted_df
```
      
Problem 5: You are working as a junior data analyst in a e-commerce company that sells electronics and accessories across multiple cities. The company has provided you with a dataset containing individual customer orders. The sales and Management teams want to use this data to understand sales patterns across cities, product categories and products. However, before performing the analysis the dataset needs some basic data cleaning and restructuring. Your task is to use Pandas and perform basic analysis.

| Order_ID | Customer | City | Product | Category | Quantity | Unit_Price | Payment_Method |
|---------:|----------|------|---------|----------|---------:|-----------:|----------------|
| 701 | Aarav | Mumbai | Laptop | Electronics | 1 | 65000 | UPI |
| 702 | Diya | Pune | Mobile | Electronics | 2 | 28000 | Credit Card |
| 703 | Rohan | Delhi | Mouse | Accessories | 3 | 900 | UPI |
| 704 | Anaya | Mumbai | Monitor | Electronics | 2 | 22000 | Debit Card |
| 705 | Kabir | Pune | Keyboard | Accessories | 4 | 1800 | UPI |

- The current analysis does require customer's payment method. You need to remove this column so that the working dataset contains information that is relevant to sales analysis?
- A new customer order has been received after the original dataset was prepared. You need to add this transaction to the dataframe?
- The management team wants to analyze orders where customers purchased at least 2 units. Order containing fewer than 2 units should be removed from the analysis?
- Some column names are not descriptive enough for the company's reporting system. The reporting needs the following changes: "Customer" -> "Customer_Name" and "Unit_Price" -> "Price_Per_Unit". Rename these columns while keeping rest of the data unchanged?
- Before performing detailed analysis, the management wants to know:

  ```
    Which cities are represented in the dataset?
    How many products are being sold?
    How many orders are coming from each city?
  ```

- Management also wants to know which products are being purchased in larger quantities. You need to calculate the total quantity sold for each product and arrange the results from highest to lowest?

Solution:

```Python
#Creating dataframe
import pandas as pd
df = pd.DataFrame({
    'Order_ID':[
        701,702,703,704,705,706,707,708,709,710,
        711,712,713,714,715,716,717,718,719,720,
        721,722,723,724,725,726,727,728,729,730
    ],
    'Customer':[
        'Aarav','Diya','Rohan','Anaya','Kabir','Ishita','Vihaan','Sara','Arjun','Myra',
        'Reyansh','Tara','Aditya','Kiara','Dev','Meera','Yash','Nisha','Aryan','Riya',
        'Kunal','Pooja','Manav','Sneha','Varun','Aisha','Rahul','Tanvi','Akash','Nandini'
    ],
    'City':[
        'Mumbai','Pune','Delhi','Mumbai','Pune','Delhi','Mumbai','Pune','Delhi','Mumbai',
        'Pune','Delhi','Mumbai','Pune','Delhi','Mumbai','Pune','Delhi','Mumbai','Pune',
        'Delhi','Mumbai','Pune','Delhi','Mumbai','Pune','Delhi','Mumbai','Pune','Delhi'
],
    'Product':[
        'Laptop','Mobile','Mouse','Monitor','Keyboard','Laptop','Mobile','Headphones','Tablet','Mouse',
        'Laptop','Keyboard','Laptop','Mobile','Headphones','Tablet','Mouse','Monitor','Keyboard','Headphones',
        'Laptop','Mobile','Tablet','Mouse','Monitor','Keyboard','Mobile','Headphones','Laptop','Tablet'
    ],
    'Category':[
        'Electronics','Electronics','Accessories','Electronics','Accessories','Electronics','Electronics','Accessories','Electronics','Accessories',
        'Electronics','Accessories','Electronics','Electronics','Accessories','Electronics','Accessories','Electronics','Accessories','Accessories',
        'Electronics','Electronics','Electronics','Accessories','Electronics','Accessories','Electronics','Accessories','Electronics','Electronics'
    ],
    'Quantity':[
        1,2,3,2,4,1,3,2,2,5,
        1,2,2,4,3,2,6,2,3,4,
        2,2,3,5,3,2,2,5,2,3
    ],
    'Unit_Price':[
        65000,28000,900,22000,1800,65000,28000,2500,32000,900,
        65000,1800,65000,28000,2500,32000,900,22000,1800,2500,
        65000,28000,32000,900,22000,1800,28000,2500,65000,32000
    ],
    'Payment_Method':[
        'UPI','Credit Card','UPI','Debit Card','UPI','Credit Card','UPI','Cash','Credit Card','UPI',
        'Debit Card','Cash','Credit Card','UPI','Cash','UPI','Credit Card','Debit Card','UPI','Cash',
        'Credit Card','UPI','Debit Card','Cash','Credit Card','UPI','Credit Card','Cash','Debit Card','UPI'
    ]
})

# Dropping Payment Method Column
df.drop(columns = 'Payment_Method', inplace = True)
df

# Adding new customer record and coveting numerical to intgers
df.loc[30,:] = [731,'Vikram','Mumbai','Laptop','Electronics',1,65000]
df['Order_ID'] = df['Order_ID'].astype(int)
df['Quantity'] = df['Quantity'].astype(int)
df['Unit_Price'] = df['Unit_Price'].astype(int)
df

# Remove customers who have purchased less than 2 units
df.drop(index = df.loc[df['Quantity'] < 2].index, inplace = True)
df

# Rename customer and unit price columns
df.rename(columns = {"Customer":"Customer_Name"}, inplace = True)
df.rename(columns = {"Unit_Price":"Price_Per_Unit"}, inplace = True)
df

# Which cities are present in the dataset
df['City'].unique()

# How many products are being sold
df['Product'].unique()
df['Product'].nunique()

# Count of orders by city
df.groupby("City").agg({"Order_ID":"count"})

# Product wise quantity sold
products_df = df.groupby("Product").agg({"Quantity":"sum"})
products_df
sorted_df = products_df.sort_values(by = ['Quantity'], ascending = [False])
sorted_df
```

Problem 6: You are working as a Junior Data Analyst in the telecom analytics team similar to Jio. The company wants to analyze customer recharge behavior, data consumption, call usage, and customer activity across different cities. The management team wants to understand:
- Which cities have most customers?
- Which recharge plans are most popular?
- How much data customers are consuming?
- How revenue is generated by different plans?
- When customers are making recharges?
- Which customers show high data usuage?
- Can customers be classified based on their usuage?
- Can the cleaned dataset be exported for further reporting?

| Customer_ID | Customer | City | Plan | Monthly_Rent | Data_GB | Calls_Minutes | Recharge_Date | Payment_Method | Customer_Status |
|-------------|----------|------|------|-------------:|--------:|--------------:|---------------|----------------|-----------------|
| 801 | Aarav   | Mumbai    | 299 Plan | 299 | 18 | 420 | 2026-01-05   | UPI         | Active |
| 802 | Diya    | Pune      | 399 Plan | 399 | 25 | 510 | 06/01/2026   | Credit Card | Active |
| 803 | Rohan   | Delhi     | 249 Plan | 249 | 12 | 350 | Jan 08, 2026 | UPI         | Active |
| 804 | Anaya   | Mumbai    | 599 Plan | 599 | 40 | 620 | 2026/01/10   | Debit Card  | Active |
| 805 | Kabir   | Bangalore | 299 Plan | 299 | 20 | 460 | 12-Jan-2026  | UPI         | Active |

Business Questions
- Create a data frame of the dataset ?
- Display Data frame information, Number of rows and columns, Data types?
- Find unique cities, Number of unique plans, Unique payment methods, Number of active and inactive customers?
- Find Number of Customer each city, Number of customers each plan, Number of customers using each payment method?
- The recharge date contains mixed date formats. Covert this column into a proper pandas datetime column. Check its datatype after conversion?
- Using the converted Recharge date column extract: Recharge_Day, Recharge_Weekday, Recharge_Month, Recharge_Year?
- Find: "Which recharge had the most recharge transactions?" and "Which weekday had most of the recharge transactions?"
- Create a new column called as user_category:

  ```
   Based on Data_GB:
     Data_GB >= 40 → "Very High Usage"
     Data_GB >= 25 → "High Usage"
     Data_GB >= 15 → "Medium Usage"
     Data_GB < 15 → "Low Usage"
  ```
- Find the number of customers in each usage category?
- Find customers who: are Active, have Data_GB >= 30, are subscribed to either the 399 Plan or 599 Plan ?
- Calculate the average Data_GB for each Plan?
- For each city calculate: Total Data_GB, Average Data_GB, Average Calls_Minutes, Maximum Data_GB?
- For each plan calculate: Number of customers, Average Data_GB, Average Calls_Minutes?
- Find the customer with highest Data_GB?
- Find the customer with highest call_minutes?
- Before exporting data:
  
    ```
    Make sure Recharge_Date is a proper datetime column.
    Make sure the new date columns exist.
    Make sure Usage_Category exists.
    Make sure the DataFrame contains the required cleaned columns.
    ```
- Create a csv containing the new dataframe?

Problem 7: You are working as a junior data analyst for a fitness center called Fit Zone. The gym owner wants you to understand how members are using the gym, which membership plans are popular, how much revenue each plan generates, and whether members are maintaining regular attendance. The owner has provided you with membership and attendance related data for 30 customers. Your job is to clean, transform and analyze the data using pandas.

| Member_ID | Member_Name | Gender | Age | Membership_Plan | Monthly_Fee | Attendance_Days | Calories_Burned | Join_Date | Membership_Status |
|----------:|-------------|--------|----:|-----------------|------------:|----------------:|----------------:|-----------|-------------------|
| 901 | Aarav | Male | 24 | Basic | 1500 | 12 | 4200 | 2026-01-05 | Active |
| 902 | Diya | Female | 29 | Premium | 3000 | 20 | 6800 | 05/01/2026 | Active |
| 903 | Rohan | Male | 34 | Basic | 1500 | 8 | 2900 | Jan 08, 2026 | Active |
| 904 | Anaya | Female | 26 | Pro | 4500 | 24 | 8200 | 2026/01/10 | Active |

Business Questions
- Create the data frame using the dataset?
- Display the dataset information shape and datatypes?
- Find: Unique Membership Plans, Number of unique Plans, Unique Membership Status?
- Find the number of members in each: Membership Plan, Membership Status, Gender?
- The gym has received a new membership registration:
     | Member_ID | Member_Name | Gender | Age | Membership_Plan | Monthly_Fee | Attendance_Days | Calories_Burned | Join_Date | Membership_Status |
     |----------:|-------------|--------|----:|-----------------|------------:|----------------:|----------------:|-----------|-------------------|
     | 931 | Karan | Male | 29 | Pro | 4500 | 23 | 8100 | 20-Mar-2026 | Active |
- The join date contains date in mixed date formats. Convert it to proper pandas datetime column. Then create Join_Day, Join_Weekday, Join_Month, Join_Year?
- Find the weekday on which most of the members joined the gym. Return only a single weekday with the highest number of joins?
- Create a conditional column called as attendance category:

  ```
  Attendance >= 20 → "Highly Active"
  Attendance >= 15 → "Regular"
  Attendance >= 10 → "Occasional"
  Attendance < 10 → "Low Attendance"
  ```

- Find the number of members in each attendance category?
- Find active members who: have attendance >= 20, Are subscribed to either Premium or Pro?
- Calculate the average attendance_days for each membership plan?
- For each membership plan calculate:

  ```
  Number of members
  Average Monthly Fee
  Average Attendance Days
  Average Calories Burned
  ```
  
- Calculate the total monthly revenue generated by each membership plan?
- Find the member who burned the highest number of calories?
- Find the member with the highest number of Attendance_Days?
- The gym wants to identify members who may be highly engaged. Find members who have: Attendance > =20 and Calories_Burned >=7000?
- Save your final cleaned and transformed data frame as "fitzone_member_analysis.csv"?

Solution:
```Python
# Creating Data Frame
import pandas as pd
data  = {
    'Member_ID':[
        901,902,903,904,905,906,907,908,909,910,911,912,913,914,915,
        916,917,918,919,920,921,922,923,924,925,926,927,928,929,930
    ],
    'Member_Name':[
        'Aarav','Diya','Rohan','Anaya','Kabir','Ishita','Vihaan','Sara','Arjun','Myra','Reyansh','Tara','Aditya','Kiara','Dev',
        'Meera','Yash','Nisha','Aryan','Riya','Kunal','Pooja','Manav','Sneha','Varun','Aisha','Rahul','Tanvi','Akash','Nandini'
    ],
    'Gender':[
        'Male','Female','Male','Female','Male','Female','Male','Female','Male','Female','Male','Female','Male','Female','Male',
        'Female','Male','Female','Male','Female','Male','Female','Male','Female','Male','Female','Male','Female','Male','Female'
    ],
    'Age':[
        24,9,34,26,31,23,28,35,40,27,25,32,29,22,36,
        30,27,33,24,28,39,25,30,34,26,29,37,31,23,28
    ],
    'Membership_Plan':[
        'Basic','Premium','Basic','Pro','Premium','Basic','Pro','Premium','Basic','Pro','Premium','Basic','Pro','Basic','Premium',
        'Pro','Basic','Premium','Basic','Pro','Premium','Basic','Pro','Premium','Basic','Pro','Premium','Pro','Basic','Premium'
    ],
    'Monthly_Fee':[
        1500,3000,1500,4500,3000,1500,4500,3000,1500,4500,3000,1500,4500,1500,3000,
        4500,1500,3000,1500,4500,3000,1500,4500,3000,1500,4500,3000,4500,1500,3000
    ],
    'Attendance_Days':[
        12,20,8,24,17,10,26,15,6,22,19,9,25,11,16,
        21,7,18,13,23,14,5,27,16,10,22,12,20,14,19
    ],
    'Calories_Burned':[
        4200,6800,2900,8200,5900,3500,9100,5100,2100,7600,6400,3100,8700,3900,5500,
        7300,2500,6100,4500,8000,4800,1800,9400,5700,3400,7800,4100,6900,4700,6500
    ],
    'Join_Date':[
        '05-01-2026','05-01-2026','Jan 08, 2026','10-01-2026','12-Jan-26','15-01-2026','18-01-2026','20-Jan-26','22-01-2026','24-01-2026',
        '26-Jan-26','28-01-2026','Feb 02, 2026','05-02-2026','07-02-2026','09-02-2026','11-Feb-26','14-02-2026','Feb 17, 2026','20-02-2026',
        '22-02-2026','25-02-2026','27-Feb-26','01-03-2026','Mar 04, 2026','07-03-2026','09-03-2026','12-03-2026','15-Mar-26','Mar 18, 2026'
    ],
    'Membership_Status':[
        'Active','Active','Active','Active','Active','Inactive','Active','Active','Inactive','Active','Active','Active','Active','Active','Active',
        'Active','Inactive','Active','Active','Active','Active','Inactive','Active','Active','Active','Active','Inactive','Active','Active','Active'
    ]
}
df = pd.DataFrame(data)

# Dataset information
df.info()

# Shape of dataset
df.shape

# Data types of dataset
df.dtypes

# Unique Membership Plans
df['Membership_Plan'].unique()

# Number of Membership Plans
df['Membership_Plan'].nunique()

# Unique Memebership Status
df['Membership_Status'].unique()

# Adding New Memeber
df.loc[30,:] = [931,'Karan','Male',29,'Pro',4500,23,8100,'20-Mar-2026','Active']
df

# Creationg float to int
df['Member_ID'] = df['Member_ID'].astype(int)
df['Age'] = df['Age'].astype(int)
df['Monthly_Fee'] = df['Monthly_Fee'].astype(int)
df['Attendance_Days'] = df['Attendance_Days'].astype(int)
df['Calories_Burned'] = df['Calories_Burned'].astype(int)
df

# Coverting Join_Date column to pandas date
df['Join_Date'] = pd.to_datetime(df['Join_Date'],format = "mixed")
df['Join_Date'].dtypes

df['Join_Day'] = df['Join_Date'].dt.day
df['Join_Weekday'] = df['Join_Date'].dt.day_name()
df['Join_Month'] = df['Join_Date'].dt.month_name()
df['Join_Year'] = df['Join_Date'].dt.year
df

# Week day when most members joined the Gym
df.groupby("Join_Weekday").agg(Member_Count = ("Member_ID","count")).sort_values(by = ['Member_Count'], ascending = [False]).head(1)

# Creating conditional column attendance category
def attendance_category(attendance_days):
    if attendance_days >= 20:
        return "Highly Active"
    elif attendance_days >= 15:
        return "Regular"
    elif attendance_days >= 10:
        return "Occasional"
    else:
        return "Low Attendance"
df['Attendance_Category'] = df['Attendance_Days'].apply(attendance_category)
df

# Member count in each attendance category
df.groupby("Attendance_Category").agg(Member_Count = ("Member_ID","count")).sort_values(by=['Member_Count'], ascending = [False])

# Active members with attendace greater than 20 days and are Premium or Pro members
df.loc[
    (df['Membership_Status'] == "Active") &
    (df['Attendance_Days'] >= 20) &
    (df['Membership_Plan'].isin(['Premium','Pro']))]

# Average attendance per Membership Plan
df.groupby("Membership_Plan").agg(Avg_Attendance = ("Attendance_Days","mean")).round(0)

# Membership Plan Metrics
df.groupby("Membership_Plan").agg(
    Member_Count = ("Member_ID","count"),
    Average_Monthly_Fee = ("Monthly_Fee","mean"),
    Average_Attendance = ("Attendance_Days","mean"),
    Average_Calories_Burned = ("Calories_Burned","mean")
).round(0).astype(int)

# Monthly Revenue Generated by each Plan
month_order =  ["January", "February", "March", "April","May", "June", "July", "August","September", "October", "November", "December"]
df["Join_Month"] = pd.Categorical(df["Join_Month"],categories = month_order, ordered = True)
df.groupby(["Membership_Plan","Join_Month"]).agg(Total_Revenue = ("Monthly_Fee","sum"))

# Member who burnt maximum amount of calories
df.loc[df['Calories_Burned'] == df['Calories_Burned'].max()]

# Gym memebrs who are highly engaged
df.loc[
    (df['Attendance_Days'] >= 20 ) &
    (df['Calories_Burned'] >= 7000)
]

# Create Engagement Score Column and sort in descending order
df['Engagement_Score'] = df['Attendance_Days'] + (df['Calories_Burned'] / 1000)
df.sort_values(by = ['Engagement_Score'],ascending = [False])
df

df.to_csv("fitzone_member_analysis.csv", index = False)
```

Problem 8: You are working as a Junior data analyst for an FMCG distribution company that sells products from several well-known consumer brands across major Indian cities. The company distributes products across categories such as Personal Care, Hair Care, Home Care, Oral Care, Beverages, Skin Care. Management has noticed high sales volume does not always mean high profitability. Some products sell in large quantities but require heavy discounts. 

Problem 9: You are working as a Business/ Data Analyst for a new airline operator planning to launch a Mumbai -> Goa route. Before entering the market the airline wants to study its competitors. Management has collected information about flights currently operating on this route. Your job is to analyze the competitor data and answer four major strategic questions:
- What type of aircraft should we operate. Should the airline use a smaller aircraft with lower capacity or a aircraft with larger capacity ?
- When should we operate. Which departure period appears to have the strongest combination of passenger demand, occupancy and commercial potential ?
- What pricing should we use. Should the new airline position itself as budget competitive or premium operator?
- Which time period offers the best operational profile. Using the operational-risk indicators provided in the dataset, identify a suitable operating window ?

Business Questions
- Create a data frame and analyze Shape, Datatypes, Missing Values, Number of airlines, Number of aircraft types, Number of Flights?
- Find: Number of flights operated by each airline?, Number of flights operated by each aircraft type?, Average fare of each airline? Identify the airline with the largest presence on this route?
- Convert Flight_Date into proper date time column. Create Flight_Day, Flight_Weekday, Flight_Month, Day_Type where Monday -> Firday: "Weekday" and Saturday -> Sunday "Weekend"
- Create a departure_Slot column with Before 07:00 → "Early Morning" 07:00–11:59 → "Morning" 12:00–15:59 → "Afternoon" 16:00–19:59 → "Evening" 20:00 onwards → "Night"?
- Create Occupancy_Pct = Passengers / Seats * 100. Find the flight with the highest occupancy?
- For each aircraft type calculate: Number of flights, Average seats, Average passengers, Average occupancy, Average fare, Average delay. Then determine which aircraft appears to be most suitable for Mumbai-Goa market?
- For each departure slot calculate: Minimum fare, Maximum fare, Average fare, Average occupancy. Determine which departure period commands the highest average fare?
- Compare weekdays and weekends based on: Average passengers, Average occupancy, Average fare, Average delay. Give short business interpretattion?
- For each airline calculate: Average fare, Minimum fare, Maximum fare, Average occupancy. Identify which airline has the strongest combination of price and passenger utilization?
- Create Estimated_Revenue = Passengers × Base_Fare × (1 - Discount_Pct / 100) Then calculate total estimated revenue by: Airline, Aircraft type, Departure slot?
- Create: Revenue_Per_Seat = Estimated_Revenue / Seats Compare this across aircraft types. Answer: Is the aircraft with the highest passenger capacity necessarily the most commercially attractive?
- Analyze Operational_Risk by departure slot. Calculate: Number of flights, Average delay, Average occupancy, Average operational risk. Identify the departure slot with the best balance between demand and the operational-risk indicators in the dataset ?
- Find combinations of:Aircraft Type × Departure Slot where: Competitor presence is relatively low, Average occupancy is relatively high, Average fare is attractive. Identify a potential market opportunity?
- Based on competitor pricing, occupancy and departure time, recommend a starting fare for the new airline. Your recommendation should classify the strategy as: Budget, Competitive,
Premium and explain why? You are presenting to the airline's management team. Give your final recommendation: Aircraft: Which aircraft type should be operated? , Departure Slot: When should the flight operate? Pricing: What fare should be targeted? Reasoning: Support your recommendation using your analysis of: Passenger demand, Occupancy, Revenue, Revenue per seat,- Competitor pricing, Delays, Operational-risk indicators?

Solution
```Python
# Creating dataset 
import pandas as pd
df = pd.read_csv('Datasets/Mumbai_Goa Airline Market Analysis.csv')
df

# Data Understanding
# Shape of Data
df.shape

# Dataypes of dataset
df.dtypes

# Missing Values present in the dataset
df.isnull().sum()

# Number of Airlines
df['Airline'].unique()

# Number of aircraft type
df['Aircraft_Type'].unique()

# Number of flight
df['Flight_ID'].nunique()

# Competitor revenue
# Number of flights operated by each airline
df.groupby("Airline").agg(Flights_Count = ("Flight_ID","count"))
# Indigo is the largest operating airline on this route

# Number of flights operated by each aircraft type
df.groupby("Aircraft_Type").agg(Flights_Count = ("Aircraft_Type","count"))

# Average fare per airline
df.groupby("Airline").agg(Avg_Fare = ("Base_Fare","mean")).round(0)

# Date Time Manipulation
df['Flight_Date'] = pd.to_datetime(df['Flight_Date'], format = 'mixed')
df['Flight_Day'] = df['Flight_Date'].dt.day 
df['Flight_Weekday'] = df['Flight_Date'].dt.day_name()
df['Flight_Month'] = df['Flight_Date'].dt.month_name()
df['Flight_Year'] = df['Flight_Date'].dt.year
df
# Day type calculation
def day_type(day):
    if day == "Saturday" or day =="Sunday":
        return "Weekend"
    else:
        return "Weekday"
df['Day_Type'] = df['Flight_Weekday'].apply(day_type)
df

# Departure Time analysis
df['Departure_Time'] = pd.to_datetime(df['Departure_Time'],format ="%H:%M")
def time_of_day(hour):
    if hour < 7:
        return "Early Morning"
    elif hour < 12:
        return "Morning"
    elif hour < 16:
        return "Afternoon"
    elif hour < 19:
        return "Evening"
    else:
        return "Night"
df['Departure_Slot'] = df['Departure_Time'].dt.hour.apply(time_of_day)

# Departure time column correction
df['Departure_Time_1'] = df['Departure_Time'].dt.strftime("%H:%M")
cols = df.columns.tolist()
cols.remove("Departure_Time_1")
cols.insert(cols.index("Departure_Time") + 1,"Departure_Time_1")
df = df[cols]
df.rename(columns={"Departure_Time_1":"Departure_Hours"},inplace = True)
df

# Passenger Utilization and Flights with highest occupancy
df['Occupancy_Pct'] = (df['Passengers'] / df['Seats'] * 100).round(2)
df.loc[df['Occupancy_Pct'] == df['Occupancy_Pct'].max(),:]

# Aircraft Analysis
df.groupby("Aircraft_Type").agg(
    Number_Flights = ("Aircraft_Type","count"),
    Average_Seats = ("Seats","mean"),
    Average_Passengers = ("Passengers","mean"),
    Average_Occupancy = ("Occupancy_Pct","mean"),
    Average_Fare = ("Base_Fare","mean"),
    Average_Delay = ("Delay_Min","mean")
).round(0).astype(int).sort_values(by=['Average_Occupancy'], ascending = False)
# The flights suitable are A320, A320neo, B737 Max where neo all three aircrafts have a average occupany rate of 90.

# Time of the day demand 
# df.columns
df.groupby("Departure_Slot").agg(
    Number_Flights = ("Flight_ID","count"),
    Average_Passengers = ("Passengers","mean"),
    Average_Occupancy = ("Occupancy_Pct","mean"),
    Average_Fare = ("Base_Fare","mean"),
    Average_Delay = ("Delay_Min","mean")
).round(0).astype(int).sort_values(by = ['Average_Occupancy'], ascending = [False])
# The strongest slot based on Average Occupancy and Average Pssengers and Average delay is Morning, Night, Evening to be exact with time slots
# 16:00 -> 19:00 (Evening) 7:00am -> 12:00 Pm (Morning) 20:00 onwards (Night)
# Morning and evening is preferred because the average fares are lowest at those timings.

# Pricing analysis
df.groupby("Departure_Slot").agg(
    Max_Fare = ("Base_Fare","max"),
    Min_Fare = ("Base_Fare", "min"),
    Average_Fare = ("Base_Fare","mean"),
    Average_Occupancy = ("Occupancy_Pct","mean"),
).round(0).astype(int).sort_values(by = ['Max_Fare'], ascending = [False])
# The Afternoon period has the highest average fare with average occupancy above 80%

# Weekday vs Weekend analysis
# df.columns
df.groupby("Day_Type").agg(
    Average_Passengers = ("Passengers","mean"),
    Average_Occupancy = ("Occupancy_Pct","mean"),
    Avergae_Fare = ("Base_Fare","mean"),
    Avergae_Delay = ("Delay_Min","mean")
).round(0).astype(int)
# There is no significant difference between passenger movent on weekday and weekend. At both times the average occupancy is greater than 80%
# Also there is no significant difference between average_passengers and fare_prices.

df.columns
df.groupby("Airline").agg(
    Average_Fare = ("Base_Fare","mean"),
    Minimum_Fare = ("Base_Fare","min"),
    Maximum_Fare = ("Base_Fare","max"),
    Average_Occupancy = ("Occupancy_Pct","mean")
).round(0).astype(int).sort_values(by = ['Average_Occupancy'], ascending = [False])
# The competitor Akasa and Indigo are in budget category and have occupancy of 90% and above

# Estimated Passenger revenue
df['Estimated_Revenue'] = df['Passengers'] * df['Base_Fare'] * (1 - df['Discount_Pct'] / 100)
df

# Airline
df.groupby("Airline").agg(Total_ER = ("Estimated_Revenue","sum")).round(0).astype(int).sort_values(by = ['Total_ER'], ascending = [False])

# Aircraft type
df.groupby("Aircraft_Type").agg(Total_ER = ("Estimated_Revenue","sum")).round(0).astype(int).sort_values(by = ['Total_ER'], ascending = [False])

# Departure slot
df.groupby("Departure_Slot").agg(Total_ER = ("Estimated_Revenue","sum")).round(0).astype(int).sort_values(by = ['Total_ER'], ascending = [False])

# Revenue Per Seat
df['Revenue_Per_Seat'] = df['Estimated_Revenue'] / df['Seats']
df

# Is the aircraft with the highest passenger capacity necessarily the most commercially attractive?
df.groupby(['Aircraft_Type','Seats']).agg(
    Revenue_Per_Seat = ("Revenue_Per_Seat","sum")
).round(0).astype(int).sort_values(by = ['Revenue_Per_Seat'], ascending = [False])
# No a aircraft with higher passenger seating is not commercially attractive because the revenue per seat decreases.

risk_score = {"Low": 1, "Moderate": 2, "High": 3}
df["Operational_Risk_Score"] = df["Operational_Risk"].map(risk_score)
df.groupby("Departure_Slot").agg(
    Number_of_Flights=("Flight_ID", "count"),
    Average_Delay=("Delay_Min", "mean"),
    Average_Occupancy=("Occupancy_Pct", "mean"),
    Average_Operational_Risk=("Operational_Risk_Score", "mean")
).round(2).sort_values(by = ['Average_Occupancy'], ascending = [False])
# Evening is the best slot and it strikes the best balance between Average Occupancy and Operational risk with operational risk score of 1.22 
# and occupancy of ~ 92%

# Exporting dataset to csv file
df.to_csv('Final_Data.csv',index = False)
```
```Text
Final Strategy: The airline should enter the Mumbai–Goa route with an Airbus A320/A320neo, operate primarily during the evening slot, and adopt a competitive budget-oriented pricing strategy with a starting base fare of approximately ₹4,500–₹5,000. This strategy aims to attract price-sensitive passengers while leveraging the high occupancy and favorable operational profile observed in the competitor data.
```

Problem 9: You are working as junior data analyst for a retail company operating across multiple cities. Management wants to understand:
- Which products and categories are performing well?
- Which cities generate the most revenue?
- How discounts affect profitability?
- Which payment method are most commonly used?
- How salary vary by month?
- Which category performs best in each city?
- Can a pivot help management compare performance quickly? 

| **Order_ID** | **Order_Date** | **Customer** | **City** | **Category** | **Product** | **Units_Sold** | **Selling_Price** | **Discount_Pct** | **Cost_Per_Unit** | **Payment_Method** |
| -----------: | -------------- | ------------ | -------- | ------------ | ----------- | -------------: | ----------------: | ---------------: | ----------------: | ------------------ |
|         1001 | 05/01/2026     | Amit         | Mumbai   | Electronics  | Laptop      |              2 |             55000 |               10 |             42000 | UPI                |
|         1002 | Jan 07, 2026   | Priya        | Pune     | Accessories  | Mouse       |              5 |               800 |                5 |               450 | Credit Card        |
|         1003 | 2026-01-10     | Rahul        | Delhi    | Electronics  | Mobile      |              3 |             25000 |                8 |             19000 | UPI                |
|         1004 | 12-Jan-2026    | Sneha        | Mumbai   | Accessories  | Keyboard    |              4 |              1500 |                5 |               900 | Debit Card         |
|         1005 | 15/01/2026     | Karan        | Pune     | Electronics  | Laptop      |              1 |             55000 |               15 |             42000 | Credit Card        |

Business Questions
- Create a data frame and find: Number of rows and columns, Data Types, Missing values, Number of unique cities, Number of unique products, Number of unique payment methods?
- Display only Customer, City, Products, Units_Sold, Selling_Price, Discount_Pct?
- Management doesn't need customer information for the final sales analysis. Drop the customer column?
- Add this transaction: Order_ID = 1041, Order_Date = 03/05/2026, Customer = Vikram, City = Mumbai, Category = Electronics, Product = Laptop, Units_Sold = 2,
  Selling_Price = 55000, Discount_Pct = 10, Cost_Per_Unit = 42000, Payment_Method = UPI.
- Convert the Order_Date into a proper datetime format despite the mixed formats. Then create: Order_Day, Order_Weekday, Order_Month, Order_Year.
- Create business metric Discounted_Selling_Price and Total revenue and Total Profit. Use the discounted selling price for actual revenue and profit?
- Create sales performance based on units sold: 10+ → Very High, 5–9 → High, 2–4 → Medium, Below 2 → Low?
- Find Number of orders per city, Number of orders per category, Number of orders per payment method, Number of orders per product?
- For each city calculate: Total Units Sold, Total Revenue, Total Profit, Average Discount. Sort by total revenue in descending order?
- For each product calculate: Total Units Sold, Total Revenue, Total Profit, Average Selling Price. Identify the best-performing product based on total profit?
- For each month calculate: Total Units Sold, Total Revenue, Total Profit. Sort the data in chronological order?
- Create a pivot table showing total revenue by City and Category?
- Create a pivot table showing total profit by city?
- Create one pivot table that shows for each city and category: Total Revenue, Total Profit, Total Units Sold?
- Find the transactions where discount is 10% or higher and total revenue is high. Then investigate does higher discounts reduce profit?
- Find the product that has the highest revenue but does not have the highest profit. Explain what data is causing the difference. Consider Units Sold, Discount, Selling Price, Cost Per Unit.
- Based on your analysis recommend:
    - Which city deserves more attention?
    - Which product/ category should be prioritized?
    - Which month performed the best?
    - What does pivot table analysis reveal that simple group does not?

 Solution
 ```Python
# Creating dataframe
import pandas as pd
df = pd.read_csv('Datasets/Retail Business Performance Analysis.csv')
print(f"Number of rows: {df.shape[0]}")
print(f"Number of columns: {df.shape[1]}")

# Datatypes
df.dtypes

# Missing values
df.isnull().sum(axis = 0)

# Number of Unique cities
df['City'].unique()

# Number of Unique Products
df['Product'].unique()

# Number of Unique payment methods
df['Payment_Method'].unique()

# Display only Customer, City, Products, Units_Sold, Selling_Price, Discount_Pct
df[['Customer','City','Product','Units_Sold','Selling_Price','Discount_Pct']]

# Drop customer information column
df.drop(columns = ['Customer'],inplace = True)
df

# Adding new customer record
df.loc[40,:] = [1041,'03/05/2026','Mumbai','Electronics','Laptop',2,55000,10,42000,'UPI']
df['Order_ID'] = df['Order_ID'].astype(int)
df['Units_Sold'] = df['Units_Sold'].astype(int)
df['Selling_Price'] = df['Selling_Price'].astype(int)
df['Discount_Pct'] = df['Discount_Pct'].astype(int)
df['Cost_Per_Unit'] = df['Cost_Per_Unit'].astype(int)
df

# Convert order date into proper date time format Order_Day, Order_Weekday, Order_Month, Order_Year.
df['Order_Date'] = pd.to_datetime(df['Order_Date'], format = "mixed")
df['Order_Day'] = df['Order_Date'].dt.day
df['Order_Weekday'] = df['Order_Date'].dt.day_name()
df['Order_Month'] = df['Order_Date'].dt.month_name()
df['Order_Year'] = df['Order_Date'].dt.year
df

# Create a business metric Discounted_Selling_Price, Total_Revenue and Total_Profit. Use dicounted selling price for actual profit.
df['Discounted_Selling_Price'] = df['Selling_Price'] * (1-df['Discount_Pct']/100)
# Converting to integer values
df['Discounted_Selling_Price'] = df['Discounted_Selling_Price'].astype(int)
df

# Calculating total revenue
df['Total_Revenue'] = df['Units_Sold'] * df['Discounted_Selling_Price']
df['Profit_Per_Unit'] = df['Discounted_Selling_Price'] - df['Cost_Per_Unit']
df['Total_Profit'] = df['Profit_Per_Unit'] * df['Units_Sold']
df

# Creating Sales Performance column based on following conditions: 10+ → Very High, 5–9 → High, 2–4 → Medium, Below 2 → Low.
def sales_performance(units_sold):
    if units_sold < 2:
        return "Low"
    elif units_sold <= 4:
        return "Medium"
    elif units_sold <= 9:
        return "High"
    else:
        return "Very High"
df['Sales_Category'] = df['Units_Sold'].apply(sales_performance)
df

# Find Number of Orders Per City
df.groupby("City").agg(Order_Count = ("Order_ID","count")).sort_values(by = ['Order_Count'],ascending = [False])

# Number of Orders Per Category
df.groupby("Category").agg(Order_Count = ("Order_ID","count")).sort_values(by=['Order_Count'], ascending = [False])

# Number of Orders payment method
df.groupby("Payment_Method").agg(Order_Count = ("Order_ID","count")).sort_values(by = ['Order_Count'], ascending = [False])

# Number of orders per product
df.groupby("Product").agg(Order_Count = ("Order_ID","count")).sort_values(by = ['Order_Count'], ascending = [False])

# Calculate Total Units Sold, Total Revenue, Total Profit, Average Discount. Sort by total revenue in descending order for each city
df.groupby("City").agg(
    Total_Units_Sold = ("Units_Sold","sum"),
    Total_Revenue = ("Total_Revenue","sum"),
    Total_Profit = ("Total_Profit","sum"),
    Average_Discount = ("Discount_Pct","mean")
).round(0).astype(int).sort_values(by = ['Total_Revenue'], ascending = [False])

# For each product calculate: Total Units Sold, Total Revenue, Total Profit, Average Selling Price. Identify the best-performing product based on total profit?
df.groupby("Product").agg(
    Total_Units_Sold = ("Units_Sold","sum"),
    Total_Revenue = ("Total_Revenue","sum"),
    Total_Profit = ("Total_Profit","sum"),
    Average_Selling_Price = ("Selling_Price","mean")
).astype(int).sort_values(by=['Total_Revenue'], ascending = [False])

# For each month calculate: Total Units Sold, Total Revenue, Total Profit. Sort the data in chronological order?
month_Order = ['January','February','March','April','May','June','July','August','September','October','November','December']
df['Order_Month'] = pd.Categorical(df['Order_Month'],categories = month_Order, ordered = True)
df.groupby("Order_Month").agg(
    Total_Units_Sold = ("Units_Sold","sum"),
    Total_Revenue = ("Total_Revenue","sum"),
    Total_Profit = ("Total_Profit","sum")
)

# Create a pivot table showing total profit by city
df.pivot_table(index = "City", values = "Total_Profit", aggfunc = "sum", fill_value = 0)

# Create a pivot table showing total revenue by City and Category
df.pivot_table(index = "Product", columns = "City", values = "Total_Revenue", aggfunc = "sum", fill_value = 0)

# Create one pivot table that shows for each city and category: Total Revenue, Total Profit, Total Units Sold?
df.pivot_table(index = "Category", columns = "City", values = ['Units_Sold','Total_Revenue','Total_Profit'], aggfunc = {
    "Units_Sold":"sum",
    "Total_Revenue":"sum",
    "Total_Profit":"sum"
}, fill_value = 0)

last 2 problems left
```
  
