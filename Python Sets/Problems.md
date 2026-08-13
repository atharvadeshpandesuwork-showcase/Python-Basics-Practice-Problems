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
