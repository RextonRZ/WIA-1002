## WIA1002/WIB1002 Data Structure
### Tutorial 9:  Graph

#### Question 1
##### Write an adjacency matrix and an adjacency list for the following graph
<p align="center">
<img src="Graph.png" alt="Graph" width="529" height="315">
</p>

<p align="center">
<img src="Adjacency matrix.png" alt="Adjacency matrix.png" width="709" height="315">
</p>

```plaintext
Adjacency matrix:

     A  B  C  D  E  F  G  H  I  
  ┌─                           ─┐
A │  0  0  1  1  0  0  0  0  0  │
B │  0  0  0  1  0  0  0  0  0  │
C │  0  0  0  0  1  1  0  0  0  │
D │  0  0  0  0  1  0  0  0  0  │
E │  0  0  0  0  0  0  1  0  0  │
F │  0  0  0  0  0  0  0  1  0  │
G │  0  0  0  0  0  0  0  1  0  │
H │  0  0  0  0  0  0  0  0  1  │
I │  0  0  0  0  0  0  0  0  0  │
  └─                           ─┘
```

```plaintext
Adjacency list: 
A        C  D
B        B
C        E  F
D        E
E        G
F        H
G        H
H        I
I
```
#### Question 2
##### 2. Represent the graph in question 1 using a 2 dimensional array. You use the adjacency matrix or the adjacency list for this purpose?
```plaintext
int[][] adjacencymatrix = {{0,0,1,1,0,0,0,0,0},
                           {0,0,0,1,0,0,0,0,0},
                           {0,0,0,0,0,1,1,0,0},
                           {0,0,0,0,0,1,0,0,0},
                           {0,0,0,0,0,0,1,0,0},
                           {0,0,0,0,0,0,0,1,0},
                           {0,0,0,0,0,0,0,1,0},
                           {0,0,0,0,0,0,0,0,1},
                           {0,0,0,0,0,0,0,0,0}
}
```
