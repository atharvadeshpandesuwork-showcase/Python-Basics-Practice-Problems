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
