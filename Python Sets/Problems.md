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
