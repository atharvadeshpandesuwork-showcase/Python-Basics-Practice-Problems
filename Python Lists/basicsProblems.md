Problem 1: An HR executive wants to store the names of newly hired employees. Your program should collect the employee name and display them at the end. Write a python program that will take the number of emplyees as input. Using a for loop take the input of employee names and store it in a list. After this display all the names of the employees.

``` python
employee_count = int(input("Enter the number of employees"))
employee_list = []
increment = 0 
while increment < employee_count:
    employee_name = str(input("Enter employee name"))
    employee_list.append(employee_name)
    increment = increment + 1

for i in range(employee_count):
    print(f"{i + 1}. {employee_list[i]}")
```
``` text
Enter the number of employees 2
Enter employee name Atharva
Enter employee name Sujat
1. Atharva
2. Sujat
```

Problem 2: A school has recently completed its semester examinations. The class teahcer wants to prepare a simple report of the students marks. Instead of calculating everything manually, the teacher asked to build a python program that collects the marks of all the students and generates a summary report. The program should allow the teacher to enter marks for multiple students store them in a list, display the entered marks, calculate the total marks obtained by class and compute the average marks. Create a python program that stores the student marks in a list and generates the summary report.

```python
student_count = int(input("Enter the number of students"))
print("")
student_marks = []
total_marks = 0
average_marks = 0
for i in range(student_count):
    student_marks_entry = int(input(f"Enter the marks for student {i+1}"))
    student_marks.append(student_marks_entry)
print("")
print("---- Student Marks ----")
for i in range(student_count):
    print(f"Student {i+1} marks: {student_marks[i]}")
    total_marks = total_marks + student_marks[i]

average_marks = total_marks / student_count
print("")
print("---- Class Performance Report ----")
print(f"Total Students: {student_count}")
print(f"Total Marks: {total_marks}")
print(f"Average Marks: {average_marks}")
```
``` text
Enter the number of students 5

Enter the marks for student 1 22
Enter the marks for student 2 45
Enter the marks for student 3 55
Enter the marks for student 4 56
Enter the marks for student 5 85

---- Student Marks ----
Student 1 marks: 22
Student 2 marks: 45
Student 3 marks: 55
Student 4 marks: 56
Student 5 marks: 85

---- Class Performance Report ----
Total Students: 5
Total Marks: 263
Average Marks: 52.6
```

Problem 3: The management of ABC public school wants to automate the preparation of class performance report after the semeter examinations. Currently the calculate the results manually which is time consuming and prone to errors. The school has asked to develop a python program that stores students marks and generates a summary report containing important class statistics. The report should help teachers understand the overall performance of the class. 

Develop a python program that collects all the marks of the students stores them in the list and performs various claculations and generates a class performance report.

Calculate the following:
- Total Marks
- Average Marks
- Maximum Marks
- Minimum Marks
- Count of passed students
- Count of failed students

