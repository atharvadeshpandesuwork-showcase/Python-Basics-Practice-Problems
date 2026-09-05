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

Problem 5: You have recently joined soft sphere technologies as a Junior Data Analyst. Soft Sphere develops accounting and payroll software across India. Whenever a customer purchases the software, they receive a license key. Every license key is expected to be unique because it represents a single software activation. However, during a recent data migration from old licensing system some license keys were accidentally duplicated due to database synchronizations issues. Before activating the licenses for customers, the licensing team wants to verify whether the imported data contains duplicate license keys. Instead of manually checking thousands of records your manager has asked you to develop a program using python sets. The final team will help the licensing team identify whether the imported dataset is valid before releasing the software to the customers.

Sample Input
```Text
Enter total License Keys imported: 8
LIC1001
LIC1002
LIC1003
LIC1002
LIC1004
LIC1005
LIC1005
LIC1006
```

Sample Output
```Text
Software License Validation Report

Unique License Keys
{'LIC1001','LIC1002','LIC1003','LIC1004','LIC1005','LIC1006'}

Total Imported License Keys : 8
Unique License Keys : 6
Duplicate License Keys detected.
License database requires verification.
```

Solution:
```Python
no_license_keys = int(input("Enter the total number of license keys imported"))
license_keys = set()
for i in range(no_license_keys):
    keys = str(input(f"Enter license key {i+1}:"))
    license_keys.add(keys)
print("Software license validation report")
print("Unique License Keys")
print(license_keys)
print()
print(f"License keys imported: {no_license_keys}")
print(f"Unique license keys {len(license_keys)}")

if no_license_keys > len(license_keys):
    print("Duplicate License keys detected")
    print("Database requires validation")
else:
    print("All license keys are unique")
    print("Database validation sucessful")
```
```Text
Enter the total number of license keys imported 5
Enter license key 1: LIC101
Enter license key 2: LIC102
Enter license key 3: LIC103
Enter license key 4: LIC104
Enter license key 5: LIC101
Software license validation report
Unique License Keys
{'LIC103', 'LIC102', 'LIC101', 'LIC104'}

License keys imported: 5
Unique license keys 4
Duplicate License keys detected
Database requires validation
```

Problem 6: You have recently joined innovate Tech Solutions pvt ltd as a junior data analyst. The company is planning to bid for several new client projects such as Python, SQL, PowerBI, Tableau. Excel, Azure, AWA and Machine Learning. Before assigning employees to these projects the Human Resources (HR) and Resource Management teams want to prepare skill inventory report. Every employee submits their primary technical skill. Since many employees possess the same skill the HR database contains duplicate skill entries. For example: Python, SQL, Excel,
Python, Power BI, SQL, Excel, Tableau, Power BI. The management is not interested in how many employees know each skill. 

Instead, they want to know: "What unique technical skills are available in the organization?". This report will help the management determine whether the company has necessary expertise before accepting new client projects. Instead of manually removing duplicate skill sets your manager has instructed to use python sets. As a junior data analyst your responsibility is to automate the skill inventory report. The program should identify the unique technical skills available in the organization.

Sample Input
```Text
Enter total number of employees: 8
Python
SQL
Python
Excel
Power BI
SQL
Tableau
Excel
```

Sample Output
```Text
Employee Skill Inventory Report
Unique Skills
{'Python', 'SQL', 'Excel', 'Power BI', 'Tableau'}

Total Employees: 8
Unique Skills: 5
The company has a diverse technical skill set.
```

Solution
```Python
total_employees = int(input("Enter the total number of employees"))
skill_set = set()
for i in range(total_employees):
    skill_name = str(input("Enter the skill set of employees"))
    skill_set.add(skill_name)
print("Employee Skill inventory report")
print()
print("Unique Skills")
print(skill_set)
print()
print(f"Total Employees: {total_employees}")
print(f"No of unique skiils {len(skill_set)}")

if len(skill_set) > 5:
    print("The company has a diverse technical skill set.")
else:
    print("The company should invest in employee upskilling.")
```

