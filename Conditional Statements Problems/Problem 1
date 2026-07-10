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
