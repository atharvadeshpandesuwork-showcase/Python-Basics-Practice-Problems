Problem 1: You have recently joined Vertex Solutions Pvt. Ltd. as a Junior Data Analyst. The Human Resources (HR) department maintains employee information such as: Employee ID, Employee Name, Department, Salary. Currently, the HR team records employee details on paper, making it difficult to retrieve information quickly. Your manager wants to digitize this process using Python. Since each employee attribute has a specific meaning (Employee ID, Name, Department, Salary), your manager has decided that a dictionary is the most appropriate data structure. As the Junior Data Analyst, your task is to create a program that stores the details of one employee using a dictionary and generates an Employee Information Report.

Sample Input
```Text
Enter Employee ID: 101
Enter Employee Name: Rahul Sharma
Enter Department: Finance
Enter Salary: 65000
```

Sample Output
```Text
Employee Dictionary

{
'Employee ID': 101,
'Employee Name': 'Rahul Sharma',
'Department': 'Finance',
'Salary': 65000
}

Employee Information Report

Employee ID: 101
Employee Name: Rahul Sharma
Department: Finance
Salary: 65000
```
Solution:

```Python
employee_details = dict()

employee_details["Employee_ID"] = str(input("Enter employee_id: "))
employee_details["Employee_Name"] = str(input("Enter employee_name: "))
employee_details["Department"] = str(input("Enter department of employee: "))
employee_details["Salary"] = str(input("Enter employee salary: "))

print(employee_details)
print()
print("Employee Information Report")
print(f"Employee ID: {employee_details.get('Employee_ID')}")
print(f"Employee Name: {employee_details.get('Employee_Name')}")
print(f"Department: {employee_details.get('Department')}")
print(f"Department: {employee_details.get('Salary')}")
```

```Text
Enter employee_id:  101
Enter employee_name:  Atharva
Enter department of employee:  Information Technology
Enter employee salary:  500000
{'Employee_ID': '101', 'Employee_Name': 'Atharva', 'Department': 'Information Technology', 'Salary': '500000'}

Employee Information Report
Employee ID: 101
Employee Name: Atharva
Department: Information Technology
Department: 500000
```

Problem 2: You have recently joined Next Gen Supermarket Pvt Ltd as a Junior Data Analyst. The supermarket sells thousands of products every day. The Billing department often needs to quickly check the price of a product before generating invoices. Instead of searching through a list of products manually, the company wants to store the product details in a dictionary where:
- Key = Product Name
- Value = Product Price

This allows employees to retrieve the price of any product instantly using its name. As a junior data analyst, you have been asked to develop a simple Product Price Lookup system.

Sample Input
```Text
Enter number of products: 4

Laptop: 65000
Mouse: 750
Keyboard: 1800
Monitor: 12000

Enter product name to search: Keyboard
```

Sample Output
```Text
Product Dictionary

{
'Laptop': 65000,
'Mouse': 750,
'Keyboard': 1800,
'Monitor': 12000
}

Product Price Report
Product Name: Keyboard
Price: ₹1800
```

Solution:

```Python
products = int(input("Enter the number of products"))
products_details = dict()
for i in range(products):
    product_name = input(f"Enter the name of product{i+1}: ")
    product_price = str(input(f"Enter the price of product{i+1}: "))
    products_details[product_name] = product_price
print(products_details)
print("\n Product price report")
search_price = input("Enter the name of the product to get price")
print(f"Product: {search_price}")
print(f"Price: {products_details.get(search_price)}")
```

```Text
Enter the number of products 2
Enter the name of product1:  Laptop
Enter the price of product1:  1000
Enter the name of product2:  Mobile
Enter the price of product2:  500
{'Laptop': '1000', 'Mobile': '500'}

 Product price report
Enter the name of the product to get price Laptop
Product: Laptop
Price: 1000
```

Interview Questions

Q1. Why is a dictionary a better choice than a list for storing product prices?
Ans: A dictionary is a better choice than list for storing products because:
- Every product has an associated key and every key in the dictionary must be unique. If the same key is entered again, Python updates the existing value instead of creating a duplicate key. 
- If 2 different products have the same price, there is a less chance of confusion because we retrieve the price using the name(key), not searching for the price itself.
- If the data is stored in a list duplicate price could make it difficult to identify which product has a particular price belongs to without additional searching.
- Since dictionary keys are unique duplicate records for the same products are avoided. If a product is entered again its price is updated rather than creating another record. This helps maintain consistent and non-redundant product information. 

Q2. What is the key and what is the value in this program?
Ans: In this program the product name is used as the key and the price is stored as its corresponding value. The key uniquely identifies each product while the value represents the price associated with that product.

Q3. How do you retrieve the price of a product from a dictionary?
Ans: The price of the product is retrieved from a dictionary using its key. We use the get() method and pass the product name as an argument. The method returns the value associated with that key which is the products price. 

Q4. What happens if you add the same product name twice?
Ans: If the same product name (key) is added again Python does not create a duplicate entry. Instead it updates the value associated with that key. The previous value will be replaced with the new value.

Q5. Why are unique keys important in a dictionary?
Ans: Unique keys are important because each key uniquely identifies a value in the dictionary. If the same key is added again Python updates the existing value instead of creating a new entry. This prevents duplicate keys and ensures that each record has a unique identifier and avoids inconsistencies caused by having multiple entries for the same key. However if a key is overwritten accidentally the previous value is lost.

