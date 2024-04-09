## WIA1002/WIB1002 Data Structure
### Tutorial 5: Linked List & Doubly Linked List

#### Question 1
```plaintext
1   public E xyz(int index,E e)
2   {
3     Node<E> current=head;
4     Node<E> temp;
5       if(index<0) return null;
6       else if(index>=size-1) {
7           this.addLast(e);
8           return null;
9       }
10      else if(index==0) {
11         temp=head;
12         head.element=e;
13         return temp.element;
14      }else{
15         for (int i = 1; i < index; i++) {
16             current=current.next;
17         }
18         temp=current.next;
19         current.next.element=e;
20         return temp.element;
21      }
```

##### Given method xyz with 2 arguments:
##### a) Based on the above source code, explain what the lines of code do from line 10 – 21.

Line 10 to Line 21 adds the element e of generic type E into the linked list at the index of index. Line 10 to 14 adds e to the first index of the linked list, whereas line 14 to line 21 adds e to any index position in the linked list.


##### b) What is the main purpose of the method xyz()?

The main purpose of xyz() is to insert a node of element e into the specific index of the linked list.

