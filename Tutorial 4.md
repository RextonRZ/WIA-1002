## WIA1002/WIB1002 Data Structure
### Tutorial 4: Linked List

#### Question 1
##### (a)Assume that a node class called Node<E> exist. Create two nodes called node1 and node2. Node1 contains alphabet ‘a’ and node2 contains alphabet ‘z’. Also, create 2 references, head and tail. Let head points to node 1 and tail points to node 2.
```plaintext
Node<Character> node1 = new Node<>('a');
Node<Character> node2 = new Node<>('z'):
Node<Character> head = node1;
Node<Character> tail = node2;
```

##### (b) Draw the nodes from (a).
<p align="center">
<img src="Tutoq1.png" alt="Node from (a)" width="400" height="370">
</p>


##### (c)  Write a statement/code for node1 accessing the node2. Modify 1(b) to show this
```plaintext
head.next = tail;
```
<p align="center">
<img src="Tutoq1(c).png" alt="node1 accessing node2 (c)" width="400" height="370">
</p>

##### (d) Create a new node, firstNode. Add this new node at the first location of all existing nodes. Draw these nodes. 
```plaintext
Sample:
Node<Character> firstNode = new Node<>('b');
firstNode.next = head;
head = firstNode;
```
<p align="center">
<img src="Tutoq1(d).png" alt="node1 accessing node2 (c)" width="400" height="370">
</p>

##### (e) If we have no information about the status of a linked-list, what are the conditions we need to consider to perform the operation in (d)?
```plaintext
* Add node
* Is the new node, the only node in the list?
* If there is already many nodes in the list
```

##### (f) Write a list of operations/steps/pseudocode needed to add the firstNode to the first location.
```plaintext
* Condition 1:
  -> If tail == null, then tail == head
       - This refers to the same node (both head and tail)

* Condition 2:
  -> Create a new node object
  -> Assign the new node's(firstNode) next reference to the current first node (current head)
  -> Assign the new node(firstNode) as the head
```

##### (g) Write codes to assign the firstNode to the first location. 
```plaintext
public void addFirst(Character e){
  Node<Character> firstNode = new Node<>('a');
  firstNode.next = head;
  head = firstNode;
  size+=1;
  if(tail == null){
    tail = head;
  }
}
```




