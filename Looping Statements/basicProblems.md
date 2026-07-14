Problem 1: A company wants to send a welcome message to its newly hired employees. Instead of writing the message multiple times manually, HR wants the system to print it automatically. Write a Python program that asks the user: Number of new employees. Then print the following message that many times: "Welcome to Infosys! Wishing you a successful career."

Using For Loop

``` Python
employee_count = int(input("Enter the number of employees"))
for i in range(0,employee_count,1):
    print("Welcome to Infosys! Wishing you a successful career.")
```
``` Text
Enter the number of employees 5
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
```
Using While Loop

``` Python
employee_count = int(input("Enter the number of employees"))
counter = 0
while counter < employee_count:
    print("Welcome to Infosys! Wishing you a successful career.")
    counter = counter + 1
```
``` Text
Enter the number of employees 5
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
Welcome to Infosys! Wishing you a successful career.
```

Problem 2: The HR department wants to calculate the total salary payout for all newly hired employees. Instead of calculating each employee's salary separately, HR wants a program that accepts multiple salaries and calculates the total payroll. Write a Python program that:
- Accepts the number of employees.
- Accepts the salary of each employee.
- Calculate: Total Salary, Average Salary.

Using For Loop

``` Python
employee_count = int(input("Enter the number of employees"))
total_salary = 0
employee_salary = 0
average_salary = 0

for i in range(0,employee_count,1):
    employee_salary = int(input(f"Enter the salary of employee {i+1}:"))
    total_salary = total_salary + employee_salary
average_salary = total_salary / employee_count
print(f"Total Salary: {total_salary}")
print(f"Average Salary: {average_salary}")
```
``` Text
Enter the number of employees 5
Enter the salary of employee 1: 2000
Enter the salary of employee 2: 1000
Enter the salary of employee 3: 3000
Enter the salary of employee 4: 4000
Enter the salary of employee 5: 6000
Total Salary: 16000
Average Salary: 3200.0
```

Using while Loop

``` python
employee_count = int(input("Enter the number of employees"))
total_salary = 0
employee_salary = 0
average_salary = 0
counter = 0

while counter < employee_count:
    employee_salary = int(input(f"Enter the salary of employee {counter + 1}:"))
    total_salary = total_salary + employee_salary
    counter = counter + 1
average_salary = total_salary / employee_count
print(f"Total Salary: {total_salary}")
print(f"Average Salary: {average_salary}")
```
``` text
Enter the number of employees 5
Enter the salary of employee 1: 2000
Enter the salary of employee 2: 3000
Enter the salary of employee 3: 4000
Enter the salary of employee 4: 5000
Enter the salary of employee 5: 1000
Total Salary: 15000
Average Salary: 3000.0
```

Problem 3: The HR department wants to analyze employee salaries. Instead of just calculating the total payroll, they also want to know how many employees belong to different salary categories. Write a Python program that:
- Accepts the number of employees.
- Accepts the salary of each employee.
- Calculates: Total Salary, Average Salary, Highest Salary, Lowest Salary, Number of employees earning ₹50,000 or more, Number of employees earning less than ₹30,000.

``` python
employee_count = int(input("Enter the number of employees"))
total_salary = 0
current_value = 0
high_earners = 0
low_earners = 0

for i in range(0,employee_count,1):
    
    current_value = int(input(f"Enter Salary of employee: {i + 1}"))
    total_salary = total_salary + current_value
    
    if i == 0:
        max_salary = current_value
        min_salary = current_value
    
    if current_value > max_salary:
        max_salary = current_value
    
    if current_value < min_salary:
        min_salary = current_value
    
    if current_value >= 50000:
        high_earners = high_earners + 1
    
    if current_value <= 30000:
        low_earners = low_earners + 1

average_salary = total_salary / employee_count

print(f"Total Salaries of Employee: {total_salary}")
print(f"Average Salaries of Employee: {average_salary}")
print(f"Maximum Salary: {max_salary}")
print(f"Minimum Salary: {min_salary}")
print(f"High Earners Count: {high_earners}")
print(f"Low Earners Count: {low_earners}")
```
``` text
Enter the number of employees 5
Enter Salary of employee: 1 10000
Enter Salary of employee: 2 200000
Enter Salary of employee: 3 300000
Enter Salary of employee: 4 40000
Enter Salary of employee: 5 500000
Total Salaries of Employee: 1050000
Average Salaries of Employee: 210000.0
Maximum Salary: 500000
Minimum Salary: 10000
High Earners Count: 3
Low Earners Count: 1
```

``` python
```
``` text
```
