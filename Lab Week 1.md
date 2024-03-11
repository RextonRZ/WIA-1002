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


