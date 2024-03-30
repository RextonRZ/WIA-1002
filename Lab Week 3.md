# Lab 3: ADT & Bags

#### Cr: OOI RUI ZHE 23004947

### Question 1
```plaintext
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
} // end BagInterface

public class ArrayBag<T> implements BagInterface<T>{
    private T[] bag;
    private static final int DEFAULT_CAPACITY = 25;
    private int numberOfEntries;

    /***
     * Gets the current number of entries in this bag.
     * 
     * @return the integer number of entries currently in the bag 
     */
    @Override
    public int getCurrentSize() {
        return 0;
    }

    /****
     * See whether the bag is Full
     * 
     * @return true if the bag is full. or false if not
     */
    @Override
    public boolean isFull() {
        return false;
    }
    
    /***
     * See whether the bag is empty
     * 
     * @return true if the bag is empty, or false if not
     */
    @Override
    public boolean isEmpty() {
       return false;
    }

    
    /***
    * Adds a new entry to this bag
    * 
    * @param newEntry the object to be added as a new entry
    * @return true if the addition is successful, or false if not
    */
    @Override
    public boolean add(Object newEntry) {
        throw new UnsupportedOperationException("Not supported yet."); //To change body of generated methods, choose Tools | Templates.
    }

    /***
     * Removes one unspecified entry from this bag if possible
     * 
     * @return either the remove entry, if the removal is successful
     */
    @Override
    public T remove() {
       return null;
    }

    /***
     * Remove one occurrence of a given entry from this bag
     * 
     * @param anEntry the entry to be removed
     * @return true if the removal was successful, or false if not
     */
    @Override
    public boolean remove(Object anEntry) {
        return false;
    }

    /***
     * Removes all entries from this bag
     */
    @Override
    public void clear() {
        
    }

    /***
     * Count the number of times a given entries in this bag
     * 
     * @param anEntry the entry to be counted
     * @return the number of times anEntry appears in this bag
     */
    @Override
    public int getFrequencyOf(Object anEntry) {
        return 0;
    }

    /***
     * Tests whether this bag contains a given entry
     * 
     * @param anEntry the entry to locate
     * @return true if this bag contains anEntry, or False if not
     */
    @Override
    public boolean contains(T anEntry) {
        return false;
    }

    /***
     * Retrieves all entries that are in this bag
     * 
     * @return a newly allocated array of all the entries in the bag
     */
    @Override
    public T[] toArray() {
        return null; 
    }

    
    
}
