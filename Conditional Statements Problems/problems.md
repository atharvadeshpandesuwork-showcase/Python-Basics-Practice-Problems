Topic: Conditional Statements in Python

Problem 1: Problem 1: A retail company wants to automate its customer loyalty program. Based on a customer’s purchase amount and membership status, the system should determine the discount they should receive. Write a python program that accepts the following input:
- Customer Name
- Purchase Amount
- Membership: Gold, Silver, Regular

The discount rules are as folows:  

| Membership | Purchase Amount      | Discount    |
|------------|----------------------|-------------|
| Gold       | ₹10,000 or more      | 20%         |
| Gold       | Less than ₹10,000    | 15%         |
| Silver     | ₹8,000 or more       | 15%         |
| Silver     | Less than ₹8,000     | 10%         |
| Regular    | ₹5,000 or more       | 5%          |
| Regular    | Less than ₹5,000     | No Discount |

The output should contain: Customer Name, Membership Type, Purchase Amount, Discount Percentage, Discount Amount, Final amount to pay

``` python
customer_name = str(input('Enter Customer Name'))
purchase_amount = float(input('Enter Purchase Amount'))
membership = str(input('Enter Membership Type'))
discount_tier = ""

if purchase_amount > 0 and (membership == 'Gold' or membership == 'Silver' or membership == 'Regular'):
    if membership == 'Gold' and purchase_amount >= 10000:
        discount_tier = "Discount Applicable 20 %"
        discount_amount = purchase_amount * 0.2
        final_payable = purchase_amount - discount_amount
    
    elif membership == 'Gold' and purchase_amount <10000:
        discount_tier = "Discount Applicable 15 %"
        discount_amount = purchase_amount * 0.15
        final_payable = purchase_amount - discount_amount
    
    elif membership == 'Silver' and purchase_amount >= 8000:
        discount_tier = "Discount Applicable 15 %"
        discount_amount = purchase_amount * 0.15
        final_payable = purchase_amount - discount_amount
    
    elif membership == 'Silver' and purchase_amount < 8000:
        discount_tier = "Discount Applicable 10 %"
        discount_amount = purchase_amount * 0.1
        final_payable = purchase_amount - discount_amount
    
    elif membership == 'Regular' and purchase_amount >= 5000:
        discount_tier = "Discount Applicable 5 %"
        discount_amount = purchase_amount * 0.05
        final_payable = purchase_amount - discount_amount
    
    elif membership == 'Regular' and purchase_amount < 5000:
       discount_tier = "No discount applicable"
       final_payable = purchase_amount

    print("Customer Name: ",customer_name)
    print("Membership Type:",membership)
    print("Purchase Amount:",purchase_amount)
    print(discount_tier)
    print("Discount Amount: ",discount_amount)
    print("Final Paybale Amount: ",final_payable)
    
elif membership != "Gold" and membership != "Silver" and membership != "Regular":
     print("Name of Customer: ",customer_name)
     print("Membership: ",membership)
     print("We are palnning to bring offers ASAP")

else:
    print("Name of Customer: ",customer_name)
    print("Membership: ",membership)
    print("Please Purchase Something")
```

Final Output

``` text
Enter Customer Name Atharva Deshpande
Enter Purchase Amount 9000
Enter Membership Type Silver
Customer Name:  Atharva Deshpande
Membership Type: Silver
Purchase Amount: 9000.0
Discount Applicable 15 %
Discount Amount:  1350.0
Final Paybale Amount:  7650.0
```

Problem 2: An online delivery company wants to determine whether an order qualifies for free delivery. The delivery charge depends on the customer's memebership and order value. Write a python program that determines the delivery based on the following rules:

Inputs
- Customer Name
- Order Amount
- Membership Type (Gold, Silver, Regular)
- Delivery Distance (in km)

Rules
- If the order amount is less than eual to 0 then display:  "Invalid Order Amount"
- If delivery distance is less than or equal to 0 display:  "Invalid Delivery Distance"
- Membership must be one of: Gold, Silver, Regular: "Otherwise Display: Invalid Membership Type"
- Delivery Charges: Gold Members order >=1000 then free delivery else 40 rs charge. Silver Members Order >= 1500 free delivery else 60 rs charge. Regular members order >= 2000 free delivery else 80 rs charge. If the delivery distance is greater than 10 km then add 20 rs extra delivery fee.


