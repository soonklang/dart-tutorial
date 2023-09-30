# Practice 2

## 1.จงเขียนโปรแกรมตรวจสอบว่าเป็นเลขคู่หรือเลขคี่ด้วยภาษา Dart

#### โปรแกรมภาษา Dart

```bash
void main() {
	int number = 7; 
	if (number % 2 == 0) {
		print('$number is even');
	} else {
		print('$number is odd');
	}
}
```

#### โปรแกรมภาษา C

```C
#include <stdio.h>
int main() {
	int number = 7; 
	if (number % 2 == 0) {
		printf("%d is even\n", number);
	} else {
		printf("%d is odd\n", number);
	}
	return 0;
}
```

#### โปรแกรมภาษา Java
```Java    
public class OddEvenCheck {
	public static void main(String[] args) {
        	int number = 7; 
        	if (number % 2 == 0) {
           		 System.out.println(number + " is even");
        	} else {
           		 System.out.println(number + " is odd");
	        }
      	}
}
```

#### โปรแกรมภาษา Python

```python
number = 7  
if number % 2 == 0:
	print(f'{number} is even')
else:
	print(f'{number} is odd')
```

## 2.จงเขียนโปรแกรมตรวจสอบว่าเป็นสระหรือพยัญชนะด้วยภาษา Dart
    
#### โปรแกรมภาษา Dart
```bash
void main() {
	String character = 'a'; 
	if ('aeiouAEIOU'.contains(character)) {
		print('$character is a vowel');
	} else {
		print('$character is a consonant');
	}
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
	char character = 'a';
	if (character == 'a' || character == 'e' || character == 'i' || character == 'o' || character == 'u' ||
	character == 'A' || character == 'E' || character == 'I' || character == 'O' || character == 'U') {
		printf("%c is a vowel\n", character);
	} else {
		printf("%c is a consonant\n", character);
	}
	return 0;
}
```  
#### โปรแกรมภาษา Java
```Java
public class VowelConsonantCheck {
	public static void main(String[] args) {
		char character = 'a';
		if ("aeiouAEIOU".contains(Character.toString(character))) {
			System.out.println(character + " is a vowel");
		} else {
			System.out.println(character + " is a consonant");
		}
	}
}
```    
#### โปรแกรมภาษา Python
```python		
character = 'a'  
if character.lower() in 'aeiou':
	print(f'{character} is a vowel')
else:
	print(f'{character} is a consonant')
```
## 3.จงเขียนโปรแกรมตรวจสอบว่าตัวเลขเป็นเลขที่มีค่า +,-,0 ในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
	int number = -5; // Change this value to the number you want to check
	if (number > 0) {
		print('$number is positive');
	} else if (number < 0) {
		print('$number is negative');
	} else {
		print('The number is zero');
	}
}
```
#### โปรแกรมภาษา C
```C	
#include <stdio.h>
int main() {
	int number = -5; 
	if (number > 0) {
		printf("%d is positive\n", number);
	} else if (number < 0) {
		printf("%d is negative\n", number);
	} else {
		printf("The number is zero\n");
	}
	return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class PositiveNegativeZeroCheck {
	public static void main(String[] args) {
		int number = -5; 
		if (number > 0) {
			System.out.println(number + " is positive");
		} else if (number < 0) {
			System.out.println(number + " is negative");
		} else {
			System.out.println("The number is zero");
		}
	}
}
```
#### โปรแกรมภาษา Python
```Python
number = -5  
if number > 0:
	print(f'{number} is positive')
elif number < 0:
	print(f'{number} is negative')
else:
	print('The number is zero')
```
# 4.จงเขียนโปรแกรมที่ปริ้นท์ชื่อตัวเอง 100 ครั้งในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
  for (int i = 0; i < 100; i++) {
    print('Ratchata');
  }
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
    for (int i = 0; i < 100; i++) {
        printf("Ratchata\n");
    }
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class PrintName {
    public static void main(String[] args) {
        for (int i = 0; i < 100; i++) {
            System.out.println("Ratchata");
        }
    }
}
```
#### โปรแกรมภาษา Python
```Python
for i in range(100):
    print('Ratchata')
```
# 5.จงเขียนโปรแกรมเพื่อคำนวนหาผลรวมของจำนวนธรรมชาติในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
  int n = 10; // Change this value to the desired positive integer
  int sum = 0;
  for (int i = 1; i <= n; i++) {
    sum += i;
  }
  print('The sum of natural numbers up to $n is $sum');
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
    int n = 10; // Change this value to the desired positive integer
    int sum = 0;
    for (int i = 1; i <= n; i++) {
        sum += i;
    }
    printf("The sum of natural numbers up to %d is %d\n", n, sum);
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        int n = 10; // Change this value to the desired positive integer
        int sum = 0;
        for (int i = 1; i <= n; i++) {
            sum += i;
        }
        System.out.println("The sum of natural numbers up to " + n + " is " + sum);
    }
}
```
#### โปรแกรมภาษา Python
```Python
n = 10 
sum = 0
for i in range(1, n + 1):
    sum += i