```Text
Enter the total number of employees 6
Enter the skill set of employees SQL
Enter the skill set of employees PYTHON
Enter the skill set of employees POWERBI
Enter the skill set of employees TABLEAU
Enter the skill set of employees GOGGLE SHEETS
Enter the skill set of employees PANDAS
Employee Skill inventory report

Unique Skills
{'POWERBI', 'SQL', 'PYTHON', 'PANDAS', 'GOGGLE SHEETS', 'TABLEAU'}

Total Employees: 6
No of unique skiils 6
The company has a diverse technical skill set.
```

Problem 7: You have recently joined velocity retail pvt ltd as a Junior Data Analyst. The company operates 2 retail stores in Mumbai and in Pune. During the annual sales review the marketing department wants to understand the company's complete customer reach. Currently each store maintains their own record database.

Store A Customers: Rahul, Amit, Priya, Neha, Rohan
Store B Customers: Neha, Amit, Sneha, Karan, Pooja

Notice that some customers have shopped in both the stores. If the marketing team combines both customer lists, then duplicate customers will appear. This would lead to an incorrect estimate of the company's total customer base. The marketing manager has asked you to prepare a report showing the complete list of unique customers who have purchased from either store A or Store B. Instead of manually checking duplicate customer names your manager has suggested you use the union method in sets.

The final report will be used to measure:
- Measure company's total outreach.
- Plan nationwide marketing campaign.
- Estimate the total active customer base.
- Design loyalty programs.

As a junior data analyst your responsibility is to merge both customer database and generate a report containing only unique customers.

Sample Input
```Text
Store A
Rahul, Amit, Priya, Neha, Rohan

Store B
Neha, Amit, Sneha, Karan, Pooja,
```

Sample Output
```Text
Velocity Retail Customer Reach Report
Store A Customers
{'Rahul', 'Amit', 'Priya', 'Neha', 'Rohan'}

Store B Customers
{'Neha', 'Amit', 'Sneha', 'Karan', 'Pooja'}

Combined Customer Database
{'Rahul', 'Amit', 'Priya', 'Neha',
'Rohan', 'Sneha', 'Karan', 'Pooja'}

Total Unique Customers: 8
```
Solution
```Python
store_A_Cust_count = int(input("Enter the total number of customers for Store A"))
store_B_Cust_count = int(input("Enter the total number of customers for Store B"))
Store_A_Customers = set()
Store_B_Customers = set()

print("Store A Customers")
for i in range(store_A_Cust_count):
    customer_records = str(input(f"Enter name of Customer {i+1}:"))
    Store_A_Customers.add(customer_records)

print("Store B Customers")
for i in range(store_B_Cust_count):
    customer_records = str(input(f"Enter name of Customer {i+1}:"))
    Store_B_Customers.add(customer_records)
print()
print("Velocity retail customer reach report")
print("Store A Customers")
print(Store_A_Customers)
print()
print("Store B Customers")
print(Store_B_Customers)
print()
print("Combined Customer Base")
resultset = Store_A_Customers.union(Store_B_Customers)
print(resultset)
print(f"Total unique customers: {len(resultset)}")
```

```Text
Enter the total number of customers for Store A 2
Enter the total number of customers for Store B 2
Store A Customers
Enter name of Customer 1: Dipti
Enter name of Customer 2: Yogesh
Store B Customers
Enter name of Customer 1: Monica
Enter name of Customer 2: Atharva

Velocity retail customer reach report
Store A Customers
{'Yogesh', 'Dipti'}

Store B Customers
{'Monica', 'Atharva'}

Combined Customer Base
{'Yogesh', 'Monica', 'Atharva', 'Dipti'}
Total unique customers: 4
```
Interview Questions

