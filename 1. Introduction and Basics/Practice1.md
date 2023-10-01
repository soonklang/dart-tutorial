# Practice1
แบบฝึกหัดในเรื่อง Introduction and Basics
## 1.Write a program to print your name in Dart.
 ```dart
  void main()
{
    var name = "John";
    print(name);
}
   ```
### • C
```c
#include <stdio.h>
 main() {
  printf("John");
}
```
### • Java
```java
import java.util.*;
   class Sample {
    public static void main(String args[])
    {
        System.out.println("John");
    }
}
```
### • Python
```python
   print("John");
```
## 2.Write a program to print Hello I am “John Doe” and Hello I’am “John Doe” with single and double quotes.
 ```dart
  void main() {
  String name = "John Doe";

  // Using double quotes
  print('Hello I am "$name"');

  // Using single quotes
  print('Hello I\'am "$name"');
}
   ```
### • C
```c
#include <stdio.h>

int main() {
    printf("Hello I am \"John Doe\"\n");
    printf("Hello I\'am \"John Doe\"\n");

    return 0;
}
```
### • Java
```java
public class Main {
    public static void main(String[] args) {
        String name = "John Doe";

        // Using double quotes
        System.out.println("Hello I am \"" + name + "\"");

        // Using single quotes
        System.out.println("Hello I'am \"" + name + "\"");
    }
}
```
### • Python
```python
name = "John Doe"

# Using double quotes
print("Hello I am \"" + name + "\"")

# Using single quotes
print("Hello I'am \"" + name + "\"")
```
## 3.Declare constant type** of int set value 7.
```dart
void main() {
  const int myConstant = 7;
  print(myConstant);
}
```
### • C
```c
#include <stdio.h>

int main() {
    const int myConstant = 7;
    printf("%d\n", myConstant);
    return 0;
}
```
### • Java
```java
public class Main {
    public static final int MY_CONSTANT = 7;

    public static void main(String[] args) {
        System.out.println(MY_CONSTANT);
    }
}
```
### • Python
```python
MY_CONSTANT = 7

def main():
    print(MY_CONSTANT)

if __name__ == "__main__":
    main()
```
## 4.Write a program in Dart that finds simple interest. Formula= (p * t * r) / 100
```dart
void main() {
  double principal = 1000; // Principal amount
  double rate = 5; // Rate of interest in percentage
  double time = 2; // Time in years

  double simpleInterest = (principal * rate * time) / 100;

  print('Principal: \$${principal.toStringAsFixed(2)}');
  print('Rate: ${rate.toStringAsFixed(2)}%');
  print('Time: ${time.toStringAsFixed(2)} years');
  print('Simple Interest: \$${simpleInterest.toStringAsFixed(2)}');
}
```
### • C
```c
#include <stdio.h>

int main() {
    double principal = 1000; // Principal amount
    double rate = 5; // Rate of interest in percentage
    double time = 2; // Time in years

    double simpleInterest = (principal * rate * time) / 100;

    printf("Principal: $%.2f\n", principal);
    printf("Rate: %.2f%%\n", rate);
    printf("Time: %.2f years\n", time);
    printf("Simple Interest: $%.2f\n", simpleInterest);

    return 0;
}
```
### • Java
```java
public class SimpleInterestCalculator {
    public static void main(String[] args) {
        double principal = 1000; // Principal amount
        double rate = 5; // Rate of interest in percentage
        double time = 2; // Time in years

        double simpleInterest = (principal * rate * time) / 100;

        System.out.println("Principal: $" + principal);
        System.out.println("Rate: " + rate + "%");
        System.out.println("Time: " + time + " years");
        System.out.println("Simple Interest: $" + simpleInterest);
    }
}
```
### • Python
```python
def main():
    principal = 1000  # Principal amount
    rate = 5  # Rate of interest in percentage
    time = 2  # Time in years

    simple_interest = (principal * rate * time) / 100

    print(f"Principal: ${principal:.2f}")
    print(f"Rate: {rate:.2f}%")
    print(f"Time: {time:.2f} years")
    print(f"Simple Interest: ${simple_interest:.2f}")

if __name__ == "__main__":
    main()
```
## 5.Write a program to print a square of a number using user input.
```dart
import 'dart:io';

void main() {
  // Prompt the user to enter a number
  stdout.write("Enter a number: ");
  
  // Read user input
  String input = stdin.readLineSync()!;
  
  // Convert the input to a double
  double number = double.parse(input);
  
  // Calculate the square
  double square = number * number;
  
  // Print the square
  print("Square of $number is $square");
}
```
### • C
```c
#include <stdio.h>

int main() {
    double number, square;

    printf("Enter a number: ");
    scanf("%lf", &number);

    square = number * number;

    printf("Square of %.2f is %.2f\n", number, square);

    return 0;
}
```
### • Java
```java
import java.util.Scanner;

public class SquareCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a number: ");
        double number = scanner.nextDouble();

        double square = number * number;

        System.out.println("Square of " + number + " is " + square);

        scanner.close();
    }
}
```
### • Python
```python
def main():
    number = float(input("Enter a number: "))
    square = number ** 2
    print(f"Square of {number} is {square}")

if __name__ == "__main__":
    main()
```
## 6.Write a program to print full name of a from first name and last name using user input.
```dart
import 'dart:io';

void main() {
  stdout.write("Enter your first name: ");
  String firstName = stdin.readLineSync()!;

  stdout.write("Enter your last name: ");
  String lastName = stdin.readLineSync()!;

  String fullName = "$firstName $lastName";

  print("Full Name: $fullName");
}
```
### • C
```c
#include <stdio.h>
#include <string.h>

int main() {
    char firstName[50];
    char lastName[50];
    char fullName[100];

    printf("Enter your first name: ");
    scanf("%s", firstName);

    printf("Enter your last name: ");
    scanf("%s", lastName);

    strcpy(fullName, firstName);
    strcat(fullName, " ");
    strcat(fullName, lastName);

    printf("Full Name: %s\n", fullName);

    return 0;
}
```
### • Java
```java
import java.util.Scanner;

public class FullNamePrinter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your first name: ");
        String firstName = scanner.nextLine();

        System.out.print("Enter your last name: ");
        String lastName = scanner.nextLine();

        String fullName = firstName + " " + lastName;

        System.out.println("Full Name: " + fullName);

        scanner.close();
    }
}
```
### • Python
```python
def main():
    first_name = input("Enter your first name: ")
    last_name = input("Enter your last name: ")

    full_name = first_name + " " + last_name

    print("Full Name:", full_name)

if __name__ == "__main__":
    main()
```

