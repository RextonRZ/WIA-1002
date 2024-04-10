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
```plaintext
public void display(){
        SNode<E> current = head;
        while(current != null){
            System.out.println(current.element+" ");
            current = current.next;
        }
        System.out.println("");
    }
```
#### 4) Write a test program called TestSList in the SList package. Using the appropriate methods you implemented in SList<E>, do the following:
##### 1) Append the following values individually: “Linked list, is, easy.”
##### 2) Display these values.
##### 3) Remove the word “Linked list” and display the removed value.
##### 4) Check if ‘difficult’ is in the list.
##### 5) Clear the list.

```plaintext
public class TestSList {
    public static void main(String[] args) {
        SList<String> a= new SList<>();
        
        //1) Append the following values individually: “Linked list, is, easy.”
        a.appendEnd("Linked list");
        a.appendEnd("is");
        a.appendEnd("easy.");
        
        //2) Display these values.
        a.display();
        
        //3) Remove the word “Linked list” and display the removed value. 
        a.removeInitial();
        a.display();
        
        //4) Check if ‘difficult’ is in the list. 
        System.out.println(a.contains("difficult"));
        
        //5) Clear the list.
        a.clear();
        a.display();
    }
}
```

### Question 2
#### A kindergarten needs to use an online student management system enabling its admin staff to manage their student list. Write a program using singly linked list to demonstrate the following:

##### i) public void add(E e)
##### ii) public void removeElement(E e)
##### iii) public void printList()
##### iv) public int getSize()
##### v) public boolean contains(E e)
##### vi) public void replace(E e, E newE) 

##### The program should demonstrate the following functions:
* Admin staff shall be able to interact with the program. The admin staff should enter a list
of student’s names.
* Display the list of the entered student’s names.
* Calculate the number of students in the list.
* Rename existing student’s name in the list with the new one specified by the admin staff.
* Delete a student name as specified by the admin staff.
```plaintext
public class StudentManagementSystem<E> {
    SNode<E> head;
    SNode<E> tail;
    int size = 0;

    public StudentManagementSystem() {
        this.head = null;
        this.tail=null;
    }
    
    public void add(E e){
        SNode<E> newStudent = new SNode<>(e);
        if(head == null) head = tail = newStudent;
        else{
            tail.next = newStudent;
            tail = tail.next;
        }
        size++;
    }
    
    public void removeElement(E e) {
        if(size==0) throw new IllegalStateException("Cannot remove from an empty list");
        if (head.element == e){
            head = head.next;
            size--;
            return; // Terminate the method 
        }
        SNode<E> current = head;
        while(current.next !=null){
            if(current.next.element.equals(e)){
                current.next = current.next.next;
                size--;
                return; // Terminate the method 
            }
            current = current.next;
        }
        throw new IllegalStateException("Element not found");
    }
    
    public void printList() {
        SNode<E> current = head;
        while(current != null){
            System.out.printf("%s", current.element.toString());
            current = current.next;
            System.out.printf("%s ", (current == null) ? "." : ","); //if current is not null will print ','
        }
    }
    
     public int getSize() {
         return this.size;
     }
    
    public boolean contains(E e) {
        SNode<E> temp = head;
        while(temp != null){
            if(temp.element.equals(e)){
                return true;
            }
            temp = temp.next;
        }
        return false;
    }
    
    public void replace(E e, E newE) {
         if(size==0) throw new IllegalStateException("The list is empty");
         SNode<E> current = head;
         while (current !=null){
             if(current.element.equals(e)){
                 current.element = newE;
                 return;
             }
             current = current.next;
         }
         throw new IllegalStateException("Element not found");
    }
    
    public static void main(String[] args) {
        
        Scanner sc = new Scanner(System.in);
        StudentManagementSystem<String> a = new StudentManagementSystem<>();
        
        //Input name 
        System.out.println("Enter your student name list. Enter 'n' to end.....");
        String name = sc.nextLine();
        while (!name.equalsIgnoreCase("n")) {
            a.add(name);
            name = sc.nextLine();
        }
        System.out.println();
        
        //Display results
        System.out.println("You have entered the following students' name : ");
        a.printList();
        
        //Display size
        System.out.println("\n\nThe number of students entered is : "+a.getSize());
    
        //Rename part
        System.out.println("\nAll the names entered are correct? Enter 'r' to rename the student name, 'n' to proceed.");
        String rename = sc.nextLine();
        if(rename.equalsIgnoreCase("r")){
            System.out.println("\nEnter the existing student name that you want to rename :");
            String entered = sc.nextLine();
            System.out.println("\nEnter the new name : ");
            String newname = sc.nextLine();
            
            a.replace(entered, newname);
            System.out.println("\nThe new student list is :");
            a.printList();
            System.out.println("\n\nDo you want to remove any of your student name? Enter 'y' for yes, 'n' to proceed.");
            String remove = sc.nextLine();
            if(remove.equalsIgnoreCase("y")){
                System.out.println("\nEnter a student name to remove :");
                String remove1 = sc.nextLine();
                a.removeElement(remove1);
                System.out.println("");
                System.out.println("The number of updated student is : "+a.getSize());
                System.out.println("The updated student list is :");
                a.printList();

            }
            
        }
        System.out.println("\n\nAll student data captured complete. Thank you! ");
    }
}
```

