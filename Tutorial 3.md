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
<img src="UML Tuto 3 Q1c.png" alt="UML Diagram Tuto3 Q1c" width="888" height="543">
</p>


#### Q2
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Interface.java to edit this template
 */
package Tutorial3;

/**
 *
 * @author ooiru
 */
public interface BidInterface {
    /***
     * Purpose:Returns the name of the company making this bid.
     * Precond: None
     * Postcond:The name was returned
     * @return The name of the company making the bid
     */
    public String getCompanyName();
    
    /***
     * Purpose:Returns the description of the air conditioner that this bid is for.
     * Precond:None
     * Postcond:The description is returned.
     * @return The description of the air conditioner 
     */
    public String getDescription();
    
    /***
     * Purpose:Returns the capacity of this bid's AC in tons (1 ton = 12,000 BTU).
     * Precond:None
     * Postcond:The capacity is returned.
     * @return The capacity of this bid's AC in tons
     */
    public double getCapacity();
    
    /***
     * Purpose:Returns the seasonal efficiency of this bid's AC (SEER).
     * Precond:None
     * Postcond:The seasonal efficiency is returned.
     * @return The seasonal efficiency of this bid's AC (SEER)
     */
    public double getEfficiency();
    
    /***
     * Purpose:Returns the cost of this bid's AC.
     * Precond:None
     * Postcond:The cost of this bid's AC is returned.
     * @return The cost of this bid's AC.
     */
    public double getCost();
    
    /***
     * Purpose:Returns the cost of installing this bid's AC.
     * Precond:None
     * Postcond:The cost of installing this bid's AC is returned.
     * @return The cost of installing this bid's AC.
     */
    public double getInstallCost();
    
    /***
     * Purpose:Returns the yearly cost of operating this bid's AC.
     * Precond:None
     * Postcond:The yearly cost of operating this bid's AC is returned.
     * @return The yearly cost of operating this bid's AC.
     */
    public double getYearlyCost();
    
}

```