Problem 3: You have joined ABC Technologies as a junior data analyst. The Hr department maintains salary records of employees. Managers frequently ask Hr questions like: 
- What is rahuls salary ?
- How much does amit earn ?
Instead of searching through excel sheets manually HR wants a Python program that can quickly retrieve an employees salary using employee's name. Your task is to build this system using a dictionary.

Sample Input
```Text
Enter number of employees: 4
Rahul: 65000
Amit: 55000
Neha: 72000
Pooja: 60000

Enter employee name: Neha
```

Sample Output
```Text
Employee Salary Database

{'Rahul': 65000,
 'Amit': 55000,
 'Neha': 72000,
 'Pooja': 60000}

Employee Salary Report

Employee Name: Neha
Salary: ₹72000
```

Solution

```Python

total_employees = int(input("Enter the number of employees: "))
employee_details = dict()
for i in range(total_employees):
    employee_name = str(input(f"Enter the name of employee{i+1}: "))
    employee_salary = int(input(f"Enter the salary of employee{i+1}: "))
    employee_details[employee_name] = employee_salary
print("\n Employee salary database")
print(employee_details)
print("Employee Salary database")
record = str(input("Enter the employee name whose salary needs to be retrieved: "))
print(f"Employee name: {record}")
print(f"Employee salary: {employee_details.get(record)}")
```

```Text
Enter the number of employees:  2

Enter the name of employee1:  Atharva
Enter the salary of employee1:  5000

Enter the name of employee2:  Sujat
Enter the salary of employee2:  6000

 Employee salary database
{'Atharva': 5000, 'Sujat': 6000}

Employee Salary database

Enter the employee name whose salary needs to be retrieved:  Atharva

Employee name: Atharva
Employee salary: 5000
```

Q1. How to update the value of the existing key?
Ans: To update the value of an existing key in a dictionary use the assignment operator with the key. If the key already exists python replaces the old value with the new value. 
Example: employee_salary['Rahul'] = 70000

Q2. What happens if you update a key that already exists?
Ans: If a key already exist in a dictionary we assign a new value to it, Python updates the value associated with the key. The previous value is overwritten and no duplicate key is created.

Q3. Can dictionaries have duplicate values after an update?
Ans: No. A dictionary cannot have duplicate keys. If a new value is assigned to an existing key Python updates the value associated with that key instead of creating another key. As a result the old value is replaced and the dictionary continues to only contain one instance of that key.

Q4. Why is updating by key efficient?
Ans: Updating by key is efficient in dictionaries because dictionaries allow direct access to values using their keys. There is no need to search through all the records to find the correct entry. This makes updates faster and maintain accurate and consistent data by modifying the intended record.

Q5. In what business scenarios would updating dictionary values be useful?
Ans: A good business case is a laptop store where the prices of models of laptop change frequently due to market demand or supplier costs. The laptop model can be used as a key and the price as value. Whenever the price changes the dictionary can be updated using the same key ensuring the latest price is stored without creating duplicate records. This helps maintain accurate and consistent pricing information.

Problem 4: You are working as a junior data analyst at bright future academy, which conducts internal assessments of students. The academic department currently stores student performance information in Python dictionary. Each students name is used as the key while their overall assessment score is store as the value. 
Example:

student_marks = {
    "Rahul": 85,
    "Amit": 92,
    "Neha": 78,
    "Sneha": 90
}

The management wants a simple reporting program that can present this information in different ways. They want to know:
- Which students are included in the assesment?
- What marks have been recorded?
- What marks belong to each student?

You will use this dictionary methods to generate these different views of the same dataset. Build a student performance reporting using a dictionary. Your program should allow the academic department to enter student records and then generate a structured report.

Sample Output
```Text
Student Performance Database
{'Rahul': 85, 'Amit': 92, 'Neha': 78, 'Sneha': 90}

Students Participating in Assessment
dict_keys(['Rahul', 'Amit', 'Neha', 'Sneha'])

Assessment Marks
dict_values([85, 92, 78, 90])

Student Performance Report
Rahul: 85
Amit: 92
Neha: 78
Sneha: 90
```

Solution

```Python
student_count = int(input("Enter the number of students"))
student_details = dict()
for i in range(student_count):
    student_name = str(input(f"Enter the name of the student {i+1}: "))
    student_marks = int(input(f"Enter the marks of student {i+1}: "))
    student_details[student_name] = student_marks
print("Student performance database")
print(student_details)
print()
print("Students Participating in assesment")
print(f"dict_keys: {student_details.keys()}")
print()
print("Assesment Marks")
print(f"dict_values: {student_details.values()}")
print()
print("Student performance report")
for student_name,student_marks in student_details.items():
    print(f"{student_name}:{student_marks}")
```

```Text
Enter the number of students 2

Enter the name of the student 1:  Rahul
Enter the marks of student 1:  85

Enter the name of the student 2:  Amit
Enter the marks of student 2:  92

Student performance database
{'Rahul': 85, 'Amit': 92}

Students Participating in assesment
dict_keys: dict_keys(['Rahul', 'Amit'])

Assesment Marks
dict_values: dict_values([85, 92])

Student performance report
Rahul:85
Amit:92
```