``` python
student_marks = []
total_marks = 0
average_marks = 0
highest_marks = 0
lowest_marks = 0
passed_students = 0
failed_students = 0
increment = 0

# Program starts
student_count = int(input("Enter the total numnber of students"))

while increment < student_count:
    student_marks_entry = int(input(f"Enter the marks of Student {increment + 1}"))
    if student_marks_entry < 0 or student_marks_entry > 100:
        print("Invalid marks")
        print("Please enter marks between 0 and 100")
        student_marks_entry = int(input(f"Enter the marks of Student {increment + 1}"))
    else:
        student_marks.append(student_marks_entry)
        increment = increment + 1
print("")
print("--- Student Marks ---")

# Print Student Marks
for i in range(student_count):
    print(f"Student {i+1} : {student_marks[i]}")
    total_marks = total_marks + student_marks[i]

# Seprate block only to count number of passed and failed students and max and min marks 
for i in range(student_count):
    if student_marks[i] >= 35:
        passed_students = passed_students + 1
    else:
        failed_students = failed_students + 1
# Block to check max and min marks
    if i == 0:
        highest_marks = student_marks[i]
        lowest_marks = student_marks[i]

    if student_marks[i] > highest_marks:
        highest_marks = student_marks[i]

    if student_marks[i] < lowest_marks:
        lowest_marks = student_marks[i]
        

average_marks = total_marks / student_count


print("")
print("--- Class Performance Report ---")
print(f"Total Students: {student_count}")
print(f"Total Marks: {total_marks}")
print(f"Average Marks: {average_marks}")
print(f"Highest Marks: {highest_marks}")
print(f"Lowest Marks: {lowest_marks}")
print(f"Passed Students: {passed_students}")
print(f"Failed Students: {failed_students}")
```
``` text
Enter the total numnber of students 5
Enter the marks of Student 1 85
Enter the marks of Student 2 74
Enter the marks of Student 3 92
Enter the marks of Student 4 68
Enter the marks of Student 5 80

--- Student Marks ---
Student 1 : 85
Student 2 : 74
Student 3 : 92
Student 4 : 68
Student 5 : 80

--- Class Performance Report ---
Total Students: 5
Total Marks: 399
Average Marks: 79.8
Highest Marks: 92
Lowest Marks: 68
Passed Students: 5
Failed Students: 0
```

Problem 4: ABC Technologies maintains a list of employee names. The HR department frequently recieves requests to verify whether a particular employee works in the organizatin. Instead of manually searchip through the employee records, they want a python program that stores the employee names and allows the HR to search for an employee efficiently. Create a python program that:
- Stores employee names in a list
- Displays all employee names
- Searches for an employee entered by the user
- Displays whether the emplyee exsists.

``` python
employee_count = int(input("Enter the number of employees"))
employee_list = []
found_str = False
employee_record = ""
search_employee_record = ""
increment = 0

while increment < employee_count:
    employee_record = input(f"Enter the name of employee {increment + 1}: ")
    employee_list.append(employee_record)
    increment = increment + 1

# Loop to print employee records
for i in range(employee_count):
    print(f"Employee {i+1}: {employee_list[i]}")

search_employee_record = input("Enter name of employee to be searched") 

# Loop to search for employee name
for i in range(employee_count):
    if employee_list[i] == search_employee_record:
        found_str = True
        break

if found_str == True:
    print("Employee Found")
else:
    print("Employee Not Found")
```
``` text
Enter the number of employees 4
Enter the name of employee 1:  Rahul
Enter the name of employee 2:  Priya
Enter the name of employee 3:  Amit
Enter the name of employee 4:  Sneha
Employee 1: Rahul
Employee 2: Priya
Employee 3: Amit
Employee 4: Sneha
Enter name of employee to be searched Rahul
Employee Found
```

Q1. Why do we use a found variable ?
- The found variable is a boolean flag that keeps the track of whether the employee exsists in the list.
- It is initialized to False because the search has not started yet.
- During traversal of the list if a matching employee is found, the flag is changed to true.
- After the loop completes the program checks the value of this flag to decide whether to display "Employee Found" or "Employee Not Found".
- Without this flag the program would not have a simple way to remember the result of the search after the loop is finished.

Q2. Why cant we simply print "Employee Not Found" inside the for loop whenever the current employee does not match the search name ?
- We should not print "Employee Not found" inside the loop because each iteration checks only one employee.
- If the current employee does not match it does not mean that the name is absent from the entire list. It only means that particular record isnt a match.
- The employee may exsist later in the list.
- Therefore we should complete the search and print "Employee Not Found" only after confirming that no matching record exsists.

Q3. What is the time complexity of searching trough a list using for loop ?
- This program uses linear search.
- In the best case employee is first records in the list so only one comparison is required before the loop stops using break statement.
- The best case time complexity is O(1).
- In the worst case the employee is in the last index of the list or does not even exsist so every employee must be checked.
- Therefore the worst case time complexity is O(n) where n is the number of employees.

