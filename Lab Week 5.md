# Lab 4: Linked List

#### Cr: OOI RUI ZHE 23004947

### Question 1
#### Create a package called SList and implement a node class called SNode<E>. The SNode<E> class consists of two constructors, respectively, a default constructor and a constructor that receives a generic item. 

##### 1) Initialise the variables appropriately in each constructor. 
```plaintext
public class SNode<E>{
    E element;
    SNode<E> next;

    public SNode() {
        this.element = null;
    }
    
    public SNode(E e){
        this.element = e;
    }
}
```

##### 2) Create a generic class called SList<E> and include the necessary declaration in the SList<E> class.
```plaintext
public class SList<E>{
    SNode<E> head;
    SNode<E> tail;
    int size=0;

    public SList() {
        this.head = null;
        this.tail = null;
    }
}
```

##### 3) Implement the following methods in class SList<E>:
##### i. public void appendEnd(E e)
##### Append a new element at the end of the list.
```plaintext
public void appendEnd(E e){
        if(tail == null){
            head = tail = new SNode<>(e);
        }else{
            tail.next = new SNode<>(e);
            tail = tail.next;
        }
        size++;
    }
```

##### ii. public E removeInitial()
##### Eliminate the first element in the list.
```plaintext
public E removeInitial(){
        if(size==0) return null;
        else{
            SNode<E> temp = head;
            head = head.next;
            size--;
            if(head==null) tail = null;
            return temp.element;
        }
    }
```

##### iii. public boolean contains(E e)
##### Search for an element and returns true if this list contains the searched element
```plaintext
public boolean contains(E e){
        SNode<E> current = head;
        while (current != null){    
            if(current.element.equals(e)){
                return true;
            }
            current=current.next;
        }
        return false;
    }
```

##### iv. public void clear()
##### Empty all elements in the list and return a statement that reports that the list is empty.
```plaintext
    public void clear(){
        head=null;
        tail = null;
        size = 0;
    }
```
##### v. public void display()
##### Display all values from the list in a successive order.



