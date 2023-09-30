# Practice 3
### 1. Write a program in Dart to print your own name using function.
Dart
```dart
void Name(String name) {
  print("My name is $name.");
}

void main() {
  String myName = "Weerapong";
  Name(myName);
}
````
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>My name is Weerapong</code>
</pre>
</details>

C
```bash
#include <stdio.h>

void printName(char *name) {
    printf("My name is %s.\n", name);
}

int main() {
    char myName[] = "Weerapong";
    printName(myName);
}
```
Java
```bash
public class Main {
    static void printName(String name) {
        System.out.println("My name is " + name + ".");
    }

    public static void main(String[] args) {
        String myName = "Weerapong";
        printName(myName);
    }
}
```
Python
```bash
def print_name(name):
    print(f"My name is {name}.")

my_name = "Weerapong"
print_name(my_name)
```
### 2. Write a program in Dart to print even numbers between intervals using function
Dart
```bash
import 'dart:io';
void EvenNumbers(int start, int end) {
  for (int i = start; i <= end; i++) {
    if (i % 2 == 0) {
      print(i);
    }
  }
}

void main() {
  print("Enter start number ");
  int intervalStart = int.parse(stdin.readLineSync()!); 
  print("Enter last number ");
  int intervalEnd = int.parse(stdin.readLineSync()!);    
  
  print("Even numbers between $intervalStart and $intervalEnd:");
  EvenNumbers(intervalStart, intervalEnd);
}
```
Input: 10, 20
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>10
12
14
16
18
20</code>
</pre>
</details>


C
```bash
#include <stdio.h>

void evenNumbers(int start, int end) {
    for (int i = start; i <= end; i++) {
        if (i % 2 == 0) {
            printf("%d\n", i);
        }
    }
}

int main() {
    int intervalStart, intervalEnd;
    printf("Enter start number: ");
    scanf("%d", &intervalStart);
    printf("Enter last number: ");
    scanf("%d", &intervalEnd);
    
    printf("Even numbers between %d and %d:\n", intervalStart, intervalEnd);
    evenNumbers(intervalStart, intervalEnd);
    
}
```
Java
```bash
import java.util.Scanner;