Q4. If there are 10 lakh (1,000,000) employee names, would this approach still be efficient ? Why or why not ?
- For a list containing 10 lakh employee names, this approach is generally not efficient because linear search has a worst-case time complexity of O(n).
- If the employee is near the end of the list or does not exist, the program may need to compare almost every record before reaching a conclusion.
- As the size of the list increases, the search time increases proportionally.
- For very large datasets, more efficient data structures or algorithms, such as hash tables or binary search on sorted data, are preferred because they can reduce the search time significantly."

Problem 5: ABC Technologies maintains a list of employee names in the order they joined the company. Before preparing for the farewell summary, the HR department wants to display the employee names in reverse order so that the most recently added employee appears first. As a python developer, your task is to write a program that accepts employee names from users, stores them in a list and displays the list in reverse order without using the pythons inbuilt functions. Write a python program that performs the following tasks:
- Ask the user to enter the total number of employees.
- Accept the name of each employee and store them in a list.
- Display the original employee list.
- Display the employee names in reverse order by traversing the list from the last element to first.
- Do not modify the original list.
- Do not use any built in methods or shortcuts for reversing the elements.

Functional Requirements
- Accept the number of employees from the user.
- Store the employee names using a python list.
- Print the employee names in the same order they were entered.
- Print the employee names in reverse order.
- The original list should remain unpacked after displaying the reversed order.

``` Python
employee_count = int(input("Enter the number of employees"))
employee_list = []
employee_record = ""

for i in range(employee_count):
    employee_record = input(f"Enter the name of employee: {i+1}")
    employee_list.append(employee_record)

# Printing the original employee list
for i in range(employee_count):
    print(f"Employee {i+1}: {employee_list[i]}")

print("")
print("Employee names in reverse order")
print("")
# Printing employee names in reverse order
for i in range(employee_count-1,-1,-1):
    print(f"Employee {i + 1}: {employee_list[i]}")
```
``` Text
Enter the number of employees 5
Enter the name of employee: 1 Atharva
Enter the name of employee: 2 Sujat
Enter the name of employee: 3 Anjali
Enter the name of employee: 4 Usha
Enter the name of employee: 5 Priya
Employee 1: Atharva
Employee 2: Sujat
Employee 3: Anjali
Employee 4: Usha
Employee 5: Priya

Employee names in reverse order
Employee 5: Priya
Employee 4: Usha
Employee 3: Anjali
Employee 2: Sujat
Employee 1: Atharva
```
Problem 6: ABC electronics wants to calculate the the total sales for a day.
- Ask the user for the number of products sold.
- Store each product sale in amount list.
- Display all sales.
- Calculate the total sales using sum().
- Calculate the average sales using the total retruned by sum().
- Display both values.

``` Python
products_sold = int(input("Enter the number of products sold"))
products_price_list = []
total_sales = 0
increment = 0 
for i in range(products_sold):
    price_entry = int(input(f"Enter the price of product {i+1}"))
    products_price_list.append(price_entry)

while increment < products_sold:
    print(f"Price of product{increment + 1}: {products_price_list[increment]}")
    increment = increment + 1

total_sales = sum(products_price_list)
print(f"Total sales: {total_sales}")
print(f"Average sales: {total_sales / products_sold }")
```
``` Text
Enter the number of products sold 2
Enter the price of product 1 10000
Enter the price of product 2 20000
Price of product1: 10000
Price of product2: 20000
Total sales: 30000
Average sales: 15000.0
```

Problem 7: ABC Electronics is a nationwide retailer that tracks the sales value of products sold each month. The management wants to quickly identify the highest monthly sales amount to recognize companys best peforming month and use it for performance analysis. Previously the analyst manually compared every sales value to find the highest amount. As a python developer your task is to develop a program that records monthly sales and displays them and identifies the highest sales amount using max function.

