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
```plaintext
```