### Question 3
#### 1) Implement all the DoublyLinked List methods in the lecture’s slide. Write a test program by using the appropriate methods, do the following:
##### 1) Add first node with value of 1
##### 2) Add last node with value of 100
##### 3) Add node with value of 2 at position index of 2
##### 4) Remove node at position index of 3
##### 5) Traverse Forward
##### 6) Traverse Backward
##### 7) Print current size of linked list
##### 8) Clear all nodes in the linked list
##### 9) Print again current size of linked list
```plaintext
//Node Class for Double Linked List
public class DNode<E>{
    E element;
    DNode<E> prev;
    DNode<E> next;

    public DNode(E element, DNode<E> next, DNode<E> prev) {
        this.element = element;
        this.prev = prev;
        this.next = next;
    }
    
    public DNode(E element) {
        this(element, null, null);
    }
}


//DoubleLinkedList class
public class DoublyLinked<E> {
    DNode<E> head;
    DNode<E> tail;
    int size=0;

    public DoublyLinked() {
        this.head = null;
        this.tail = null;
    }
    
    public void addFirst(E element){
        DNode<E> tmp = new DNode(element, head, null);
        if(head!= null) head.prev = tmp;
        head = tmp;
        if(tail==null) tail = tmp;
        size++;
        System.out.println("adding: "+element);
    }
    
    public void addLast(E element){
        DNode<E> tmp = new DNode(element, null , tail);
        if(tail != null) tail.next = tmp;
        tail = tmp;
        if(head ==null) head = tmp;
        size++;
        System.out.println("adding: "+element);
    }
    
    
    public void add(int index, E element){
        if(index<0 || index >size) throw new IndexOutOfBoundsException();
        if (index ==0) addFirst(element);
        else if (index == size) addLast(element);
        else{
            DNode<E> temp = head;
            for(int i=1;i<index;i++){
                temp = temp.next;
            }
            DNode<E> insert = new DNode(element,temp,temp.prev);
            temp.prev.next = insert;
            temp.prev = insert;
            size++;
        }
    }
    
    public void iterateForward(){
        System.out.println("iterating forward...");
        DNode<E> current= head;
        while(current!= null){
            System.out.print(current.element+" ");
            current = current.next;
        }
    }
    
    public void iterateBackward(){
        System.out.println("iterating backward...");
        DNode<E> current = tail;
        while(current!=null){
            System.out.print(current.element+" ");
            current= current.prev;
        }
    }
    
    public E removeFirst(){
        if (size ==0) throw new NoSuchElementException();
        DNode<E> temp = head;
        head = head.next;
        head.prev = null;
        size--;
        System.out.println("deleted: "+temp.element);
        return temp.element;
    }
    
    public E removeLast(){
        if(size ==0) throw new NoSuchElementException();
        DNode<E> temp = tail;
        tail = tail.prev;
        tail.next = null;
        size--;
        System.out.println("deleted: "+temp.element);
        return temp.element;
    }
    
    public E remove(int index){
        E element = null;
        if (index<0 || index>= size) throw new IndexOutOfBoundsException();
        if(index == 0) element = removeFirst();
        else if (index == size-1) element = removeLast();
        else{
            DNode<E> temp = head;
            for(int i=1;i<index; i++){
                temp = temp.next;
            }
            temp.next.prev = temp.prev;
            temp.prev.next = temp.next;
            temp.prev = null;
            temp.next = null;
            size--;
            element = temp.element;
        }
        return element;
    }
    
    public void clear(){
        DNode<E> temp = head;
        while (head != null){
            temp = head.next;
            head.prev = head.next = null;
            head = temp;
        }
        temp = null;
        tail.prev = tail.next = null;
        size =0;
    }
    
    public int getSize(){
        return this.size;
    }
}


//Tester class
public class TestDList {
    public static void main(String[] args) {
        DoublyLinked<Integer> a = new DoublyLinked<>();

        a.addFirst(1);
        a.add(1,10);
        a.addLast(100);
        a.add(2, 2);
        
        a.remove(2);
        System.out.println("");
        a.iterateForward();
        System.out.println("");
        a.iterateBackward();;
        int prevSize = a.getSize();
        System.out.println("\nSize of current Double Linked List: "+ prevSize);
        a.clear();
        System.out.println("Successfully clear "+prevSize+" node(s)");
        System.out.println("");
        System.out.println("Size of current Double Linked List: "+ a.getSize());
    }
}
```

















