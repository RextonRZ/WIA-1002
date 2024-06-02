## WIA1002/WIB1002 Data Structure
### Tutorial 11:   Sorting and searching

#### Question 1:
#### Compare between linear search and binary search algorithms by searching for the numbers 45 and 54 in the following list :
##### 3 8 12 34 54 85 61 110

```plaintext
Linear search:
- Search sequentially from index 0 -> index n, stop when you found the element.
i) 45: 0,1,2,3,4,5,6,7 = Not in the list = 8 times checking
ii) 54: 0,1,2,3,4 = Found at index 4 = 4 times checking

Binary search:
- Sort: 3  8  12  34  54  61  85  110

i) Searching for 45: 
- Get the middle index = 3-> value of = 34
- Check, 45>34
- Get middle index = 5 -> value of =  61
- Check, 45<65
- is 45 =54? No
- So 45 is not in the list

ii) Searching for 54: 
- Get the middle index = 3-> value of = 34
- Check, 54>34
- Get middle index = 5 -> value of =  61
- Check, 54<65
- is 54=54? Yes
- Found

```

#### Question 2:
#### Describe the technique for each sort algorithm below. Given the following list:
##### 90 8 7 56 125 237 9 1 653

```plaintext
Show a trace of execution for:
a. Selection sort
b. Insertion sort
c. Bubble sort
d. Merge sort
```