print(f"The sum of natural numbers up to {n} is {sum}")
```
# 6.จงเขียนโปรแกรมเพื่อสร้างตารางสูตรคูณแม่ 5 ในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
  int num = 5;
  for (int i = 1; i <= 12; i++) {
    int result = num * i;
    print('$num x $i = $result');
  }
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
    int num = 5;
    for (int i = 1; i <= 12; i++) {
        int result = num * i;
        printf("%d x %d = %d\n", num, i, result);
    }
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class MultiplicationTable {
    public static void main(String[] args) {
        int num = 5;
        for (int i = 1; i <= 12; i++) {
            int result = num * i;
            System.out.println(num + " x " + i + " = " + result);
        }
    }
}
```
#### โปรแกรมภาษา Python
```Python
num = 5
for i in range(1, 13):
    result = num * i
    print(f'{num} x {i} = {result}')
```
# 7.จงเขียนโปรแกรมเพื่อสร้างตารางสูตรคูณแม่ 1-9 ในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
  for (int num = 1; num <= 9; num++) {
    print("Multiplication Table of $num:");
    for (int i = 1; i <= 12; i++) {
      int result = num * i;
      print('$num x $i = $result');
    }
    print(""); // Blank line between tables
  }
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
    for (int num = 1; num <= 9; num++) {
        printf("Multiplication Table of %d:\n", num);
        for (int i = 1; i <= 12; i++) {
            int result = num * i;
            printf("%d x %d = %d\n", num, i, result);
        }
        printf("\n"); // Blank line between tables
    }
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class MultiplicationTables {
    public static void main(String[] args) {
        for (int num = 1; num <= 9; num++) {
            System.out.println("Multiplication Table of " + num + ":");
            for (int i = 1; i <= 12; i++) {
                int result = num * i;
                System.out.println(num + " x " + i + " = " + result);
            }
            System.out.println(""); // Blank line between tables
        }
    }
}
```
#### โปรแกรมภาษา Python
```Python
for num in range(1, 10):
    print(f"Multiplication Table of {num}:")
    for i in range(1, 13):
        result = num * i
        print(f"{num} x {i} = {result}")
    print("")  # Blank line between tables
```
# 8.จงเขียนโปรแกรมเครื่องคิดเลขอย่างง่ายที่มี +,-,*,/ ในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
import 'dart:io';
void main() {
  print("Simple Calculator");
  print("Enter two numbers:");
  double num1 = double.parse(stdin.readLineSync()!);
  double num2 = double.parse(stdin.readLineSync()!);
  print("Select operation (+, -, *, /):");
  String operator = stdin.readLineSync()!;
  double result;
  switch (operator) {
    case "+":
      result = num1 + num2;
      break;
    case "-":
      result = num1 - num2;
      break;
    case "*":
      result = num1 * num2;
      break;
    case "/":
      result = num1 / num2;
      break;
    default:
      print("Invalid operator");
      return;
  }
  print("Result: $result");
}
```
#### โปรแกรมภาษา C
```C
#include <stdio.h>
int main() {
    printf("Simple Calculator\n");
    printf("Enter two numbers:\n");
    double num1, num2;
    scanf("%lf %lf", &num1, &num2);
    printf("Select operation (+, -, *, /):\n");
    char operator;
    scanf(" %c", &operator);
    double result;
    switch (operator) {
        case '+':
            result = num1 + num2;
            break;
        case '-':
            result = num1 - num2;
            break;
        case '*':
            result = num1 * num2;
            break;
        case '/':
            result = num1 / num2;
            break;
        default:
            printf("Invalid operator\n");
            return 1;
    }
    printf("Result: %lf\n", result);
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
import java.util.Scanner;

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Simple Calculator");
        System.out.println("Enter two numbers:");
        double num1 = scanner.nextDouble();
        double num2 = scanner.nextDouble();
        System.out.println("Select operation (+, -, *, /):");
        char operator = scanner.next().charAt(0);
        double result;
        switch (operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                result = num1 / num2;
                break;
            default:
                System.out.println("Invalid operator");
                return;
        }
        System.out.println("Result: " + result);
    }
}
```
#### โปรแกรมภาษา Python
```Python
print("Simple Calculator")
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))
print("Select operation (+, -, *, /):")
operator = input()
if operator == "+":
    result = num1 + num2
elif operator == "-":
    result = num1 - num2
elif operator == "*":
    result = num1 * num2
elif operator == "/":
    result = num1 / num2
else:
    print("Invalid operator")
    exit(1)
print("Result:", result)
```
# 9.จงเขียนโปรแกรมที่ปริ้นท์เลข 1-100 โดยที่ไม่เอาเลข 41 ในภาษา Dart

#### โปรแกรมภาษา Dart
```bash
void main() {
  for (int i = 1; i <= 100; i++) {
    if (i != 41) {
      print(i);
    }
  }
}
```
```C
#include <stdio.h>
int main() {
    for (int i = 1; i <= 100; i++) {
        if (i != 41) {
            printf("%d\n", i);
        }
    }
    return 0;
}
```
#### โปรแกรมภาษา Java
```Java
public class PrintNumbers {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if (i != 41) {
                System.out.println(i);
            }
        }
    }
}
```
#### โปรแกรมภาษา Python
```Python
for i in range(1, 101):
    if i != 41:
        print(i)
```
---
## Video

[Video](https://www.youtube.com/watch?v=kfxUKefYSP0)

## file powerpoint

[Practice2](https://github.com/630710133Ratchata/Slide_Download/raw/main/Practice%202.pptx)

# อ้างอิง
>https://dart-tutorial.com/conditions-and-loops/

>https://www.geeksforgeeks.org/c-programming-examples/

>https://www.geeksforgeeks.org/java-programming-examples/

>https://www.geeksforgeeks.org/python-programming-examples/