Q1. What does the union() method do?
Ans: The union() method is used to combine two or more sets into a single set containing all unique elements from each set. Duplicate values are automatically removed because sets only store unique values. The union method returns a new set and does not modify the original set.

Q2. Why union() is useful in customer analytics?
Ans: The union() method is useful in customer analytics because it combines customer data from multiple stores into a single set of unique customers. If the same customer has made purchases from one or more store, the union() method automatically removes duplicate entries and returns only one occurrence of that customer. This helps the company determine its total unique customer base, which is useful for marketing campaigns, customer reach analysis and loyalty program planning. 

Q3. If the same customer shops at both stores, how many times will they appear in the union?
Ans: If the customer shops at both stores they will appear only once in union. This is because union only returns a set elements containing only unique elements. Since sets do not allow duplicate values the customers name will only be included once regardless how many stores they have shopped at.

Q4. What is the difference between union() and simply adding two lists together?
Ans: The union method combines 2 or more sets and returns a new set containing only unique elements. Since sets automatically ignore duplicate values, no additional logic is required to remove duplicates. If we simply add two lists together using the (+) operator all the elements in the lists are combined including duplicate values. If we need only unique elements we must write additional logic to identify and remove duplicate elements.

Q5. Can union() be performed on Lists? If not, why?
Ans: No union() cannot be performed on lists because it is a method of Set data structure and not the List data structure. List do not have a union method. If we need to combine two lists and remove duplicates, we must write additional logic or convert the lists into sets before using union().

Q6. Give another real-world example where union() would be useful in data analysis?
Ans: A good example is combining customer data from online store and a physical store. Some customers may shop through both the channels. Using union() method allow us to combine both customer datasets and obtain a list of unique customers. This helps business understand its total customer reach and plan marketing campaigns more effectively. 

Problem 8: You have recently joined velocity pvt limited as a junior data analyst. The company operates two retail store in Mumbai and Pune. At the end of the financial quarter the marketing department reviews customer purchasing behavior to identify company's most loyal customers. Management believes that customers who have purchased from both stores are more engaged with the brand and are eligible for: 
- Premium membership programs.
- Exclusive discount coupons.
- Early product launch invitations.
- Customer loyalty rewards.

Each store maintains its own customer database.

Store A Customers: Rahul, Amit, Neha, Priya, Rohan, Sneha
Store B Customers: Neha, Amit, Karan, Pooja, Sneha, Riya

The marketing manager is not interested in:
- Customers who only purchased from one store.
- The complete customer database.

Instead, the management wants to answer one specific question: "Which customer have made purchases from Store A and Store B". These customers will automatically qualify for company's premium loyalty program. Instead of manually comparing the names your manager asked you to use the python's intersection method. As a junior data analyst your responsibility is to identify the customers who are common to both stores and prepare the premium customer report.

Sample Input
```Text
Store A: Rahul, Amit, Neha, Priya, Rohan, Sneha

Store B: Neha, Amit, Karan, Pooja, Sneha, Riya
```
Sample Output
```Text
Velocity Retail Premium Customer Report

Store A Customers
{'Rahul', 'Amit', 'Neha', 'Priya', 'Rohan', 'Sneha'}

Store B Customers
{'Neha', 'Amit', 'Karan', 'Pooja', 'Sneha', 'Riya'}

Premium Customers
{'Amit', 'Neha', 'Sneha'}
Total Premium Customers: 3
```

