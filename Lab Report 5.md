# Part 1
## Student's Request

**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

-Computer: Acer Laptop 

-Operating System: Windows 11 

-Web Browser: Google Chrome 

-Editor: Visual Studio Code

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

When running the bash script `calculate_average.sh` with the file `numbers.txt` containing a list of numbers, instead of calculating the average of the numbers, it always returns 0.0, no matter what numbers are there. With the following code in my java file, I get this using this txt file: 
```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CalculateAverage {
    public static void main(String[] args) {
        String filename = "numbers.txt";

        try {
            File file = new File(filename);
            Scanner scanner = new Scanner(file);

            int sum = 0;
            int count = 0;

            while (scanner.hasNextInt()) {
                int num = scanner.nextInt();
                count++;
                sum = sum / count;
            }

            double average = (double) sum / count;
            System.out.println("The average is: " + average);

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + filename);
        }
    }
}
```

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**
After running `$ ./calculate_average.sh` (after compiling the java file)
My .txt file has the following:
`numbers.txt`

```
10

5

8

2
```
Result:
`The average is: 0.0`

What is supposed to happen is (10+5+8+2)/4 = 6.25, but I get 0.0. No matter if I add or remove numbers, I keep getting 0.0, and can't seem to figure out why. 

## TA's Response
Hello, I see and understand what your issue is, and I thank you for being very clear and concise! Just a word of advice, have you tried checking to see if the loop is working? Perhaps, if you trace through the loop, we might be able to identify the issue.

I recommend making checkpoints to check the code at certain points. You can see what goes on by inserting a System.out.println() statement inside the loop to print the sum and count at that exact time. Maybe this can help us understand what's happening.

Let me know if this was helpful! Feel free to let me know if anything else comes up!

## Student's Response

Hello again! I implemented the advice you gave and after doing so, I think I figured out where the issue comes up. I added a bunch of System.out.println() lines to count as loop loops:

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CalculateAverage {
    public static void main(String[] args) {
        String filename = "numbers.txt";

        try {
            File file = new File(filename);
            Scanner scanner = new Scanner(file);

            int sum = 0;
            int count = 0;

            while (scanner.hasNextInt()) {
                int num = scanner.nextInt();
                count++;
                System.out.println(num);
                System.out.println(count);
                sum = sum / count;
                System.out.println(sum);
            }

            double average = (double) sum / count;
            System.out.println(average);

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + filename);
        }
    }
}
```

The `System.out.println()` lines printed this:

```
10
1
10
5
2
5
8
3
1
2
4
0
0.0
```

Specifically, I found that the line `sum = sum / count;` is where the issue came up, a foresight on my part. After editing my code and removing the line and the rest of the test `System.out.println()` lines, this was my final result!

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CalculateAverage {
    public static void main(String[] args) {
        String filename = "numbers.txt";

        try {
            File file = new File(filename);
            Scanner scanner = new Scanner(file);

            int sum = 0;
            int count = 0;

            while (scanner.hasNextInt()) {
                int num = scanner.nextInt();
                sum += num;
                count++;
            }

            double average = (double) sum / count;
            System.out.println("The average is: " + average);

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + filename);
        }
    }
}
```

Final Result:
`The average is: 6.25` (Correct!)

Final Project Directory:

-`CalculateAverage.java`

-`numbers.txt`

-`calculate_average.sh`

Before Fix:

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CalculateAverage {
    public static void main(String[] args) {
        String filename = "numbers.txt";

        try {
            File file = new File(filename);
            Scanner scanner = new Scanner(file);

            int sum = 0;
            int count = 0;

            while (scanner.hasNextInt()) {
                int num = scanner.nextInt();
                count++;
                sum = sum / count;
            }

            double average = (double) sum / count;
            System.out.println("The average is: " + average);

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + filename);
        }
    }
}
```

After Fix:

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class CalculateAverage {
    public static void main(String[] args) {
        String filename = "numbers.txt";

        try {
            File file = new File(filename);
            Scanner scanner = new Scanner(file);

            int sum = 0;
            int count = 0;

            while (scanner.hasNextInt()) {
                int num = scanner.nextInt();
                sum += num;
                count++;
            }

            double average = (double) sum / count;
            System.out.println("The average is: " + average);

            scanner.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + filename);
        }
    }
}
```

Code used to run test: 

`$ ./calculate_average.sh` (after compiling the java file {`javac CalculateAverage.java`, `java CalculateAverage`})

The corrected code ensures that the sum and count are calculated correctly within the loop, and the average is calculated accurately outside the loop using the final sum and count values.

# Part 2

Honestly, I really enjoyed the VIM section of the class. Professor said he would usually skip out on teaching it sometimes, but I was honestly enjoying this section the most. Being able to edit code like that was something new to me, and I had loads of fun. Using different keys to go up down left right with different keys was strange, yet exciting. I plan on using this more in the future, and further developing my skills.























