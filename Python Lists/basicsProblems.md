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
