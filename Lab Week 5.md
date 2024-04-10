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

