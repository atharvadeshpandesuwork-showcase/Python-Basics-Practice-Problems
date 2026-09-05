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

Why is a dictionary a better choice than a list for storing product prices?
What is the key and what is the value in this program?
How do you retrieve the price of a product from a dictionary?
What happens if you add the same product name twice?
Why are unique keys important in a dictionary?
