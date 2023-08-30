# Practice 2

## 1.จงเขียนโปรแกรมตรวจสอบว่าเป็นเลขคู่หรือเลขคี่ด้วยภาษา Dart

#### โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Dart

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

#### โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา C

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

#### โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Java
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

#### โปรแกรมการเช็คเลขคู่หรือเลขคี่ในภาษา Python

```python
number = 7  
if number % 2 == 0:
	print(f'{number} is even')
else:
	print(f'{number} is odd')
```

## 2.Write a dart program to check whether a character is a vowel or consonant.
    
#### โปรแกรมสำหรับเช็คว่าเป็นสระหรือพยัญชนะในภาษา Dart
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
#### โปรแกรมสำหรับเช็คว่าเป็นสระหรือพยัญชนะในภาษา C
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
#### โปรแกรมสำหรับเช็คว่าเป็นสระหรือพยัญชนะในภาษา Java
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
#### โปรแกรมสำหรับเช็คว่าเป็นสระหรือพยัญชนะในภาษา Python
```python		
character = 'a'  
if character.lower() in 'aeiou':
	print(f'{character} is a vowel')
else:
	print(f'{character} is a consonant')
```
## 3.Write a dart program to check whether a number is positive, negative, or zero.

#### โปรแกรมเช็คว่าเลขนั้นเป็นเลขที่มีค่าเป็น +,-,0 ในภาษา Dart
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
#### โปรแกรมเช็คว่าเลขนั้นเป็นเลขที่มีค่าเป็น +,-,0 ในภาษา C
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
#### โปรแกรมเช็คว่าเลขนั้นเป็นเลขที่มีค่าเป็น +,-,0 ในภาษา Java
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
#### โปรแกรมเช็คว่าเลขนั้นเป็นเลขที่มีค่าเป็น +,-,0 ในภาษา Python
```Python
number = -5  
if number > 0:
	print(f'{number} is positive')
elif number < 0:
	print(f'{number} is negative')
else:
	print('The number is zero')
```
# 4.Write a dart program to print your name 100 times.
```bash
```
```C
```
```Java
```
```Python
```
# 5.Write a dart program to calculate the sum of natural numbers.
```bash
```
```C
```
```Java
```
```Python
```
# 6.Write a dart program to generate multiplication tables of 5.
```bash
```
```C
```
```Java
```
```Python
```
# 7.Write a dart program to generate multiplication tables of 1-9.
```bash
```
```C
```
```Java
```
```Python
```
# 8.Write a dart program to create a simple calculator that performs addition, subtraction, multiplication, and division.
```bash
```
```C
```
```Java
```
```Python
```
# 9.Write a dart program to print 1 to 100 but not 41.
```bash
```
```C
```
```Java
```
```Python
```
