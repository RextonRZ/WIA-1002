## WIA1002/WIB1002 Data Structure
### Tutorial 3: ADT & Bags

#### Q1(a)Identify the instance variables for each of the class (i.e. Dispenser, Cash Register, Candy Machine)
```plaintext
Dispenser: To make the sale
Instance variables:
* Product cost - cost
* Number of items in the dispenser - numOfItems

Cash Register: Accept money, return change
Instance variables:
* Amount of cash available inside the rigister - cashOnHand

Candy Machine
Instance variables:
* Four dispenser - candies,chip,gum, cookie
* Cash register - cRegister
```

#### Q1(b)Identify the *methods/operations* for each of the class (i.e. Dispenser, Cash Register, Candy Machine)
```plaintext
Dispenser:
* getCount: Retrive the number of items in the dispenser
* getProductCost: Retrieve the cost for each item
* makeSales: Reduce the number of items in the dispenser by 1
* setCost: Set the cost of the product
* setNumberOfItems: Set the num of items in the dispenser

Cash Register:
* acceptAmount: Update the total cash
* returnChange: Return the change
* getCashOnHand: Retrieve the toal amount in the cash register
* setCashOnHand: Set the amount of cash in the register

Candy Machine:
* showSelection: Show the number of products sold by the candy machine
* makeSelection: Allow the customers to select the product
```


#### Q1(C)Produce a UML class diagram to represent the three classes
<p align="center">
<img src="UML Tuto 3 Q1c.png" alt="UML Diagram Tuto3 Q1c" width="296" height="181">
</p>


