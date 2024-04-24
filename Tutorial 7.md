## WIA1002/WIB1002 Data Structure
### Tutorial 7: Queue

#### Question 1
##### 1. Name four everyday examples of a queue other than those discussed during lecture.
```plaintext
1) Airplane boarding
2) Theme Park Ride Queue
3) Restaurant Waiting Line
4) Drive-thru Line
```

#### 2. What is the difference between a queue and stack? 
```plaintext
Queue
- An item removed from the queue is the first element that was added into the queue
- has FIFO (first-in-first-out) ordering.

Stack
- the elements are accessed, inserted, and deleted only from the end, called the top, of the stack
- has LIFO (last-in-first-out) ordering.
```

#### 3. Use the following code segment to answer parts (a) through (c):
```plaintext
Queue<Integer> q = new Queue<Integer>();
Scanner keyIn = new Scanner(System.in);
  for (int i = 1; i <= 5; i++) {
      if (keyIn.nextBoolean())
        System.out.print(i + " ");
      else
      q.enqueue(i);
  }
}
while (!q.isEmpty())
  System.out.print(q.dequeue() + " ");
  System.out.println();
```

##### (a) What is the output for the following input sequence?
##### true false false true true
```plaintext
1 4 5 2 3 
```

##### (b) Is it possible to have output: 1 3 5 4 2? If yes, give an input sequence that produces the output; or else, provide justification to your answer
```plaintext
No it is not possible. The code can only produce two sublist of increasing values. 1 3 5 is an increasing order, but 4 2 is in a descending order.
```

##### (c) Give at least three input sequences that produce the output: 1 2 3 4 5
```plaintext
Input 1:
true true true true true

Input 2:
false false false false false

input 3:
true true true true false
```

##### 4. Hand trace a queue X through the following operations:
```plaintext
 X.enqueue(new Integer(14));
 X.enqueue(new Integer(3));
 X.enqueue(new Integer(5));
 Object Y = X.dequeue();
 X.enqueue(new Integer(7));
 X.enqueue(new Integer(9));
 Y = X.dequeue();
 X.enqueue(new Integer(2));
 X.enqueue(new Integer(4));
```

##### Given the resulting queue X above, what would be the result of each of the following?

##### a) X.front();
```plaintext
5
```

##### b) Y = X.dequeue();
#####    X.enqueue(new Integer(10));
#####    X.front();
```plaintext
7
```

##### c) Y = X.dequeue();
```plaintext
Y = 7
```

##### d) X.front();
```plaintext
9
```


