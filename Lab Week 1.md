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





