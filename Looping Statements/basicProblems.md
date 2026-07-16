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

Problem 4: An e-commerce company wants to analyze customer purchases made during the day. You need to process multiple customer orders and generate a summary report. Write a Python program that:
- Accepts the number of customers.
- Accepts the purchase amount for each customer.
- Calculate: Total Sales, Average Purchase, Highest Purchase, Lowest Purchase, Number of customers eligible for discount (Purchase ≥ ₹5000), Number of customers not eligible for discount (Purchase < ₹5000).

``` python
customer_count = int(input("Enter the number of customers"))
total_sales = 0
eligible_customers = 0
not_eligible_customers = 0
total_discount = 0

for i in range(0,customer_count,1):
    purchase_amount = int(input(f"Enter amount for items purchased for customer {i+1}"))
    total_sales = total_sales + purchase_amount

    if i == 0:
        highest_purchase = purchase_amount
        lowest_purchase = purchase_amount

    if purchase_amount > highest_purchase:
        highest_purchase = purchase_amount

    if purchase_amount < lowest_purchase:
        lowest_purchase = purchase_amount
    
    if purchase_amount >= 5000:
        eligible_customers = eligible_customers + 1
        discount = purchase_amount * 0.1
        total_discount = total_discount + discount

    if purchase_amount < 5000:
        not_eligible_customers = not_eligible_customers + 1

average_sales = total_sales / customer_count

print(f"Total Customers: {customer_count}")
print(f"Total Sales: {total_sales}")
print(f"Average Purchase: {average_sales}")
print(f"Highest Purchase: {highest_purchase}")
print(f"Lowest Purchase: {lowest_purchase}")
print(f"Eligible Customers: {eligible_customers}")
print(f"Non Eligible Customers: {not_eligible_customers}")
print(f"Total Discount Given {total_discount}")
```
``` Text
Enter the number of customers 5
Enter amount for items purchased for customer 1 20000
Enter amount for items purchased for customer 2 30000
Enter amount for items purchased for customer 3 50000
Enter amount for items purchased for customer 4 100000
Enter amount for items purchased for customer 5 8000
Total Customers: 5
Total Sales: 208000
Average Purchase: 41600.0
Highest Purchase: 100000
Lowest Purchase: 8000
Eligible Customers: 5
Non Eligible Customers: 0
Total Discount Given 20800.0
```

Problem 5: The HR department wants to prepare a Monthly Employee Performance Report. You have to process multiple employees and generate a summary. Write a python program that asks for:
- Enter the number of employees.
- For every employee input: Employee Name, Annual Salary, Performance Rating
- The allowed ratings will be: Excellent, Good, Average, Poor
- The validation rules are as follows:
- Salary should be greater than 0, if not display "Invalid Salary" and ask for the salary of the same employee again.
- If the values dont match performance rating values given then display "Invalid Rating" and ask for the rating of the same employee.
- Also there are rules for bonus:
- Excellent - 20%, Good - 10%, Average - 5%, Poor - 0%

At end display the following information: Total Employees, Total Salary, Average Salary, Highest Salary, Lowest Salary, Count of Excellent Employees, Count of Good Employees, Count of Average Employees, Count of Poor Employees, Total Bonus Budget

``` python
employee_count = int(input("Enter the number of employees: "))

# Business Variables
total_salary = 0
total_bonus = 0

excellent_count = 0
good_count = 0
average_count = 0
poor_count = 0

highest_salary = 0
lowest_salary = 0

for i in range(employee_count):

    print(f"\n---------- Employee {i + 1} ----------")

    employee_name = input("Enter Employee Name: ")

    annual_salary = int(input("Enter Annual Salary: "))

    while annual_salary <= 0:
        print("Invalid Salary")
        annual_salary = int(input("Enter Annual Salary: "))

    performance_rating = input("Enter Performance Rating: ")

    while performance_rating != "Excellent" and \
          performance_rating != "Good" and \
          performance_rating != "Average" and \
          performance_rating != "Poor":

        print("Invalid Rating")
        print("Valid Ratings: Excellent, Good, Average, Poor")
        performance_rating = input("Enter Performance Rating: ")

    # Initialize Highest and Lowest Salary
    if i == 0:
        highest_salary = annual_salary
        lowest_salary = annual_salary

    # Total Salary
    total_salary += annual_salary

    # Highest Salary
    if annual_salary > highest_salary:
        highest_salary = annual_salary

    # Lowest Salary
    if annual_salary < lowest_salary:
        lowest_salary = annual_salary

    # Bonus Calculation
    if performance_rating == "Excellent":
        bonus = annual_salary * 0.20
        excellent_count += 1

    elif performance_rating == "Good":
        bonus = annual_salary * 0.10
        good_count += 1

    elif performance_rating == "Average":
        bonus = annual_salary * 0.05
        average_count += 1

    else:
        bonus = 0
        poor_count += 1

    total_bonus += bonus

average_salary = total_salary / employee_count

print("\n==============================================")
print("      MONTHLY EMPLOYEE PERFORMANCE REPORT")
print("==============================================")

print(f"Total Employees        : {employee_count}")
print(f"Total Salary           : ₹{total_salary:,.2f}")
print(f"Average Salary         : ₹{average_salary:,.2f}")
print(f"Highest Salary         : ₹{highest_salary:,.2f}")
print(f"Lowest Salary          : ₹{lowest_salary:,.2f}")

print("\nEmployee Ratings")
print("-------------------------------")
print(f"Excellent Employees    : {excellent_count}")
print(f"Good Employees         : {good_count}")
print(f"Average Employees      : {average_count}")
print(f"Poor Employees         : {poor_count}")

print(f"\nTotal Bonus Budget     : ₹{total_bonus:,.2f}")
```
``` text
Enter the number of employees:  2

---------- Employee 1 ----------
Enter Employee Name:  Atharva
Enter Annual Salary:  400000
Enter Performance Rating:  Excellent

---------- Employee 2 ----------
Enter Employee Name:  Sujat
Enter Annual Salary:  5000000
Enter Performance Rating:  Excellent

==============================================
      MONTHLY EMPLOYEE PERFORMANCE REPORT
==============================================
Total Employees        : 2
Total Salary           : ₹5,400,000.00
Average Salary         : ₹2,700,000.00
Highest Salary         : ₹5,000,000.00
Lowest Salary          : ₹400,000.00

Employee Ratings
-------------------------------
Excellent Employees    : 2
Good Employees         : 0
Average Employees      : 0
Poor Employees         : 0

Total Bonus Budget     : ₹1,080,000.00
```