Functional Requirements
Your program should ask the user:
- Ask the user to enter the number of months.
- Store each month number sales amount in a list.
- Display all recorded monthly sales.
- Display the highest sales amount.

``` Python
no_months = int(input("Enter number of months"))
monthwise_sales = []
max_sales = 0

# Enter monthly sales loop
for i in range(no_months):
    sales_entry = int(input(f"Enter the month {i+1} sales"))
    monthwise_sales.append(sales_entry)

# Print monthwise sales
for i in range(no_months):
    print(f"Month {i+1}: {monthwise_sales[i]}")

max_sales = max(monthwise_sales)
print(f"Highest monthly sales: {max_sales}")

```
``` Text
Enter number of months 2
Enter the month 1 sales 50000
Enter the month 2 sales 60000
Month 1: 50000
Month 2: 60000
Highest monthly sales: 60000
```

Problem 7: ABC Technologies is conducting its annual salary review. Before finalizing the increment budget the HR department wants to identify the employee with the second highest salary. The HR team already has the salary details of all the employees but they need a python program to automate this task instead of checking salaries manually. As a data analyst your responsibility is to write a program that needs the employee salaries and determined the highest unique salary. Write a python program to do the following tasks:
- Ask the user to enter the number of employees.
- Accept salary of each employee from the user.
- Store all the salaries in a list.
- Display the complete list of employees.
- Arrange the salaries in ascending order.
- Display the sorted salary list.
- Find and display the second highest unique salary.

Using mannual Sorting
``` python
```
``` Text
```

Using sort method
``` python
no_employees = int(input("Enter the number of employees"))
employees_salary = []

# Loop to enter salary employees in list
for i in range(no_employees):
    salary_record = int(input(f"Enter the salary of employee {i+1}:"))
    employees_salary.append(salary_record)

print("Employee Salary")
print("")

# loop to print the salaries
for i in range(no_employees):
    print(employees_salary[i])

new_list = employees_salary

print("Sorted employee salary")
print("")

# Loop to print the sorted salaries
for i in range(no_employees):
    print(new_list[i])

highest_salary = new_list[-1]
salary_found = False

for i in range(len(new_list)-2,-1,-1):
    if new_list[i] != highest_salary:
        print(f"Second highest salary {new_list[i]}")
        salary_found = True
        break
    else:
        print("Second highest salary does not exsist")
```
``` Text
Enter the number of employees 2
Enter the salary of employee 1: 1000
Enter the salary of employee 2: 20000
Employee Salary

1000
20000
Sorted employee salary

1000
20000
Second highest salary 1000
```

Problem 8: You have recently joined ABC technologies Pvt Ltd as a junior data analyst. Every year the human resources (HR) department conducts a salary review before deciding employee appraisals and budgeting for next financial year. Currently the HR team receives salary data from multiple departments and manually calculates important statistics using spreadsheets. This process is time-consuming and prone to errors especially as the company grows. Your manager has asked to automate this analysis using python. The program should read the employee salaries, calculate important salary statistics and identify employees earning above companies average salary.

The report generated by your program will help HR:
- Understand overall salary expenditure.
- Identify the highest and lowest paid employees.
- Calculate the average salary offered by the company.
- Determine how many employees earn above the company average, which will help in planning performance bonuses.

Develop a python program that performs the following task:
- Ask the user to enter the number of employees.
- Accept the salary of each employee.
- Store the salaries in a list.
- Display all employee salary.
- Generate the following statistics: Total salary payout, Average Salary, Highest Salary, Lowest Salary.
- Count and display the number of employees whose salary is greater than the average salary.

