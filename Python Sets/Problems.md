Problem 1: You have recently joined ABC Technologies Pvt Ltd as a Junior data analyst. The Human Resources department is preparing an organizational report for company annual board meeting. Currently HR maintains records in Excel. Every employee belongs to one department such as: IT, HR, Finance, Sales, Marketing, Operations. Since multiple employees work in the same department the excel file contains many duplicate department names.

The HR manager wants to know how many unique departments currently exist in the organization. Initially an intern attempted to solve this problem using a list, but the report contained duplicate department names making it difficult to identify actual number of departments. Your manager has asked to use python sets because they automatically remove duplicate values. The final report will be presented to senior management to understand the company's organizational structure. As a data analyst your responsibility is to develop a program that automatically identifies unique departments in the company.

Sample Input
```Text
Enter the total number of employees: 10
Employee 1: IT
Employee 2: HR
Employee 3: IT
Employee 4: Finance
Employee 5: Sales
Employee 6: Finance
Employee 7: IT
Employee 8: Marketing
Employee 9: HR
Employee 10: Sales
```

Sample Output
```Text
Company Department Report
Unique Departments
{'IT', 'Finance', 'Sales', 'Marketing', 'HR'}
Total Employees: 10
Unique Departments: 5
```
Solution
```Python
employee_dept = set()
employee_count = int(input("Enter the number of employee"))
for i in range(employee_count):
    emp_dept_record = str(input(f"Enter the department of employee {i+1}"))
    employee_dept.add(emp_dept_record)
print("Company Department Report")
print(employee_dept)
print(f"Total Employees: {employee_count}")
print(f"Unique Departments: {len(employee_dept)}")
```
```Text
Enter the number of employee 5
Enter the department of employee 1 IT
Enter the department of employee 2 IT
Enter the department of employee 3 HR
Enter the department of employee 4 Operations
Enter the department of employee 5 Operations
Company Department Report
{'HR', 'Operations', 'IT'}
Total Employees: 5
Unique Departments: 3
```

Problem 2: You have recently joined velocity retail Pvt Ltd as a Junior data analyst. The company operates an online shopping platform that delivers across India. Everyday thousands of customers place orders from cities. During a weekly business review meeting the sales manager asks a simple question: "How many unique cities placed order this week?". The raw sales data contain duplicate city names because multiple customers order from the same city. If the data is stored in the list duplicate cities remain. Your Analytics manager has asked you to use python sets to automatically identify unique customer cities. The final report will help the marketing team decide where to launch advertising campaigns.

Sample Input
```Text
Enter total customer orders: 10
Mumbai
Pune
Mumbai
Delhi
Bangalore
Delhi
Hyderabad
Pune
Mumbai
Chennai
```

Sample Output
```Text
Customer City Report
Unique Cities
{'Mumbai', 'Delhi', 'Pune', 'Bangalore', 'Hyderabad', 'Chennai'}
Total Orders: 10
Unique Cities: 6
```

Solution
```Python
orders_city = set()
order_count = int(input("Enter the number of orders recieved in week"))
for i in range(order_count):
    city_record = str(input(f"Enter the city of order{i+1}"))
    orders_city.add(city_record)
print("Customer City Report")
print()
print("Unique Cities")
print(orders_city)
print()
print(f"Total Orders: {order_count}")
print(f"Unique Cities {len(orders_city)}")
```
```Text
Enter the number of orders recieved in week 5
Enter the city of order1 Mumbai
Enter the city of order2 Pune
Enter the city of order3 Nagpur
Enter the city of order4 Nasik
Enter the city of order5 Aurangabad
Customer City Report

Unique Cities
{'Nasik', 'Mumbai', 'Nagpur', 'Aurangabad', 'Pune'}

Total Orders: 5
Unique Cities 5
```

Interview Questions

Q1. Why is set ideal for finding unique cities?

Ans: A set is the ideal data structure for finding unique cities because it automatically stores only unique values. If duplicate city names are added Python ignores the duplicates and keep only one value for each city. This allows us to easily determine the total number of unique cities without writing additional logic to remove duplicates.

Q2. What happens if we write "Mumbai" 100 times in a set?

Ans: Python does not keep multiple copies of a single value in a set. When you try to add "Mumbai" again it already contains the value so nothing changes. Therefore when duplicate value is added in a set Python ignores it since it already exists in the set.

