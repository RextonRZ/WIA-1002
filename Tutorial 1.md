# Tutorial 1: Programming Fundamentals (Revision)

#### Cr: OOI RUI ZHE 23004947

### Q1(a):
```plaintext
package Tutorial1;
/**
 *
 * @author rz_rexton
 */
public class Telephone {

    private String areaCode;
    private int number;
    private static int numberOfTelephoneObject = 0;
    
    public Telephone(String areaCode,int number){
        this.areaCode = areaCode;
        this.number = number;
    }
    

    public String getAreaCode() {
        return areaCode;
    }

    public void setAreaCode(String areaCode) {
        this.areaCode = areaCode;
    }


    public int getNumber() {
        return number;
    }

    public void setNumber(int number) {
        this.number = number;
    }
    
    public String makeFullNumber(){
       return areaCode+"-"+number; 
    }
       
}
```

### Q1(b):
```plaintext
package Tutorial1;

/**
 *
 * @author ooiru
 */
public class Q1 {
    public static void main(String[] args) {
        Telephone[] arrays = new Telephone[5];
        
        //store the telephone numbers
        for(int i=0;i<arrays.length;i++){
            arrays[i] = new Telephone("03",79676300+i);
        }
        
        //print the telephone numbers
        for(int i=0;i<arrays.length;i++){
             System.out.println(arrays[i].makeFullNumber());;
        }
    }
}
```

### Q2
```plaintext
Ans:
(1) Performs Person's tasks
(2) Invoke Employee's overloaded constructor
(3) Performs Employee's tasks 
(4) Performs Faculty's tasks


Explanation:
class Person {                                                    //class Person is created                            
     public Person() {                                            //empty constructor (no parameter) is created to print (1) Performs Person's tasks
         System.out.println("(1) Performs Person's tasks");
     }
}

class Employee extends Person {                                   //Employee, a subclass of Person is created
     public Employee() {                                          //empty constructor 
         this("(2) Invoke Employee's overloaded constructor");    //'this' is used to invoke another constructor in the same class (call Employee(String s) )
         System.out.println("(3) Performs Employee's tasks ");    //after invoking, print 
     }
     public Employee(String s) {
         System.out.println(s);
     }
}

public class Faculty extends Employee {                           //Faculty, a subclass of Employee is created
     public Faculty() {                                           //empty constructor is created 
         System.out.println("(4) Performs Faculty's tasks");      //print
     }
     public static void main(String[] args) {                     //Main method 
         new Faculty();                                           //Create an instance of Faculty, which triggers the constructor chain
     }                                                            //causing the constructors of Employee and Person to execute as well. 
}


So the program will start excecute from Person -> Employee -> Faculty.
```


### Q3
```plaintext
Ans: a. AB

Explanation:
1)
class B {                                        //a toString method is create in class B and it will return B
    public String toString() {
    return "B";
    }
}

2)
class A extends B {                              //A is the subclass of B.
    public String toString() {                   //When a toString method is created, it overrides the toString method in class B,
    return "A";                                  //it returns A for the toString method
    }
}

3)
public class C {
     public static void main(String[] args) {    //In main method,
         Object[] o = {new A(), new B()};        //array of object is created to store the instances of class A and B
         System.out.print(o[0]);                 //print out the string representation for the instance of class A and B
         System.out.print(o[1]);
     }
}
```

