## WIA1002/WIB1002 Data Structure
### Tutorial: Generics

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

···

#### 