public class Main {
    static void evenNumbers(int start, int end) {
        for (int i = start; i <= end; i++) {
            if (i % 2 == 0) {
                System.out.println(i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter start number: ");
        int intervalStart = scanner.nextInt();
        System.out.print("Enter last number: ");
        int intervalEnd = scanner.nextInt();
        
        System.out.println("Even numbers between " + intervalStart + " and " + intervalEnd + ":");
        evenNumbers(intervalStart, intervalEnd);
    }
}
```
Python
```bash
def even_numbers(start, end):
    for i in range(start, end + 1):
        if i % 2 == 0:
            print(i)

interval_start = int(input("Enter start number: "))
interval_end = int(input("Enter last number: "))
    
print(f"Even numbers between {interval_start} and {interval_end}:")
even_numbers(interval_start, interval_end)
```
### 3. Write a program in Dart that generates random password.
Dart
```bash
import 'dart:math';
import 'dart:io';

String Generate_password(int length) {
  Random random = Random();
  String vChars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#\$%^&*()-_';
  String password = '';
  for(int i = 0; i<length; i++){
    int randomChar = random.nextInt(vChars.length);
    password += vChars[randomChar];
  }
  
return password;
}

void main() {
  print("Enter password length");
  int length = int.parse(stdin.readLineSync()!);
  String password= Generate_password(length);
  print(password);
}
```
Input:8
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>ZlmyW1tP</code>
</pre>
</details>


C
```bash
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <string.h>

char* generate_password(int length) {
    srand(time(NULL));
    char vChars[] = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#\$%^&*()-_";
    char* password = (char*)malloc((length + 1) * sizeof(char));
    for (int i = 0; i < length; i++) {
        int randomChar = rand() % strlen(vChars);
        password[i] = vChars[randomChar];
    }
    password[length] = '\0';
    return password;
}

int main() {
    int passwordLength;
    printf("Enter password length: ");
    scanf("%d", &passwordLength);

    char* generatedPassword = generate_password(passwordLength);
    printf("Generated password: %s\n", generatedPassword);
}
```
Java
```bash
import java.util.Random;
import java.util.Scanner;

public class Main {
    static String generatePassword(int length) {
        Random random = new Random();
        String vChars = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#\\$%^&*()-_";
        StringBuilder password = new StringBuilder();
        for (int i = 0; i < length; i++) {
            int randomChar = random.nextInt(vChars.length());
            password.append(vChars.charAt(randomChar));
        }
        return password.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter password length: ");
        int passwordLength = scanner.nextInt();
        scanner.close();

        String generatedPassword = generatePassword(passwordLength);
        System.out.println("Generated password: " + generatedPassword);
    }
}
```
Python
```bash
import random
import string

def generate_password(length):
    vChars = string.ascii_letters + string.digits + "!@#$%^&*()-_"
    password = ''.join(random.choice(vChars) for _ in range(length))
    return password

password_length = int(input("Enter password length: "))
generated_password = generate_password(password_length)
print("Generated password:", generated_password)
```
### 4. Write a program in Dart that find the area of a circle using function.
Dart
```bash
import 'dart:io';

void Circle(double radius) {
  var cir = 22/7*radius*radius;
  print("The area of the circle is $cir");
}

void main() {
  print("Enter radius number");
  double radius = double.parse(stdin.readLineSync()!);
  Circle(radius);
  }
````
Input:5
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>The area of the circle is 78.57142857142857</code>
</pre>
</details>


C
```bash
#include <stdio.h>

void circle(double radius) {
    double cir = 3.14 * radius * radius;
    printf("The area of the circle is %lf\n", cir);
}

int main() {
    printf("Enter radius number: ");
    double radius;
    scanf("%lf", &radius);

    circle(radius);
}
```
Java
```bash
import java.util.Scanner;

public class Main {
    static void circle(double radius) {
        double cir = 3.14 * radius * radius;
        System.out.println("The area of the circle is " + cir);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter radius number: ");
        double radius = scanner.nextDouble();

        circle(radius);
    }
}
```
Python
```bash
def circle(radius):
    cir = 3.14 * radius * radius
    print("The area of the circle is", cir)

radius = float(input("Enter radius number: "))
circle(radius)
```
### 5. Write a program in a dart that implements the Pythagorean theorem using function.
Dart
```bash
import 'dart:math';
import 'dart:io';
//Hypotenuse,Opposite,Adjacent
double Hypotenuse(double opp,double adj )=>sqrt(opp * opp + adj * adj) ;

void main() {
  print("Enter opposite length");
  double opp = double.parse(stdin.readLineSync()!);
  print("Enter adjacent length");
  double adj = double.parse(stdin.readLineSync()!);
  double hypotenuse = Hypotenuse(opp,adj);
  print("hypotenuse length = $hypotenuse");
}
````
Input: 4, 5
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>hypotenuse length = 6.4031242374328485</code>
</pre>
</details>


C
```bash
#include <stdio.h>
#include <math.h>

double hypotenuse(double opp, double adj) {
    return sqrt(opp * opp + adj * adj);
}

int main() {
    printf("Enter opposite length: ");
    double opp;
    scanf("%lf", &opp);

    printf("Enter adjacent length: ");
    double adj;
    scanf("%lf", &adj);

    double hyp = hypotenuse(opp, adj);
    printf("Hypotenuse length = %lf\n", hyp);
}
```
Java
```bash
import java.util.Scanner;
import java.lang.Math;

public class Main {
    static double hypotenuse(double opp, double adj) {
        return Math.sqrt(opp * opp + adj * adj);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter opposite length: ");
        double opp = scanner.nextDouble();

        System.out.print("Enter adjacent length: ");
        double adj = scanner.nextDouble();

        double hyp = hypotenuse(opp, adj);
        System.out.println("Hypotenuse length = " + hyp);
    }
}
```
Python
```bash
import math

def hypotenuse(opp, adj):
    return math.sqrt(opp * opp + adj * adj)

opp = float(input("Enter opposite length: "))
adj = float(input("Enter adjacent length: "))
    
hyp = hypotenuse(opp, adj)
print("Hypotenuse length =", hyp)
```
### 6. Write a program in Dart to reverse a String using function.
Dart
```bash
import 'dart:io';
String reverseString(String original) {
  String reversed = '';
  for (int i = original.length - 1; i >= 0; i--) {
    reversed += original[i];
  }
  return reversed;
}

void main() {
  String original = (stdin.readLineSync()!);
  String reversed = reverseString(original);
  
  print("Original string: $original");
  print("Reversed string: $reversed");
}
````
Input: today
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Original string: today
Reversed string: yadot</code>
</pre>
</details>


C
```bash
#include <stdio.h>
#include <string.h>

char* reverse_string(char* original) {
    int length = strlen(original);
    char* reversed = (char*)malloc((length + 1) * sizeof(char));
    
    for (int i = 0; i < length; i++) {
        reversed[i] = original[length - i - 1];
    }
    reversed[length] = '\0';
    return reversed;
}

int main() {
    char original[100];
    printf("Enter a string: ");
    fgets(original, sizeof(original), stdin);
    original[strcspn(original, "\n")] = 0;

    char* reversed = reverse_string(original);
    printf("Original string: %s\n", original);
    printf("Reversed string: %s\n", reversed);

}
```
Java
```bash
import java.util.Scanner;

public class Main {
    static String reverseString(String original) {
        StringBuilder reversed = new StringBuilder();
        for (int i = original.length() - 1; i >= 0; i--) {
            reversed.append(original.charAt(i));
        }
        return reversed.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String original = scanner.nextLine();
        scanner.close();

        String reversed = reverseString(original);
        System.out.println("Original string: " + original);
        System.out.println("Reversed string: " + reversed);
    }
}
```
Python
```bash
def reverse_string(original):
    return original[::-1]

original = input("Enter a string: ")
reversed_str = reverse_string(original)
    
print("Original string:", original)
print("Reversed string:", reversed_str)
```
### 7. Write a program in Dart to calculate power of a certain number. For e.g 5^3=125
Dart
```bash
import 'dart:math';
//pow return type is "num"
double powernum(double number, int power) =>pow(number,power).toDouble();

void main() {
  double number = 5.0;
  int power = 3;
  double result = powernum(number, power);
  
  print("$number ^ $power = $result");
}
````
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>5.0 ^ 3 = 125.0</code>
</pre>
</details>


C
```bash
#include <stdio.h>
#include <math.h>

double power_num(double number, int power) {
    return pow(number, power);
}

int main() {
    double number = 5.0;
    int power = 3;
    double result = power_num(number, power);

    printf("%.1lf ^ %d = %.1lf\n", number, power, result);
}

```
Java
```bash
import java.lang.Math;

public class Main {
    static double powerNum(double number, int power) {
        return Math.pow(number, power);
    }

    public static void main(String[] args) {
        double number = 5.0;
        int power = 3;
        double result = powerNum(number, power);
        
        System.out.printf("%.1f ^ %d = %.1f%n", number, power, result);
    }
}
```
Python
```bash
def power_num(number, power):
    return number ** power

number = 5.0
power = 3
result = power_num(number, power)
    
print(f"{number} ^ {power} = {result}")
```
### *< Reference >*
https://dart-tutorial.com/dart-functions/math-in-dart/

https://dart-tutorial.com/dart-functions/arrow-function-in-dart/

https://dart-tutorial.com/dart-functions/functions-in-dart/

https://docs.oracle.com/javase/8/docs/api/java/util/Random.html

https://docs.python.org/3/library/random.html

https://www.khanacademy.org/math/cc-eighth-grade-math/cc-8th-geometry/cc-8th-pythagorean-theorem/v/the-pythagorean-theorem

https://www.khanacademy.org/math/cc-seventh-grade-math/cc-7th-geometry/cc-7th-area-circumference/v/area-of-a-circle

### *< video presentation>*
https://youtu.be/wVn2PZxak2k
### *< presentation file>*
[630710336 Presentation Practice 3.pptx](https://github.com/soonklang/dart-tutorial/files/12775084/630710336.Presentation.Practice.3.pptx)
