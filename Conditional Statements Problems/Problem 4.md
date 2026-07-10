Problem 4: A company wants to automate the calculation of annual employee bonuses. The HR department has defined bonus percentage based on performance rating, years of service and attendance. Write a python program that calculates employees annual bonus.

Inputs
- Employee Name
- Annual Salary
- Performance Rating (Excellent, Good, Average, Poor)
- Years of Service
- Attendance Percentage

Validation Rules
- Salary must be greater than 0.
- Years of experience should be negative.
- Attendance should be between 0 and 100.
- Performance rating must be: Excellent, Good, Average, Poor

If any validation fails display an appropriate error message.

Rule 1: If employee atendance is below 70%: employee recieved 0% bonus and status is not eligible and no further checks.

Rule 2: Otherwise determine the base bonus: 
- Excellent: 20% bonus
- Good: 12% bonus
- Average: 6% bonus
- Poor: 0% bonus

Rule 3: If employee has completed 10 years of service or more then add 5% extra bonus, otherwise no extra bonus.

Rule 4: Bonus cannot exceed 25 %

``` python
employee_name = input("Enter Employee Name: ")
annual_salary = float(input("Enter Annual Salary: "))
performance_rating = input("Enter Performance Rating (Excellent/Good/Average/Poor): ")
years_of_service = int(input("Enter Years of Service: "))
attendance = float(input("Enter Attendance Percentage: "))

bonus_percentage = 0
bonus_status = "Not Eligible"

if annual_salary <= 0:
    print("Salary must be greater than 0.")

elif years_of_service < 0:
    print("Years of service cannot be negative.")

elif attendance < 0 or attendance > 100:
    print("Attendance must be between 0 and 100.")

elif (performance_rating != "Excellent"
      and performance_rating != "Good"
      and performance_rating != "Average"
      and performance_rating != "Poor"):
    print("Invalid Performance Rating.")

else:
    
    if attendance < 70:
        bonus_percentage = 0
        bonus_status = "Not Eligible (Attendance below 70%)"
    else:

        
        if performance_rating == "Excellent":
            bonus_percentage = 20

        elif performance_rating == "Good":
            bonus_percentage = 12

        elif performance_rating == "Average":
            bonus_percentage = 6
        
        else:
            bonus_percentage = 0

        if years_of_service >= 10:
            bonus_percentage += 5

        # Rule 4: Maximum Bonus
        if bonus_percentage > 25:
            bonus_percentage = 25

        bonus_status = "Eligible"
        
    bonus_amount = annual_salary * (bonus_percentage / 100)
    final_salary = annual_salary + bonus_amount

    print("\n========== Employee Bonus Summary ==========")
    print(f"Employee Name      : {employee_name}")
    print(f"Annual Salary      : ₹{annual_salary:,.2f}")
    print(f"Performance Rating : {performance_rating}")
    print(f"Years of Service   : {years_of_service}")
    print(f"Attendance         : {attendance}%")
    print(f"Bonus Percentage   : {bonus_percentage}%")
    print(f"Bonus Amount       : ₹{bonus_amount:,.2f}")
    print(f"Final Salary       : ₹{final_salary:,.2f}")
    print(f"Status             : {bonus_status}")
```
Final Output:

``` text
Enter Employee Name:  Atharva
Enter Annual Salary:  30000
Enter Performance Rating (Excellent/Good/Average/Poor):  Average
Enter Years of Service:  5
Enter Attendance Percentage:  80

========== Employee Bonus Summary ==========
Employee Name      : Atharva
Annual Salary      : ₹30,000.00
Performance Rating : Average
Years of Service   : 5
Attendance         : 80.0%
Bonus Percentage   : 6%
Bonus Amount       : ₹1,800.00
Final Salary       : ₹31,800.00
Status             : Eligible
```