Q3. Can a Set store different datatypes?

Ans: Yes a set can store different data types together, provided the elements are immutable. For example integers, strings, floats, Booleans, and tuples can all be stored in the same set. Mutable objects like lists and dictionaries cannot be stored because they are unshashable.

Q4. Why sets are unordered?

Ans: Sets are unordered because they are implemented using a hash table. Their primary purpose is to store unique elements and provide fast membership checking, not to preserve insertion order. Therefore the order of elements in sets is not guaranteed.

Problem 3: You have recently joined tech mart ltd as a junior data analyst. Tech Mart is one of India's fastest growing retail companies selling products across multiple categories such as: Electronics, Clothing, Grocery, Furniture, Sport's, Books, Home Appliances, Beauty and personal care. Every day thousands of products are sold through the company's website. At the end of each month sales and inventory departments generate reports to understand which product categories are currently being sold. However there is a challenge. Since thousands of products are sold the sales database contains same category multiple times.

Example:
```Text
Electronics, Clothing, Electronics, Furniture, Books, Electronics, Sports, Furniture, Books, Clothing
```

The inventory manager is not interested in how many products were sold in each category. Instead, management wants a report answering the following business question:

"Which unique product categories are available in our sales data?"

This information helps the company:
- Understand the variety of products being sold.
- Plan warehouse storage.
- Identify product categories.
- Prepare inventory planning reports.
- Analyze category wise business expansion opportunities.

Instead of manually checking for duplicate category names your manager has asked you to develop a python program to only display unique categories.

Sample Input
```Text
Enter total products sold: 10

Electronics
Clothing
Electronics
Furniture
Books
Electronics
Sports
Books
Furniture
Clothing
```
Sample Output
```Text
TechMart Product Category Report

Unique Categories
{'Furniture', 'Books', 'Sports', 'Electronics', 'Clothing'}
Total Products Sold: 10
Unique Product Categories: 5
```
Solution
```python
products_sold = int(input("Enter the total number of products sold"))
products_category = set()
for i in range(products_sold):
    product_record = str(input(f"Enter the category of product{i+1}"))
    products_category.add(product_record)
print("TechMart Product Category Report")
print()
print("Unique Categories")
print(products_category)
print()
print(f"Total Products Sold {products_sold}")
print(f"Unique product categories {len(products_category)}")
```
```Text
Enter the total number of products sold 5
Enter the category of product1 Electronics
Enter the category of product2 Clothes
Enter the category of product3 Electronics
Enter the category of product4 Books
Enter the category of product5 Sports
TechMart Product Category Report

Unique Categories
{'Electronics', 'Books', 'Sports', 'Clothes'}

Total Products Sold 5
Unique product categories 4
```

Interview Questions

Q1. Why set is a better choice than list for this problem?

Ans: A set is a better choice than list because the business requirement is to identify unique product categories. A set automatically stores only unique values and ignores duplicate entries, so we don't need to write any additional logic to remove duplicates. A list allows duplicate values, which would require extra processing to identify unique categories. Therefore a set provides a simpler and more efficient solution for this problem.

Q2. What happens if "Electronics" is entered 1,000 times?

Ans: If electronics is stored a 1000 times, then the set will contain only one "Electronics". When python encounters duplicate values, it does not add them because a set stores only unique elements. Therefore, regardless of how many times "Electronics" is entered it will appear only once in a set.

Q3. Why doesn't a Set maintain the order of insertion?

Ans: Sets do not maintain the order of insertion because they are used to provide fast lookup, insertion, and duplicate checking rather than preserving the order in which the elements were added. Python stores set elements using a hash table which organizes elements for efficient access instead of sequential order.

Q4. Can we access the first category using categories[0]?

Ans: No we cannot access the elements using indexing in a set because sets are unordered and do not maintain index positions. Internally python stores the elements using a hash table for faster lookup and duplicate checking rather than sequential indexing. There expressions like categories[0] are not allowed and will raise a TypeError.

Q5. If the company has 1,00,000 products but only 12 categories, why is a Set an efficient data structure for generating this report?

Ans: A set is a efficient data structure for this problem because the company wants to identify unique product categories. Even if there are 1,00,000 products, python stores each category only once and automatically ignores the duplicate entries. This allows us to quickly determine all the unique categories without writing additional logic to remove duplicates. As a result the code is simpler more efficient and easier to maintain. 