Solution:
```python
store_A_Cust_count = int(input("Enter the total number of customers for Store A"))
store_B_Cust_count = int(input("Enter the total number of customers for Store B"))
Store_A_Customers = set()
Store_B_Customers = set()

print("Store A Customers")
for i in range(store_A_Cust_count):
    customer_records = str(input(f"Enter name of Customer {i+1}:"))
    Store_A_Customers.add(customer_records)

print("Store B Customers")
for i in range(store_B_Cust_count):
    customer_records = str(input(f"Enter name of Customer {i+1}:"))
    Store_B_Customers.add(customer_records)
print()
print("Velocity retail customer reach report")
print("Store A Customers")
print(Store_A_Customers)
print()
print("Store B Customers")
print(Store_B_Customers)
print()
print("Combined Customer Base")
resultset = Store_A_Customers.union(Store_B_Customers)
print(resultset)
print(f"Total unique customers: {len(resultset)}")
```
```Text
Enter the total number of customers for Store A 2
Enter the total number of customers for Store B 2
Store A Customers
Enter name of Customer 1: Dipti
Enter name of Customer 2: Yogesh
Store B Customers
Enter name of Customer 1: Monica
Enter name of Customer 2: Atharva

Velocity retail customer reach report
Store A Customers
{'Yogesh', 'Dipti'}

Store B Customers
{'Monica', 'Atharva'}

Combined Customer Base
{'Yogesh', 'Monica', 'Atharva', 'Dipti'}
Total unique customers: 4
```

Problem 9: You have recently joined Tech Nova Solutions Pvt Ltd as a data analyst. The company recently conducted two mandatory training programs for all employees: Python for data analysis and SQL for data analysis. To be eligible for the upcoming Business Intelligence Project an employee must have successfully completed both the programs. The HR department maintains two seprate databases:
- Python Training Participants: Employees who completed python training.
- SQL Training Participants: Employees who completed SQL training.
Management now wants to identify employees who have completed both the training programs. These employees will be shortlisted for the new project. Instead of manually comparing employee names your manager has asked to use the pythons intersection method. As a junior data analyst your role is to generate the project eligibility report. Only employees who appear in both training records are included in the final report.

Sample Input
```Text
Python Training
Rahul, Amit, Neha, Sneha, Karan, Pooja

SQL Training
Neha, Rahul, Rohan, Sneha, Anjali
```

Sample Output
```Text
Project Eligibility Report

Python Training Participants
{'Rahul', 'Amit', 'Neha', 'Sneha', 'Karan', 'Pooja'}

SQL Training Participants
{'Neha', 'Rahul', 'Rohan', 'Sneha', 'Anjali'}

Employees Eligible for the Project
{'Rahul', 'Neha', 'Sneha'}
Total Eligible Employees: 3
```

Solution
```python
python_training = set()
sql_training = set()

while True:
    python_records = str(input("Enter the name of employees who completed the python course"))
    if python_records.lower() == "done":
        break
    python_training.add(python_records)

while True:
    sql_records = str(input("Enter the name of the employees who have completed the SQL course "))
    if sql_records.lower() == "done":
        break
    sql_training.add(sql_records)

print("Project eligibility report")
print("Python Training Participants")
print(python_training)
print("SQL Training Participants")
print(sql_training)
print("Employees eligible for project")
print(python_training.intersection(sql_training))
print(f"Total eligible employees: {len(python_training.intersection(sql_training))}")
```

```Text
Enter the name of employees who completed the python course Rahul
Enter the name of employees who completed the python course Amit
Enter the name of employees who completed the python course Neha
Enter the name of employees who completed the python course Sneha
Enter the name of employees who completed the python course Karan
Enter the name of employees who completed the python course Pooja
Enter the name of employees who completed the python course done

Enter the name of the employees who have completed the SQL course Neha
Enter the name of the employees who have completed the SQL course Rahul
Enter the name of the employees who have completed the SQL course Rohan
Enter the name of the employees who have completed the SQL course Sneha
Enter the name of the employees who have completed the SQL course Anjali
Enter the name of the employees who have completed the SQL course done

Project eligibility report

Python Training Participants
{'Neha', 'Rahul', 'Pooja', 'Karan', 'Sneha', 'Amit'}

SQL Training Participants
{'Neha', 'Rahul', 'Rohan', 'Sneha', 'Anjali'}

Employees eligible for project
{'Neha', 'Rahul', 'Sneha'}
Total eligible employees: 3
```

