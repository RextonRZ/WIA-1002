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
##### Use the following code segment to answer parts (a) through (c):
```plaintext
Queue<Integer> q = new Queue<Integer>();
Scanner keyIn = new Scanner(System.in);
for (int i = 1; i <= 5; i++)
{
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