Q6. What is the difference between add() (Set) and append() (List)?

Ans: The append() method is used to add an element at the end of the list. Since lists in python allows duplicate values it is important to maintain the order of insertion of every element being stored. The add() method is used in sets to insert a new element into the set. If the element already exists then python ignores it because sets store only unique values.

Problem 4: You have recently joined Vortex Technologies Pvt Ltd as a Junior Data Analyst. The HR department has started onboarding new employees. Every new Employee is assigned a unique employee ID before joining the company. Due to manual data entry by different HR executives the same employee ID is sometimes entered more than once. Duplicate employee id create serious business problems because payroll attendance and employee records rely on each employee having a unique identifier.

Instead of manually checking every employee ID your manager has suggested using python sets since they store only unique values. The report generated by your program will quickly help the HR identify how many unique employee records have been entered. As a junior data analyst you need to develop a validation system that automatically removes duplicate employee ID and generates a summary report.

Sample Input
```Text
Enter total employee records: 8
EMP101
EMP102
EMP103
EMP101
EMP104
EMP102
EMP105
EMP106
```

Sample Output
```Text
Employee ID Validation Report
Unique Employee IDs
{'EMP101', 'EMP102', 'EMP103', 'EMP104', 'EMP105', 'EMP106'}
Total Records Entered: 8
Unique Employee IDs: 6
Duplicate Employee IDs were detected.
```

Solution:
```Python
employee_details = set()
number_employees = int(input("Enter total number of employee records"))
for i in range(number_employees):
    record = str(input(f"Enter the Emp Id for Employee {i+1}"))
    employee_details.add(record)

print("Employee ID Validation Report")
print("Unique Employee ID's")
print(employee_details)
print(f"Total number of records entered: {number_employees}")
print(f"Unique Employees: {len(employee_details)}")

if number_employees > len(employee_details):
    print("Duplicate Employee ID were detected")
else:
    print("All employee ID are unique")
```
```Text
Enter total number of employee records 8
Enter the Emp Id for Employee 1 EMP101
Enter the Emp Id for Employee 2 EMP102
Enter the Emp Id for Employee 3 EMP103
Enter the Emp Id for Employee 4 EMP101
Enter the Emp Id for Employee 5 EMP104
Enter the Emp Id for Employee 6 EMP102
Enter the Emp Id for Employee 7 EMP105
Enter the Emp Id for Employee 8 EMP106
Employee ID Validation Report
Unique Employee ID's
{'EMP106', 'EMP105', 'EMP104', 'EMP103', 'EMP101', 'EMP102'}
Total number of records entered: 8
Unique Employees: 6
Duplicate Employee ID were detected
```

Interview Questions

Q1. Why is set useful for validating employee ID?

Ans: A set is useful for validating employee ID because it stores only unique values. If duplicate Employee ID is entered, Python automatically ignores it instead of storing another copy. This eliminates the need to write additional logic to remove duplicate Employee ID making the validation process simpler and more efficient.

Q2. How can you determine whether duplicate employee ID's were entered?

Ans: We can determine whether duplicate employee ID,s were entered by comparing the total number of Employee records entered with the number of unique employee ID stored in the set using len() function. If the total number of records is greater than the number of unique employee ID's it means duplicate employee ID,s were entered. If both values are equal then all employee ID's are unique.

Q3. Why compare len(set) with the total number of records?

Ans: We compare the length of the Set with the total number of employee records entered to determine whether duplicate Employee IDs exist. A Set stores only unique values, while the total number of records includes both unique and duplicate entries. If the length of the Set is smaller than the total number of records, it means some Employee IDs were duplicated. If both values are equal, then every Employee ID is unique.

Q4. What would happen if every Employee ID is unique?

Ans: If every Employee ID is unique, then every Employee ID entered by the user will be stored in the Set because there are no duplicate values to ignore. As a result, the length of the Set will be equal to the total number of employee records entered, and the program will display that all Employee IDs are unique.

Q5. Could this validation be implemented using a List? If yes, what additional work would be required?

Ans: Yes, this validation can also be implemented using a List. However, a List allows duplicate values, so it will store every Employee ID, including duplicates. To detect duplicate Employee IDs, we would need to write additional logic to compare each Employee ID with the others or maintain another data structure to track which IDs have already been seen. This makes the solution more complex and less efficient than using a Set, which automatically stores only unique values.
