## WIA1002/WIB1002 Data Structure
### Tutorial 10:  Recursion (Applications)

#### Question 1
<p align="center">
<img src="RecursionQ1.png" alt="RecursionQ1" width="631" height="182">
</p>

##### Tips:
<p align="center">
<img src="RecursionQ1b.png" alt="RecursionQ1B" width="731" height="749">
</p>


```plaintext
public class Questionl {

    public static int F(int s, int t){
        if (t == 1)
            return s;
        else if (s == 1)
            return 1;
        else{
            int partl = F(s-1, t);
            int part2 = F(s, t-1);
            return partl + part2;
        }
    }

    public static void main(String[] args) {
          int s =2, t=3;
          System.out.println(("F("+s+", "+t+") = " + F(s,t)));
    }
}

```
