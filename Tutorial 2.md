## WIA1002/WIB1002 Data Structure
### Tutoria 2: Generics

#### Q1. 
```plaintext
public class Container<T> {
    private T t;
    
    public void add(T t){
        this.t = t;
    }
    
    public T retrieve() {
        return t;
    }
    
    public static void main(String[] args) {
        Container<Integer> intContainer =new Container<>();
        Container<String> strContainer = new Container<>();
        
        intContainer.add(50);
        strContainer.add("Java");
        
        System.out.println("Integer object: "+intContainer.retrieve());
        System.out.println("String object: "+strContainer.retrieve());
    }
}
```


#### Q2(a)(b)(c)
```plaintext
public class MyArray {
    public static <E>void listAll(E[] e){
        System.out.print("List of arrays ("+e.getClass().getComponentType().getSimpleName()+") : ");
        for(int i=0;i<e.length;i++){
            System.out.print(e[i]+" ");
        }
        System.out.println("");
    }
    
    public static void main(String[] args) {
        Integer[] num = {1,2,3,4,5};
        String[] names = {"Jane","Tom","Bob"};
        Character[] alpha = {'a','b','c'};
        
        listAll(num);
        listAll(names);
        listAll(alpha);
    }
}
```

#### Q3
#### What is a raw type? Why is a raw type unsafe? Why is the raw type allowed in Java?
```plaintext
A raw type is a generic class used without specifying the type parameter or concrete type.

Raw type is unsafe because it returns a runtime error instead of compile error.While using the raw type, the
compiler does not perform any type checking, allowing us to violate type safety guarantees provided by the Java compiler.

Raw type is allowed in Java to maintain backwards compatibility with older version. When generics were introduced in Java 5, the language designer wanted to ensure that the existing code that did not use generics would still compile and work as expected.

Example:
    ArrayList list1 = new ArrayList();
    list1.add(“hello world”);
    list.add(100);
    String s = (String)list1.get(0); //run time error

    ArrayList<String>list2 = new ArrayList<>();
    list2.add(“hello world”);
    list2.add(100); //compile error
    String s = list2.get(0); //compile error
```


#### Q4
#### What is erasure? Why are Java generics implements using erasure?
```plaintext
Erasure is a process in Java generics where the type parameter information is removed at compile time and is replaced with the raw type or type bound if one is specified.

Java generics implements using erasure to maintain backwards compatibility with existing Java code.By using erasure, the implementation of generics was able to reuse the existing Java bytecode format, allowing the generics code to be able to compiled to bytecode on any Java Virtual Machine(JVM), regardless whether the JVM support generics.
Using erasure also help to minimize memory and runtime overhead required by the JVM to support generics.
```



#### Q5, Q6
```plaintext
public class Duo<A,B> {

    private A first;
    private B second;
    
    public Duo(A first,B second){
        this.first = first;
        this.second = second;
    }
    
    public A getFirst() {
        return first;
    }

    public void setFirst(A first) {
        this.first = first;
    }

    public B getSecond() {
        return second;
    }

    public void setSecond(B second) {
        this.second = second;
    }
    
    //Tester 
    public static void main(String[] args) {
        Duo<Integer,String> sideShape= new Duo<>(39,"Square side length");
        System.out.println("First variable ("+sideShape.getFirst().getClass().getSimpleName()+") : "+sideShape.getFirst());
        System.out.println("Second variable ("+sideShape.getSecond().getClass().getSimpleName()+") : "+sideShape.getSecond());
        
        System.out.println("");
        System.out.println("Point coordinate: ");
        Duo<Double,Double> points = new Duo<>(3.3,2.2);
        System.out.println("x axis: "+points.getFirst());
        System.out.println("y axis: "+points.getSecond());
    }
    
}
```

#### Q7 
```plaintext
public class Q7 {
    public static <E> void allTransportation(ArrayList<?> list1, ArrayList<?> list2){
    }

    
    public static void main(String[] args) {
        ArrayList<String> vehicle = new ArrayList<>();
        ArrayList<Object> transportation = new ArrayList<>();
         
        allTransportation(vehicle, transportation);

    }
    
}
```


#### Q8
```plaintext
public class Q8 {
    public static void main(String[] args) {
        ArrayList<Integer> numOfCars = new ArrayList<>();
        ArrayList<Double> milesPerHour = new ArrayList<>();
        
        
        //add elements
        numOfCars.add(12);
        numOfCars.add(30);
        numOfCars.add(4);
        milesPerHour.add(16.44);
        milesPerHour.add(30.32);
        milesPerHour.add(23.96);
        
        System.out.println("Number of cars list: ");
        displayList(numOfCars);
        
        System.out.println("Miles Per Hour list: ");
        displayList(milesPerHour);
    }
    
    public static <E>void displayList(ArrayList<?> list){
        for (Object lists: list){
            System.out.println(lists);
        }
        System.out.println("");
    }
}
```


#### Q9
#### When the compiler encounters a generic class, interface, or method with an unbound type parameter, such as <T> or <E>, it replaces 
#### all occurrences of the type parameter with what type?
````plaintext
It replaces of the type parameter with the type ‘Object’.

The unbound type parameter has no restrictions on the type of object that can be used as a parameter.
````


#### Q10
#### When the compiler encounters a generic class, interface, or method with a bound type parameter, such as <T extends Number> or 
#### <E extends Comparable>, it replaces all occurrences of the type parameter with what type?
```plaintext
It replaces with bounded type of the parameter, that is Number and Comparable
```






