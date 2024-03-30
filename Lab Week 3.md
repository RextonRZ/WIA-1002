# Lab 3: ADT & Bags

#### Cr: OOI RUI ZHE 23004947
##### Bag Interface Code
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Interface.java to edit this template
 */
package lab3;

/**
 *
 * @author ooiru
 */
public interface BagInterface<T> {
    /** Gets the current number of entries in this bag.
        @return the integer number of entries currently in the bag */
    public int getCurrentSize();
    
    /** Sees whether this bag is full.
        @return true if the bag is full, or false if not */
    public boolean isFull();

    /** Sees whether this bag is empty.
        @return true if the bag is empty, or false if not */
    public boolean isEmpty();

    /** Adds a new entry to this bag.
        @param newEntry the object to be added as a new entry
        @return true if the addition is successful, or false if not */
    public boolean add(T newEntry);

    /** Removes one unspecified entry from this bag, if possible.
        @return either the removed entry, if the removal was successful,
        or null */
    public T remove();

    /** Removes one occurrence of a given entry from this bag.
        @param anEntry the entry to be removed
        @return true if the removal was successful, or false if not */
    public boolean remove(T anEntry);

    /** Removes all entries from this bag. */
    public void clear();

    /** Counts the number of times a given entry appears in this bag.
        @param anEntry the entry to be counted
        @return the number of times anEntry appears in the bag */
    public int getFrequencyOf(T anEntry);

    /** Tests whether this bag contains a given entry.
        @param anEntry the entry to locate
         @return true if this bag contains anEntry, or false otherwise */
    public boolean contains(T anEntry);

    /** Retrieves all entries that are in this bag.
        @return a newly allocated array of all the entries in the bag */
        public T[] toArray();
    
    /***
    * Creates a new bag that combines the contents of this bag and another bag
    * @param anotherBag a bag that is to be added.
    * @return a combined bag
    */
    public BagInterface<T> union(BagInterface<T> anotherBag);
    
    /***
    * Creates a new bag that contains those objects that occurs in both the bag and another bag
    * @param anotherBag a bag that is to be compared.
    * @return a combined bag
    */
    public BagInterface<T> intersection(BagInterface<T> anotherBag);
    