Problem 10: You have joined Prime Mart Retail Pvt ltd as a Junior Data Analyst. The company wants to identify customers who have purchased products last year but did not make any purchases this year. The marketing team believes that these customers may have switched to its competitors. To improve customer retention they want to launch a "Win Back Campaign" offering special discounts to these customers.

The company has two customer databases:
- Last year's Customers
- This year's customers
Your task is to identify customers who have made purchases in the last year and not this year. Instead of manually comparing both the customer lists your manager has asked to use the python's difference() method. Business Question: "Which customer purchased last year but did not purchase this year?"

Sample Output
```Text
Customer Retention Report

Last Year's Customers
{...}

This Year's Customers
{...}

Inactive Customers
{...}

Total Inactive Customers: X
```

Solution
```python
ly_customer = set()
cy_customer = set()

while True:
    customer = str(input("Enter customer who made purchases LY: "))
    if customer.lower() == "done":
        break
    ly_customer.add(customer)

while True:
    customer_cy = str(input("Enter customer who made purchases CY: "))
    if customer_cy.lower() == "done":
        break
    cy_customer.add(customer_cy)
print("\n Customer retention report")
print("\n Last Year Customers")
print(ly_customer)
print("\n Current Year Customers")
print(cy_customer)
print("\n Inactive customers")
inactive_customers = cy_customer.difference(ly_customer)
print(f"\n {inactive_customers}")
print(f"Total Inactive customers: {len(inactive_customers)}")
```

```Text
Enter customer who made purchases LY:  Atharva
Enter customer who made purchases LY:  Anjali
Enter customer who made purchases LY:  Sujat
Enter customer who made purchases LY:  Usha
Enter customer who made purchases LY:  done

Enter customer who made purchases CY:  Kshitij
Enter customer who made purchases CY:  Ratna
Enter customer who made purchases CY:  Atharva
Enter customer who made purchases CY:  Anjali
Enter customer who made purchases CY:  Sujat
Enter customer who made purchases CY:  Usha
Enter customer who made purchases CY:  done

 Customer retention report

 Last Year Customers
{'Atharva', 'Anjali', 'Sujat', 'Usha'}

 Current Year Customers
{'Atharva', 'Usha', 'Kshitij', 'Sujat', 'Anjali', 'Ratna'}

 Inactive customers

 {'Kshitij', 'Ratna'}

Total Inactive customers: 2
```

Interview Questions

Q1. What does the difference() method do?
Ans: The difference method returns a new set containing elements that are present in the first set but not in the second set and vice versa. The difference method compares the 2 sets and displays the elements that uncommon from the first and the second set. This method will not modify the original sets.

Q2. Why is difference() useful in customer retention analysis?
Ans: The difference() method is useful because it specifies the difference between the two datasets. The difference method is useful in customer retention analysis becuase it helps identify customers who have purchased in the previous year but did not make any purchase this year. These customers may have stopped buying from the company or switched to competitors. The business can use this information to launch customer retention campaigns, offer discounts or send personalized promotions to encourage them to retrun. 

Q3. If a customer appears in both years, will they appear in the difference?
Ans: No, if the customer appears in both previous year and current year, they will not appear in difference because the difference() method only displays the customers that are present in set A but absent in set B. Customers that are common to both the sets are removed from the result.

Q4. What is the difference between union() and difference()?
Ans: The union() method combines two or more sets and returns a new set containing all unique elements from those sets. The difference() method returns a new set containing only the elements that are present in the first set but absent from the second set. Unlike union(), difference() is directional so changing the order of the set changes the result.

Q5. Give another business use case for difference()?
Ans: A real world use case would be the use of difference() method in banking. Suppose a bank issues credit cards to customers in January and wants to identify customers who have not activated their cards in February. By performing jan.difference(feb) the bank can identify customers who were issued cards but did not activate them. This helps bank to launch reminder campaigns or offer incentives to increase card activation rates.
