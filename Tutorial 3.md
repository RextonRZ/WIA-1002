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
//no precondition because no accepting anything

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


public interface BidCollectionInterface {
    /**
     * Purpose: Adds a bid to this collection
     * Precond: None
     * Postcond: The bid was added into the collection
     * @param toAdd the bid to add
     */
    public void add(BidInterface toAdd);
    
    
    /***
     * Purpose: Return the bid in this collection with best yearly cost
     * Precond: The collection must not be empty.
     * Postcond: The bid with the lowest yearly cost was returned.
     * @param averageHours Average hours of operation per year
     * @param energyCost Cost in dollars per KWH
     * @return The bid with lowest yearly cost
     */
    public BidInterface getBestYearlyCost(double averageHours, double energyCost);
    
    /***
     * Purpose: Returns the bid in this collection with the best initial cost. 
     * Precond: The collection must not be empty.
     * Postcond: The bid with the best initial cost was returned.
     * @return The bid with the best initial cost.
     */
    public BidInterface getBestInitialCost();
    
    
    /****
     * Purpose: Clears all of the items from this collection.
     * Precond: None
     * Postcond: All of the items from this collection were cleared.
     */
    public void clear();
    
    /****
     * Purpose: Returns the number of items in this collection.
     * Precond: None
     * Postcond: The number of items in this collection was returned.
     * @return The number of items in the collection
     */
    public int getLength();
    
    /***
     * Purpose: Check whether this collection is empty.
     * Precond: None
     * Postcond: The condition of the collection whether it is empty a not was returned.
     * @return the condition of the collection to check whether it is empty.
     */
    public boolean isEmpty();
}

```


