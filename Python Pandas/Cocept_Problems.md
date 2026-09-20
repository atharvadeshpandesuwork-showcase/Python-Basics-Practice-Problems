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