    /***
    * Creates a new bag of objects that would be left in this bag after removing those that also occur in another bag
    * @param anotherBag a bag that is to be removed.
    * @return a combined bag
    */
    public BagInterface<T> difference(BagInterface<T> anotherBag);
  
    
} // end BagInterface
```

##### ArrayBag Code
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package lab3;

import java.util.Arrays;

/**
 *
 * @author ooiru
 */
public class ArrayBag<T> implements BagInterface<T>{
    private T[] bag;
    private static final int DEFAULT_CAPACITY = 25;
    private int numberOfEntries;

    public ArrayBag() {
	this(DEFAULT_CAPACITY);
    }

    public ArrayBag(int capacity) {
        @SuppressWarnings("unchecked")
        T[] tempbag = (T[])new Object[capacity];
        bag = tempbag;
        numberOfEntries = 0;
    }
    
    /***
     * Gets the current number of entries in this bag.
     * 
     * @return the integer number of entries currently in the bag 
     */
    @Override
    public int getCurrentSize() {
        return numberOfEntries;
    }

    /****
     * See whether the bag is Full
     * 
     * @return true if the bag is full. or false if not
     */
    @Override
    public boolean isFull() {
        return bag.length == numberOfEntries;
    }
    
    /***
     * See whether the bag is empty
     * 
     * @return true if the bag is empty, or false if not
     */
    @Override
    public boolean isEmpty() {
       return numberOfEntries == 0;
    }

    
    /***
    * Adds a new entry to this bag
    * 
    * @param newEntry the object to be added as a new entry
    * @return true if the addition is successful, or false if not
    */
    @Override
    public boolean add(T newEntry) {
        if (isFull())
	    return false;

	bag[numberOfEntries++] = newEntry;
	return true;
    }

    /***
     * Removes one unspecified entry from this bag if possible
     * 
     * @return either the remove entry, if the removal is successful
     */
    @Override
    public T remove() {
       return remove((int) (Math.random() * this.numberOfEntries));
    }

    /***
     * Remove one occurrence of a given entry from this bag
     * 
     * @param anEntry the entry to be removed
     * @return true if the removal was successful, or false if not
     */
    @Override
    public boolean remove(T anEntry) {
		int index = indexOf(anEntry);
		return remove(index) == null ? false : true;
    }
    
    T remove(int index) {
		if (index < 0 || index >= this.bag.length || this.isEmpty())
			return null;

		T item = bag[index];

		for (int i = index; i < this.numberOfEntries - 1; i++) {
			bag[i] = bag[i + 1];
		}

		bag[--numberOfEntries] = null;

		return item;
	}

    /***
     * Removes all entries from this bag
     */
    @Override
    public void clear() {
        Arrays.fill(bag, null);
	numberOfEntries = 0;
    }

    /***
     * Count the number of times a given entries in this bag
     * 
     * @param anEntry the entry to be counted
     * @return the number of times anEntry appears in this bag
     */
    @Override
	public int getFrequencyOf(T entry) {
		int count = 0;

		for (int i = 0; i < numberOfEntries; i++) {
			count += ((bag[i]).equals(entry)) ? 1 : 0;
		}

		return count;
	}

    /***
     * Tests whether this bag contains a given entry
     * 
     * @param anEntry the entry to locate
     * @return true if this bag contains anEntry, or False if not
     */
    @Override
	public boolean contains(T entry) {
		return indexOf(entry) >= 0;
	}

	int indexOf(T entry) {
		Object[] esA = bag;

		if (entry == null) {
			for (int i = 0; i < numberOfEntries; i++) {
				if (entry == es[i])
					return i;
			}
		} else {
			for (int i = 0; i < numberOfEntries; i++) {
				if (entry.equals(es[i]))
					return i;
			}
		}

		return -1;
	}

    /***
     * Retrieves all entries that are in this bag
     * 
     * @return a newly allocated array of all the entries in the bag
     */
    @Override
	@SuppressWarnings("unchecked")
	public T[] toArray() {
		T[] resultArr = (T[]) new Object[numberOfEntries];
		System.arraycopy(bag, 0, resultArr, 0, numberOfEntries);
		return resultArr;
	}

	@SuppressWarnings("unchecked")
	public T[] toArray(T[] a) {
		return (T[]) Arrays.copyOf(bag, Math.min(a.length, numberOfEntries), a.getClass());
	}

        
    /***
    * Creates a new bag that combines the contents of this bag and another bag
    * @param anotherBag a bag that is to be added.
    * @return a combined bag
    */
    @Override
    public BagInterface<T> union(BagInterface<T> anotherBag){
        //First, we calculate the size of the new bag, which is the sum of the sizes of both bags
        int newSize = this.getCurrentSize() +anotherBag.getCurrentSize();
        
        //Create the new bag with the combined capacity
        ArrayBag<T> combineBag = new ArrayBag<>(newSize);
       
        //Add all elements from this bag
        for(int i=0;i<this.numberOfEntries;i++){
            combineBag.add(this.bag[i]);
        }
        
        //Add all elements from the other bag
        T[] otherBagArray = anotherBag.toArray();//change to array
        for(T item: otherBagArray)
            combineBag.add(item);
        
        return combineBag;
    }
    
    /***
    * Creates a new bag that contains those objects that occurs in both the bag and another bag
    * @param anotherBag a bag that is to be compared.
    * @return a combined bag
    */
    @Override
    public BagInterface<T> intersection(BagInterface<T> anotherBag){
        BagInterface<T> intersectionBag = new ArrayBag<T>();
        ArrayBag<T> otherBag = (ArrayBag<T>)anotherBag;
        BagInterface<T> copyOfAnotherBag = new ArrayBag<T>();
        int index;
        //copy the second bag
        
        for(index=0;index<otherBag.numberOfEntries;index++){
            copyOfAnotherBag.add(otherBag.bag[index]);
        }
        //add to intersectionBag each item in this bag that matches an item in another bag
        //once match, remove it from the second bag
        
        for(index=0;index<getCurrentSize();index++){
            if(copyOfAnotherBag.contains(bag[index])){
                intersectionBag.add(bag[index]);
                copyOfAnotherBag.remove(bag[index]);
            }
            
        }
        return intersectionBag;
    }
    
    /***
    * Creates a new bag of objects that would be left in this bag after removing those that also occur in another bag
    * @param anotherBag a bag that is to be removed.
    * @return a combined bag
    */
    public BagInterface<T> difference(BagInterface<T> anotherBag){
        BagInterface<T> differenceBag = new ArrayBag<T>();
        ArrayBag<T> otherBag = (ArrayBag<T>)anotherBag;
        int index;
        //copy this bag
        for(index=0;index<numberOfEntries;index++){
            differenceBag.add(bag[index]);
        }
        
        //remove the one that are in anotherBag
        for(index=0;index<otherBag.getCurrentSize();index++){
            if(differenceBag.contains(otherBag.bag[index])){
                differenceBag.remove(otherBag.bag[index]);
            }
        }
       return differenceBag;
    }
}
```

##### ArrayBagDemo Code
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package lab3;

/**
 *
 * @author ooiru
 */
public class ArrayBagDemo {
    //Q5a)
    private static void testAdd(BagInterface<String> aBag, String[] content){
        System.out.print("Adding ");
        for(int i=0;i<content.length;i++){
            aBag.add(content[i]);
            System.out.print(content[i]+" ");
        }
        System.out.println("");
    }
    
    //Q5b)
    private static void displayBag(BagInterface<String> aBag){
        System.out.println("This bag contains "+aBag.getCurrentSize()+" string(s), as follows: ");
        Object[] arrayBag = aBag.toArray();
        for(int i=0;i<aBag.getCurrentSize();i++){
            System.out.print(arrayBag[i]+" ");
        }
        System.out.println("");
    }
    
    public static void main(String[] args) {
        ArrayBag<String> bag1 = new ArrayBag<>();
        ArrayBag<String> bag2 = new ArrayBag<>();
        
        String[] contentsOfBag1 = {"A", "A", "B", "A", "C", "A"};
        String[] contentsOfBag2 = {"A", "B", "A", "C", "B", "C", "D", "another string"};
        
        System.out.println("bag1:");
        testAdd(bag1,contentsOfBag1);
        displayBag(bag1);
        
        System.out.println("");
        System.out.println("bag2:");
        testAdd(bag2,contentsOfBag2);
        displayBag(bag2);
        
        BagInterface<String> bag3 = bag1.union(bag2);
        System.out.println("");
        System.out.println("bag3, test the method union of bag1 and bag2:");
        displayBag(bag3);
        
        BagInterface<String> bag4 = bag1.intersection(bag2);
        System.out.println("");
        System.out.println("bag4, test the method intersection of bag1 and bag2:");
        displayBag(bag4);
        
        BagInterface<String> bag5 = bag1.difference(bag2);
        System.out.println("");
        System.out.println("bag5, test the method difference of bag1 and bag2:");
        displayBag(bag5);
        
    }
}
```
