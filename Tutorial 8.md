## WIA1002/WIB1002 Data Structure
### Tutorial 8:  Priority Queue

#### Question 1
##### Describe the main difference between Queue and PriorityQueue.
```plaintext
A priority queue has a largest-in, first-out behavior while a regular queue is a first-in and first-out (FIFO) data structure.

In a priority queue, elements are assigned with priorities. When accessing elements, the element with the highest priority is removed first.
In a regular queue is a first,elements are appended to the end of the queue and are removed from the beginning of the queue. 
```

#### Question 2
##### Briefly provide THREE (3) real-life example in using PriorityQueue
```plaintext
i) The emergency room in a hospital assigns priority numbers to patients; the patient with the highest priority is treated first.
2) To-Do List. Tasks with urgent deadlines or those that are critical for your work or personal life might be prioritized over less important tasks.
3) Airport Security Check. Passengers with disabilities, small children, or urgent flights might be given priority over others on security check point of an airport. 
```


#### Question 3
##### Show the output for every System.out.println ((a) – (f)) in the following code:
```plaintext
 import java.util.*;
public static void main(String args[])
 {
     PriorityQueue<String> pQueue = new PriorityQueue<String>();
     pQueue.offer("C++");
     pQueue.offer("Python");
     pQueue.offer("Java");
     pQueue.offer("Fortran");

     System.out.println("peek() gives us: "+ pQueue.peek()); //(a)

     System.out.println("The queue elements:"); //(b)
     Iterator itr = pQueue.iterator();
     while (itr.hasNext())
     System.out.println(itr.next()); //(b)

     pQueue.poll();
     System.out.println("After poll():"); //(c)
     Iterator<String> itr2 = pQueue.iterator();
     while (itr2.hasNext())
         System.out.println(itr2.next()); //(c)

     pQueue.remove("Java");
     System.out.println("After remove():"); //(d)
     Iterator<String> itr3 = pQueue.iterator();
     while (itr3.hasNext())
     System.out.println(itr3.next()); //(d)

     boolean b = pQueue.contains("Ruby");
     System.out.println ( "Priority queue contains Ruby or not?: " + b); //(e)

     Object[] arr = pQueue.toArray();
     System.out.println ( "Value in array: "); //(f)
     for (int i = 0; i<arr.length; i++)
         System.out.println ( "Value: " + arr[i].toString()) ; //(f)
     }
```

##### (a) 
```plaintext
peek() gives us: C++
```
##### (b) 
```plaintext
The queue elements:
C++
Python
Java
Fortran
```

##### (c)
```plaintext
After poll():
Python
Java
Fortran
```

##### (d)
```plaintext
After remove():
Python
Fortran
```

##### (e)
```plaintext
Priority queue contains Ruby or not?: false
```

##### (f)
```plaintext
Value in array:
Value: Python
Value: Fortran
```

#### Question 4
##### Answer the following sub-questions with referring to the following code:
```plaintext
public class PriorityQueue2 {
     public static void main(String... args ){
     PriorityQueueComparator pqc=new PriorityQueueComparator();
     PriorityQueue<String> pq=new PriorityQueue<String>(5,pqc);
     pq.add("Jason");
     pq.add("Ali");
     pq.add("Muhamad");
     for(String s:pq){
         System.out.println(s);
     }
     }
}

public class PriorityQueueComparator implements Comparator<String>{
    public int compare(String s1, String s2) {
         if (s1.length() < s2.length()) {
             return -1;
         }
         if (s1.length() > s2.length()) {
             return 1;
         }
         return 0;
    }
}
```

##### a) What is the purpose of the PriorityQueueComparator in the code?
```plaintext
The purpose of the PriorityQueueComparator class is to define the priority order for elements in the PriorityQueue. It is used to compare two String based on their length.
```

##### b) What is the output for the code?
```plaintext
Ali
Jason
Muhamad
```
