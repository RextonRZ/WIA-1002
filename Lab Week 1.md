# Lab 1: Programming Fundamentals (Revision)

#### Cr: OOI RUI ZHE 23004947

### Question 1
### Part 1:
#### 1.
```plaintext
Thursday, 11 March 2024.
My name is Ooi Rui Zhe (your name) with matrix number, 23004947 (your matrix number). I am
majoring in Artificial Intelligence (your majoring). This is my first (specify) time taking the
Data Structure subject. At the moment, I am feeling nervous (your emotion) about taking this
subject. This is because I didn't do well in my previous Programming 1 course (describe the cause of your emotion about taking DS).
I acquired B+ (your grade) for my previous Programming 1 course. It’s not too bad. So, I
think I can manage to get A (the expected grade) for this DS subject this term. In order
to do well in the subject, I will work hard (what will you do). Wish me luck!!! 
```

#### 2.
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package ds.lab;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.util.Scanner;

/**
 *
 * @author ooiru
 */
public class Q1 {

    public static void main(String[] args) {
        try{
            Scanner in = new Scanner(new FileInputStream("OOIRUIZHE_23004947.txt"));
                while (in.hasNextLine()) {
                String line = in.nextLine();
                if (line.startsWith("My name is")) {
                    String name = line.substring(line.indexOf("My name is") + 10, line.indexOf("(your name)")).trim();
                    System.out.println("Name: " + name);

                    String matrixNumber = line.substring(line.indexOf("with matrix number") + 19, line.indexOf("(your matrix number)")).trim();
                    System.out.println("Matrix Number: " + matrixNumber);
                } else if (line.contains("majoring in")) {
                    String majoring = line.substring(line.indexOf("majoring in") + 12, line.indexOf("(your majoring)")).trim();
                    System.out.println("Majoring: " + majoring);

                    String timeTaking = line.substring(line.indexOf("This is my") + 11, line.indexOf("(specify)")).trim();
                    System.out.println("Time Taking: " + timeTaking);
                } else if (line.contains("feeling")) {
                    String emotion = line.substring(line.indexOf("At the moment, I am feeling") + 28, line.indexOf("(your emotion)")).trim();
                    System.out.println("Emotion: " + emotion);
                    
                } else if (line.contains("This is because")) {
                    String emotion = line.substring(line.indexOf("This is because") + 16, line.indexOf("(describe")).trim();
                    System.out.println("Cause of your emotion about taking DS: " + emotion);


                } else if (line.contains("acquired")) {
                    String grade = line.substring(line.indexOf("I acquired") + 10, line.indexOf("(your grade)")).trim();
                    System.out.println("Previous Grade: " + grade);

                } else if (line.contains("expected grade")) {
                    String expectedGrade = line.substring(line.indexOf("get") + 3, line.indexOf("(the expected grade)")).trim();
                    System.out.println("Expected Grade: " + expectedGrade);

                    
                } else if (line.contains("in the subject,")){    
                    String plan = line.substring(line.indexOf("subject,") + 8, line.indexOf("(what will you do)")).trim();
                    System.out.println("Plan: " + plan);
                }
            }
            in.close();
        }catch(FileNotFoundException e){
            System.out.println("File was not found.");
        }catch(IOException e){
            System.out.println("Problem with file output");
        }
    }
}
```

#### Part 2:
```plaintext
* How you have performed in the class?
I have performed well in the class.

* Are you happy with your performance?
I am happy with my performance

* What has learning DS taught you / what did you learn from DS?
Learning DS taught me to be more patient and analytical.

* Is there any change to your target grade?
My target grade remains the same, which is A.

* What you did well during the course?
During the course, I consistently engaged with the material on Spectrum and completed assignments on time.

* What could have been done better during the course?
I could have dedicated more time to practice problems and past year questions to deepen my understanding of certain topics.
```

#### 3.
```plaintext
//write letter part 2 based on information read from Part 2
public class Part2 {
    public static void main(String[] args) {
        String performance = "";
        String emotion = "";
        String lesson = "";
        String target = "";
        String how = "";
        String better = "";
        try {
            Scanner in = new Scanner(new FileInputStream("(Part 2)ans the questions.txt"));
            while (in.hasNextLine()) {
                String line = in.nextLine();
                if (line.startsWith("* How")) {
                    performance = in.nextLine();
                } else if (line.startsWith("* Are")) {
                    emotion = in.nextLine();
                } else if (line.startsWith("* What has")) {
                    lesson = in.nextLine();
                } else if (line.startsWith("* Is")) {
                    target = in.nextLine();
                } else if (line.startsWith("* What you")) {
                    how = in.nextLine();
                } else if (line.startsWith("* What could")) {
                    better = in.nextLine();
                }
            }
            in.close();
            
            // Construct the letter using the extracted information
            String letterP2 = "It's me again. Finally, it's the end of the term and the DS class has finished! " +
                              performance + emotion + lesson + target + how + better;
            String[] word = letterP2.split(" ");
            try{
                PrintWriter out = new PrintWriter(new FileOutputStream("OOIRUIZHE_23004947(Part 2).txt"));
                out.println("Thursday, 18 June 2021.");
                out.println();
                for (int i = 0; i < word.length; i++) {
                    out.print(word[i] + " "); // Print each word with a space separator
                    if ((i + 1) % 19 == 0) { // Add a newline every 20 words
                        out.println();
                    }
                }

                out.close();
            }catch(IOException e){
                System.out.println("Problem with file output.");
            }

            System.out.println(letterP2); // Print the constructed letter
        } catch (FileNotFoundException e) {
            System.out.println("File was not found");
        } catch (IOException e) {
            System.out.println("Problem with file output");
        }
    }
}


