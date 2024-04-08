# Lab 4: Linked List

#### Cr: OOI RUI ZHE 23004947

### Question 1
#### 1) Write the generic Node class consisting of two components of a node (i.e.: element, next), with a default construct and a constructor that accepts an item assigned to the initially declared element variable.
```plaintext
public class Node<T> {
    T element;
    Node<T> next;

    public Node() {
        this.element= null;
        this.next = next;
    }

    public Node(T element, Node<T> next) {
        this.element = element;
        this.next = next;
    }

    public T getElement() {
        return element;
    }

    public Node<T> getNext() {
        return next;
    }

    public void setElement(T element) {
        this.element = element;
    }

    public void setNext(Node<T> next) {
        this.next = next;
    }
}
```

#### 2) Write a class called MyLinkedList. The class should have the following :
##### a. Default constructor
##### b. Nodes for head and tail
```plaintext
public class MyLinkedList <E> {
    private Node<E> head;
    private Node<E> tail;
    private int size = 0;

    public MyLinkedList() {
        head=null;
        tail=null;
    }
}
```

#### 3) Implement the following methods from tutorial in this class:
##### a. public void addFirst(E e)
```plaintext
    public void addFirst(E e){
        Node<E> newNode = new Node<E>(e);
        newNode.next = head;
        head = newNode;
        if(tail==null)
            tail=head;
        size++;
    }
```
##### b. public void addLast(E e)
```plaintext
public void addLast(E e){
    if(tail == null)
        head = tail = new Node<>(e);
    else{
        tail.next = new Node<>(e);
        tail = tail.next;
    }
    size++;
}
```
##### c. public void add(int index, E e)
##### d. public E removeFirst()
##### e. public E removeLast()
##### f. public E remove(int index)