``` python
no_employees = int(input("Enter the number of employees"))
employee_salaries = []
count_emp = 0

# Loop to enter the employee salaries
for i in range (no_employees):
    salary_record = int(input(f"Enter the salary of Employee {i+1}: "))
    employee_salaries.append(salary_record)

print("Employee Salaries")
print("")

# Loop to display employee salaries
for i in range(len(employee_salaries)):
    print(f"Salary of Employee{i+1}: {employee_salaries[i]}")

total_salary_payout = sum(employee_salaries)
average_salary = total_salary_payout / no_employees
highest_salary = max(employee_salaries)
lowest_salary = min(employee_salaries)

for i in range(no_employees):
    if employee_salaries[i] > average_salary:
        count_emp = count_emp + 1
print("Summary Report")
print(f"Total salary payout: {total_salary_payout}")
print(f"Average Salary: {average_salary}")
print(f"Highest Salary: {highest_salary}")
print(f"Lowest Salary: {lowest_salary}")
print(f"Employees earning more than average salary: {count_emp}")
```
``` Text
Enter the number of employees 5
Enter the salary of Employee 1:  1000
Enter the salary of Employee 2:  15000
Enter the salary of Employee 3:  5000
Enter the salary of Employee 4:  3000
Enter the salary of Employee 5:  8000
Employee Salaries

Salary of Employee1: 1000
Salary of Employee2: 15000
Salary of Employee3: 5000
Salary of Employee4: 3000
Salary of Employee5: 8000
Summary Report
Total salary payout: 32000
Average Salary: 6400.0
Highest Salary: 15000
Lowest Salary: 1000
Employees earning more than average salary: 2
```

Problem 9: You are working as a data analyst at velocity retail stores a company that operates multiple supermarkets across the country. At the end of every business day each product's total sales amount is collected. Before generating daily performance reports the management team wants to arrange the sales amount from lowest to the highest. Although python provides a built-in sorting algorithm your manager wants you to understand how sorting algorithms work internally before using built in functions. Therefore, you are being instructed to perform sorting manually. After sorting the management also wants to know:
- Which product generated highest sales.
- Which product generated the second highest sales.
- Which product generated the lowest sales.

These insights help the management identify top performing products and products that may require promotional campaigns. Develop a python program that:
- Accepts number of products sold.
- Accepts the sales amount for each product.
- Stores all the sales amount in a list.
- Displays the original list.
- Sorts the list manually in ascending order
- Displays: Highest Sales, Second Highest Sales, Lowest Sales amount

``` python
no_products = int(input("Enter the number of products"))
sales_amount = []

# Loop to enter the product sales
for i in range(no_products):
    sales_record = int(input(f"Enter the sales for Product {i+1}:"))
    sales_amount.append(sales_record)
print("\n")
# Loop to display the product sales
for i in range(no_products):
    print(f"Product {i+1} sales: {sales_amount[i]}")

# Loop to sort the sales_list
for i in range(no_products):
    for j in range(i+1,no_products):
        if sales_amount[i] > sales_amount[j]:
            tmp = sales_amount[i]
            sales_amount[i] = sales_amount[j]
            sales_amount[j] = tmp
print("\n")
print("Sorted List")
print(sales_amount)

lowest_sales = min(sales_amount)

# Logic to find second highest unique sale
highest_sales = sales_amount[-1]
found = False
print("\n")
print(f"Highest Sales is of: {highest_sales}")

for i in range(len(sales_amount)-2,-1,-1):
    if sales_amount[i] != highest_sales:
        print(f"Second highest sales: {sales_amount[i]}")
        found = True
        break
if found == False:
    print("No Second Highest Sales found")
```
``` Text
Enter the number of products 5
Enter the sales for Product 1: 2000
Enter the sales for Product 2: 600
Enter the sales for Product 3: 100
Enter the sales for Product 4: 10000
Enter the sales for Product 5: 1000


Product 1 sales: 2000
Product 2 sales: 600
Product 3 sales: 100
Product 4 sales: 10000
Product 5 sales: 1000


Sorted List
[100, 600, 1000, 2000, 10000]


Highest Sales is of: 10000
Second highest sales: 2000
Click to add a cell.
```
