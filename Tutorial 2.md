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
···

#### 
