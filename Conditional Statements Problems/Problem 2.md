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
