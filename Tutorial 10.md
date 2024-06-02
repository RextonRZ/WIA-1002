## WIA1002/WIB1002 Data Structure
### Tutorial 10:  Recursion

## 1) Explain the problem that occurs when executing the recursive method f(0).
```plaintext
public static int f(int n) {
  if (n == 1)
    return n;
  else
    return n * f(n-1);
}
```


```plaintext
This method has a base case that stops recursion only when n equals 1. However, when f(0) is called, the method will attempt to compute f(0 - 1), which is f(-1), and this will continue indefinitely, decrementing n by 1 each time but never reaching the base case of n == 1. This endless recursion will eventually lead to a `StackOverflowError` because the call stack will keep growing without ever returning from the recursive calls.
```


## 2) Explain the problem that occurs when executing the recursive method f().
```plaintext
public static int f(int n) {
  if (n == 0)
    return n;
  else
    return f(n+1) + n;
}
```

```plaintext
The method has a base case that stops recursion only when n equals 0. However, for any non-negative integer n, the method will attempt to compute f(n + 1), which increases n by 1 each time. This means n will keep growing larger, moving further away from the base case of n == 0. This endless recursion will eventually lead to a `StackOverflowError` because the call stack will keep growing without ever returning from the recursive calls.

```

## 3) Write a recursive method to reverse a string.
## String → gnirts

```plaintext
public static void main(String[] args) {
        System.out.println(reverse("String"));
    }
    public static String reverse(String word){
        
        if (word ==null || word.length() == 1){
            return word;
        }else{
            return reverse(word.substring(1))+word.charAt(0);
            
        }
    }
```


## 4) Write a recursive method to calculate the following :

```plaintext
5 + 4 + 3 + 2 + 1.
State the base case and recursive case. Trace your solution using number, N of 5.
Algorithm :
1. Base case = 1
2. Recursive case = n + sum(n-1)
```

```plaintext
public static void main(String[] args) {
        System.out.println(recursive(5));
    }
    public static int recursive(int num){
        if (num ==1) return 1;
        else return num+recursive(num-1);
    }
```


## 5) Write a recursive method printDigit that prints an integer argument as its constituent digits, with a blank space separates each digit with the next. For example, if the argument is 4567, this method will print 4 5 6 7 on the screen. 


```plaintext
public static void main(String[] args) {
        printDigit(4567);
        System.out.println("");
    }
    public static void printDigit(int n){
        
        if (n>10) {
            printDigit(n/10);
            System.out.print(" ");
            System.out.print(n%10);
        }
        else System.out.print(n%10);
    }
```