``` python
customer_name = str(input("Enter name of customer"))
order_amount = int(input("Enter total order amount"))
membership_type = str(input("Enter type of membership"))
delivery_distance = int(input("Enter delivery distance in km"))
base_delivery = 0

if order_amount <= 0:
    print("Invalid Order Amount")

elif delivery_distance <= 0:
    print("Invalid Distance")
    
elif membership_type != "Gold" and membership_type != "Silver" and membership_type != "Regular":
    print("Invalid Membership")

else:
        if membership_type == "Gold":
            if order_amount >=1000:
                print("Yay Free Delivery Unlocked")
                final_amount = order_amount
            else:
                base_delivery = 40
                print(base_delivery,":charges applicable")
                final_amount = order_amount + base_delivery
        
        elif membership_type == "Silver":
            if order_amount >= 1500:
                print("Yay Free Delivery Unlocked")
                final_amount = order_amount
            else:
                base_delivery = 60
                print(base_delivery,":charges applicable")
                final_amount = order_amount + base_delivery
        
        elif membership_type == "Regular":
            if order_amount >= 2000:
                print("Yay Free Delivery Unlocked")
                final_amount = order_amount
            else:
                base_delivery = 80
                print(base_delivery,":charges applicable")
                final_amount = order_amount + base_delivery
    
        if delivery_distance > 10:
            extra_charges = base_delivery + 20
            print("RS 20 extra delivery fee applicable")
            final_amount = order_amount + base_delivery + 20
        else:
            extra_charges = base_delivery
        
        print("Customer Name: ",customer_name)
        print("Membership: ",membership_type)
        print("Order Amount: ",order_amount)
        print("Delivery Distance: ",delivery_distance)
        print("Delivery Charges: ",extra_charges)
        print("Amount Payable: ",final_amount)
```

Final Output

``` Text
Enter name of customer Atharva
Enter total order amount 1900
Enter type of membership Regular
Enter delivery distance in km 12
80 :charges applicable
RS 20 extra delivery fee applicable
Customer Name:  Atharva
Membership:  Regular
Order Amount:  1900
Delivery Distance:  12
Delivery Charges:  100
Amount Payable:  2000
```

Problem 3: An insurance company wants to determine whether a customer is eligible for car insurance premium discount. The discount depends on the customers age, driving experience and whether they have insatlled a safety device in thier vehicle. Write a python program that calculates the insurance discount.

Inputs
- Customer Name
- Age
- Driving Experience (Years)
- Number of Accidents
- Safety device intalled (yes or no)

Validation Rules
- Age should be above 18 years.
- Driving experience cannot be negative.
- Safety Device must be yes or no

If any validation fails print the appropriate message.

Rule 1: If the customer has 3 or more accidents: No discount and No further checks required

Rule 2: Other the base disocunt will be determined as:
- age >= 30 and experience >= 10 years: Discount 20%
- Age ≥ 25 and Experience ≥ 5 years: Discount 10%
- Otherwise: Discount 5%

Rule 3: If the customer has installed a safety device then add 5% discount.

Rule 4: The maximum dicount cannot exceed 25 %

Display
- Customer Name
- Age
- Driving Exeperience
- Number of Accidents
- Safety Device
- First Discount
- Discount Status

``` python
customer_name = str(input("Enter Customer Name"))
age = int(input("Enter your age"))
driving_experience = int(input("Enter your driving experience in years"))
number_accidents = int(input("Enter the number of accidents"))
safety_device = str(input(" Is safety device installed yes / no"))
discount_status = "Not Eligible"

if age < 18:
    print("You dont qualify the age criteria to apply for the insurance")
elif driving_experience < 0:
    print("Driving experience cannot be negative")
elif number_accidents < 0:
    print("Accidents cannot be negative")
elif safety_device != "Yes" and safety_device != "No":
    print("Your input is invalid please read the prompt carefully")
    safety_device = safety_device = str(input(" Is safety device installed yes / no"))
else:
    if number_accidents >= 3:
        print("No dicount will be given")
        print("No further checks required")
        discount_applied = 0
    
    elif age >= 30 and driving_experience >= 10:
        discount_applied = 20
        discount_status = "Eligible"
    elif age >= 25 and driving_experience >= 5:
        discount_applied = 10
        discount_status = "Eligible"
    else:
        discount_applied = 5
        discount_status = "Eligible"

    if safety_device == "Yes" and discount_status == "Eligible":
        discount_applied = discount_applied + 5
    
    if discount_applied > 25:
        discount_applied = 25
    
    print("\n------ Insurance Discount Summary ------")
    print("Customer Name      :", customer_name)
    print("Age                :", age)
    print("Driving Experience :", driving_experience, "Years")
    print("Accidents          :", number_accidents)
    print("Safety Device      :", safety_device)
    print("Final Discount     :", str(discount_applied) + "%")
    print("Status             :", discount_status)
```

``` text
Enter Customer Name Suresh
Enter your age 40
Enter your driving experience in years 15
Enter the number of accidents 5
 Is safety device installed yes / no Yes
No dicount will be given
No further checks required

------ Insurance Discount Summary ------
Customer Name      : Suresh
Age                : 40
Driving Experience : 15 Years
Accidents          : 5
Safety Device      : Yes
Final Discount     : 0%
Status             : Not Eligible
```

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
