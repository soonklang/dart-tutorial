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
```
### • C
```c
```
### • Java
```java
```
### • Python
```python
```
## 7.Write a program to find quotient and remainder of two integers.
```dart
```
### • C
```c
```
### • Java
```java
```
### • Python
```python
```
## 8.Write a program to swap two numbers.
### • C
```c```
### • Java
```c```
### • Python
```c```
## 9.Write a program in Dart to remove all whitespaces from String.
### • C
```c```
### • Java
```c```
### • Python
```c```
## 10.Write a dart program to convert String to int.
### • C
```c```
### • Java
```c```
### • Python
```c```
## 11.Suppose, you often go to restaurant with friends and you have to split amount of bill. Write a program to calculate split amount of bill. Formula= (total bill amount) / number of people
### • C
```c```
### • Java
```c```
### • Python
```c```
## < Reference >
https://dart-tutorial.com/introduction-and-basics/questions-for-practice-1/
https://www.tamemo.com/post/172/dart-101-intro/
https://www.geeksforgeeks.org/introduction-to-python/
https://www.geeksforgeeks.org/introduction-to-java/
https://www.geeksforgeeks.org/c-language-introduction/
