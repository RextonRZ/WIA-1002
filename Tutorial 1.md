# Tutorial 1: Programming Fundamentals (Revision)

#### Cr: OOI RUI ZHE 23004947

### Q1(a):
```plaintext
package Tutorial1;
/**
 *
 * @author rz_rexton
 */
public class Telephone {

    private String areaCode;
    private int number;
    private static int numberOfTelephoneObject = 0;
    
    public Telephone(String areaCode,int number){
        this.areaCode = areaCode;
        this.number = number;
    }
    

    public String getAreaCode() {
        return areaCode;
    }

    public void setAreaCode(String areaCode) {
        this.areaCode = areaCode;
    }


    public int getNumber() {
        return number;
    }

    public void setNumber(int number) {
        this.number = number;
    }
    
    public String makeFullNumber(){
       return areaCode+"-"+number; 
    }
       
}
```

### Q1(b):
```plaintext
package Tutorial1;

/**
 *
 * @author ooiru
 */
public class Q1 {
    public static void main(String[] args) {
        Telephone[] arrays = new Telephone[5];
        
        //store the telephone numbers
        for(int i=0;i<arrays.length;i++){
            arrays[i] = new Telephone("03",79676300+i);
        }
        
        //print the telephone numbers
        for(int i=0;i<arrays.length;i++){
             System.out.println(arrays[i].makeFullNumber());;
        }
    }
}
```

### Q2