## 7.Write a program in Dart to remove all whitespaces from String.
```dart
void main() {
  String input = "This is a sample string with spaces";

  String output = input.replaceAll(' ', '');

  print("Original String: $input");
  print("String without Spaces: $output");
}
```
### • C
```c
#include <stdio.h>
#include <string.h>

int main() {
    char input[] = "This is a sample string with spaces";
    char output[sizeof(input)]; // Make sure the output buffer is big enough

    int j = 0;
    for (int i = 0; i < strlen(input); i++) {
        if (input[i] != ' ') {
            output[j++] = input[i];
        }
    }
    output[j] = '\0';

    printf("Original String: %s\n", input);
    printf("String without Spaces: %s\n", output);

    return 0;
}
```
### • Java
```java
import java.util.Scanner;

public class RemoveWhitespace {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        String output = input.replaceAll(" ", "");

        System.out.println("Original String: " + input);
        System.out.println("String without Spaces: " + output);

        scanner.close();
    }
}
```
### • Python
```python
def main():
    input_string = input("Enter a string: ")

    output_string = input_string.replace(" ", "")

    print("Original String:", input_string)
    print("String without Spaces:", output_string)

if __name__ == "__main__":
    main()
```
## 8.Write a dart program to convert String to int.
```dart
void main() {
  String input = "12345"; // Replace this with the input string
  int convertedNumber = int.parse(input);

  print("Original String: $input");
  print("Converted Number: $convertedNumber");
}
```
### • C
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char input[] = "12345"; // Replace this with the input string
    int convertedNumber = atoi(input);

    printf("Original String: %s\n", input);
    printf("Converted Number: %d\n", convertedNumber);

    return 0;
}
```
### • Java
```java
import java.util.Scanner;

public class StringToInt {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String input = scanner.nextLine();

        int convertedNumber = Integer.parseInt(input);

        System.out.println("Original String: " + input);
        System.out.println("Converted Number: " + convertedNumber);

        scanner.close();
    }
}
```
### • Python
```python
def main():
    input_string = input("Enter a string: ")
    converted_number = int(input_string)

    print("Original String:", input_string)
    print("Converted Number:", converted_number)

if __name__ == "__main__":
    main()
```
## < Slide&Video>
[Practice.pptx](https://github.com/soonklang/dart-tutorial/files/12777734/620710327.Practice.pptx) <br>
https://youtu.be/or15PgLEskY?si=SgAuMLiQjBy4Ul3O
## < Reference >
https://dart-tutorial.com/introduction-and-basics/questions-for-practice-1/<br>
https://www.tamemo.com/post/172/dart-101-intro/<br>
https://www.geeksforgeeks.org/introduction-to-python/<br>
https://www.geeksforgeeks.org/introduction-to-java/<br>
https://www.geeksforgeeks.org/c-language-introduction/