//append both letter part 1 and 2
public class AppendFiles {
    public static void main(String[] args) {
        String filename1 = "OOIRUIZHE_23004947.txt";
        String filename2 = "OOIRUIZHE_23004947(Part 2).txt";

        try {
            PrintWriter out = new PrintWriter(new FileWriter("combined_letter.txt"));

            BufferedReader reader1 = new BufferedReader(new FileReader(filename1));
            String line;
            while ((line = reader1.readLine()) != null) {
                out.println(line);
            }
            reader1.close();

            // Read and append contents of the second file
            BufferedReader reader2 = new BufferedReader(new FileReader(filename2));
            out.println("\n\n");
            while ((line = reader2.readLine()) != null) {
                out.println(line);
            }
            reader2.close();

            out.close();

            System.out.println("Contents of " + filename1 + " and " + filename2 + " have been appended to combined_letter.txt");
        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

### Question 2
#### 1.
```plaintext
public class Q2Text1 {
    public static void main(String[] args) {
        try{
            Scanner in = new Scanner(new FileInputStream("text1.txt"));
            int chartotal = 0;
            while (in.hasNextLine()){
                String line = in.nextLine();
                String[] charac = line.split(",");
                chartotal+=charac.length;
            }
            in.close();
            System.out.println("Total number of characters retrieved: "+chartotal);
        }catch(FileNotFoundException e){
            System.out.println("File was not found.");
        }catch(IOException e){
            System.out.println("Problem with file output.");
        }
    }
}
```

### Question 2
#### 2(a)
```plaintext
public class Q2Text2 {
    public static void main(String[] args) {
        try{
            Scanner in = new Scanner(new FileInputStream("text2.txt"));
            int chartotal = 0;
            while (in.hasNextLine()){
                String line = in.nextLine();
                String[] num = line.split(", ");
                for (String nums : num) {
                    int numValue = Integer.parseInt(nums);
                    while (numValue != 0) {
                        int digit = numValue % 10;
                        if (digit > 0) {
                            chartotal++;
                        }
                        numValue /= 10;
                    }
                }
            }
            in.close();
            System.out.println("Total number of characters retrieved: "+chartotal);
        }catch(FileNotFoundException e){
            System.out.println("File was not found.");
        }catch(IOException e){
            System.out.println("Problem with file output.");
        }
    }
}
```

### Question 2
#### 2(b)
```plaintext
public class Q2Text3 {
    public static void main(String[] args) {
        try{
            Scanner in = new Scanner(new FileInputStream("text3.txt"));
            int chartotal = 0;
            while (in.hasNextLine()) {
                String line = in.nextLine();
                String[] num = line.split("; ");
                for (String nums : num) {
                    String[] numbers = nums.split("\\.");
                    for (String number : numbers) {
                        chartotal += number.length();
                    }
                }
            }
            in.close();
            System.out.println("Total number of characters retrieved: "+chartotal);
        }catch(FileNotFoundException e){
            System.out.println("File was not found.");
        }catch(IOException e){
            System.out.println("Problem with file output.");
        }
    }
}
```

### Question 2
#### 2(c)
```plaintext
public class Q2Text4 {
    public static void main(String[] args) {
        try{
            Scanner in = new Scanner(new FileInputStream("text4.txt"));
            int chartotal = 0;
            while (in.hasNextLine()){
                String line = in.nextLine();
                chartotal+=line.length();
            }
            in.close();
            System.out.println("Total number of characters retrieved: "+chartotal);
        }catch(FileNotFoundException e){
            System.out.println("File was not found.");
        }catch(IOException e){
            System.out.println("Problem with file output.");
        }
    }
}
```


### Question 3
#### Implement a class Account
```plaintext
public class Account {

    private int id;
    private double balance;
    private double annualInterestRate;
    private final Date dateCreated;
    
    public Account(){
        id=0;
        balance=0;
        annualInterestRate =0;
        dateCreated = new Date();
    }
    
    public Account(int id, double balance) {
        this.id = id;
        this.balance = balance;
        annualInterestRate = 0;
        dateCreated = new Date();
    }
    

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }

    public double getAnnualInterestRate() {
        return annualInterestRate;
    }

    public void setAnnualInterestRate(double annualInterestRate) {
        this.annualInterestRate = annualInterestRate;
    }
    
    public Date getDateCreated() {
        return dateCreated;
    }
    
    public double getMonthlyInterestRate(){
        return annualInterestRate/12;
    }
    
    public double getMonthlyInterest(){
        return balance*(getMonthlyInterestRate()/100);
    }
    
    public boolean withdraw(double amount){
        if(amount>balance){
            System.out.println("Insufficient balance.");
            return false;
        }else{
            balance-=amount;
            return true;
        }
    }
    
    public double deposit(double amount){
        balance+=amount;
        return balance;
    }
}
```


### Question 3
#### Tester program
```plaintext
public class Q3 {
    public static void main(String[] args) {
        Account Rexton = new Account(1122,20000);
        Rexton.setAnnualInterestRate(4.5);
        System.out.println("Initial Balance : "+Rexton.getBalance());
        Rexton.withdraw(2500);
        Rexton.deposit(3000);
        System.out.println("Final Balance : "+Rexton.getBalance());
        System.out.println("Monthly Interest : "+Rexton.getMonthlyInterest());
        System.out.println("Date where account created: "+Rexton.getDateCreated());
    }
}
```


### Question 4
#### Account1 class 
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package ds.lab;

/**
 *
 * @author ooiru
 * 
 */
import java.util.ArrayList;
import java.util.Date;
public class Account1 {
    private String name;
    private int id;
    private double balance;
    private double annualInterestRate;
    private final Date dateCreated;
    private final ArrayList<Transaction> transactions;
    
    public Account1(){
        this.id=0;
        this.name="";
        this.balance=0;
        dateCreated = new Date();
        transactions = new ArrayList<>();
    }
    
    public Account1(int id, String name,double balance){
        this.id=id;
        this.name=name;
        this.balance=balance;
        dateCreated = new Date();
        transactions = new ArrayList<>();
    }
    
        public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }

    public double getAnnualInterestRate() {
        return annualInterestRate;
    }

    public void setAnnualInterestRate(double annualInterestRate) {
        this.annualInterestRate = annualInterestRate;
    }
    
    public Date getDateCreated() {
        return dateCreated;
    }
    
    public double getMonthlyInterestRate(){
        return annualInterestRate/12;
    }
    
    public double getMonthlyInterest(){
        return balance*(getMonthlyInterestRate()/100);
    }
    
    public boolean withdraw(double amount){
        if (amount <= balance) {
            balance -= amount;
            transactions.add(new Transaction('W', amount, balance, "Withdraw"));
            return true;
        }
        return false;
    }
    
    public double deposit(double amount) {
        balance += amount;
        transactions.add(new Transaction('D', amount, balance, "Deposit"));
        return balance;
    }
    
    public String toString() {
        StringBuilder str = new StringBuilder(String.format("Account Summary\nHolder Name: %s\nAnnual Interest Rate: %.2f %%\nBalance: %.2f\n", name, annualInterestRate, balance));
        str.append(String.format("Transaction History:\n%-30s %5s %10s %10s %15s\n", "Date", "Type", "Amount", "Balance", "Description"));

        for (Transaction transaction : transactions) {
            str.append(String.format("%-30s %5s %10.2f %10.2f %15s\n",
                    dateCreated, transaction.getType(), transaction.getAmount(),
                    transaction.getBalance(), transaction.getDescription()));
        }
        return str.toString();
    }
}
```

### Question 4
#### Transaction class
```plaintext
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package ds.lab;

/**
 *
 * @author ooiru
 */
import java.util.Date;

public class Transaction {
    private Date date;
    private char type;
    private final double amount;
    private final double balance;
    private final String description;

    public Transaction(char type, double amount, double balance, String description) {
        this.type = type;
        this.amount = amount;
        this.balance = balance;
        this.description = description;
    }

    public Date getDate() {
        return date;
    }

    public void setDate(Date date) {
        this.date = date;
    }

    public char getType() {
        return type;
    }

    public void setType(char type) {
        this.type = type;
    }

    public double getAmount() {
        return amount;
    }

    public double getBalance() {
        return balance;
    }

    public String getDescription() {
        return description;
    }
}

```


### Question 4
#### Tester class
```plaintext
public class Q4 {
    public static void main(String[] args) {
        Account1 a= new Account1(1112,"George",1000);
        a.setAnnualInterestRate(1.5);
        a.deposit(30);
        a.deposit(40);
        a.deposit(50);
        a.withdraw(5);
        a.withdraw(4);
        a.withdraw(2);
        System.out.println(a);
    }
}
```








