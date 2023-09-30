# STRING IN DART 
String (สตริง) หมายถึงลำดับอักขระหรือลำดับของรหัสตัวอักษร unit code หน้าที่หลักของสตริงสามารถจัดเก็บข้อมูลในรูปแบบข้อความ นอกจากอักขระแล้วยังมีตัวเลขและตัวอักษรพิเศษที่นับรวมว่าเป็นสตริงด้วยเช่นกัน
 
### รูปแบบการเขียนสตริง
   -	การเขียนสตริงในภาษา Dart จะเขียนโดยใช้เครื่องหมาย single quotes ( '' ) , double quotes ( "" ) และเครื่องหมาย Triple quotes ( """ ) จะถูกใช้ในกรณีที่มีสตริงหลายบรรทัด

>ตัวอย่างของการแสดงค่าสตริงในภาษา Dart :
```dart
void main() {   
   	String str1 = 'Single quotes';   
   	String str2 = "Double quotes";   
   	String str3 = """A
multiline
string""";   
   	print(str1);  
   	print(str2);   
   	print(str3);   
}
```
>Output :

  ```
Single quotes
Double quotes
A
multiline
string
```
>ตัวอย่างของการแสดงค่าสตริงในภาษา C :
```c
#include <stdio.h>

int main() {
  	char str[] = "C is Fun!";
  	printf("%s", str);
}
```
>Output :
```
C is Fun!
```

>ตัวอย่างของการแสดงค่าสตริงในภาษา Java :
```javascript
public class Main {
  public static void main(String[] args) {
    String str = "Java is Fun!";
    System.out.println(str);
  }
}
```
>Output :
```
Java is Fun!
```
>ตัวอย่างของการแสดงค่าสตริงในภาษา Python :
```python
str = "Python is Fun!"
print(str)
```
>Output :
```
Python is Fun!
```
------
## String Concatenation (การต่อข้อความ)

•	String Concatenation หมายถึงการนำสตริงตัวที่หนึ่งรวมเข้ากับสตริงตัวอื่น
-	ในภาษา Dart สามารถใช้เครื่องหมาย ( + ) เพื่อรวมสตริงเข้าด้วยกัน
-	อีกทั้งยังสามารถใส่ค่านิพจน์ภายในสตริงได้ โดยใช้ “${}” หากนิพจน์เป็นตัวแปรสามารถใช้ “$” เพียงตัวเดียว

>ตัวอย่างการต่อสตริงในภาษา Dart
```dart
void main() {

	String firstName = "John";
	String lastName = "๋Jae"; 

	print("Using +, Full Name is "+firstName + " " + lastName+".");  //การรวมสตริงโดยใช้เครื่องหมาย ( + )
	print("Using interpolation, full name is $firstName $lastName.");  //การรวมสตริงโดยใช้ “$”
	print("How old is he?, $firstName is ${25} years old ");  //การรวมสตริงโดยสามารถใส่ค่านิพจน์ใน “${}” ได้
}
```
>Output :

```
Using +, Full Name is John Jae.
Using interpolation, full name is John Jae.
How old is he?, John is 25 years old 
```
-	หากพิมพ์ข้อความติดกัน สตริงก็สามาถต่อรวมกันโดยอัตโนมัติ ดังตัวอย่างด้านล่าง
```dart
void main() {

	String str = 'John ' 'Jae';
	print(str);
} 
```
>ตัวอย่างการต่อสตริงในภาษา C
-	ภาษา C สามารถต่อสตริงได้หลากหลายแบบ จึงขอยกตัวอย่างการใช้ฟังก์ชัน strcat() เพื่อนำมาเปรียบเทียบในภาษา Dart

```
#include <stdio.h>
#include <string.h>

int main()
{

	char firstName[] = "John ";
	char lastName[] = "Jae";

	strcat(firstName, lastName);	//เรียกใช้ฟังก์ชัน strcat()
	printf("Full Name is: %s ", firstName);
}

```

>ตัวอย่างการต่อสตริงในภาษา Java

-	ภาษา Java นั้นเราจะนำเมธอด concat() มาใช้ต่อท้ายสตริงหรือข้อความที่เราต้องการ
```
public class Main {
  public static void main(String[] args) {
    String firstName = "John ";
    String lastName = "Jae";
    System.out.println(firstName.concat(lastName));
  }
}
```

>ตัวอย่างการต่อสตริงในภาษา Python
```
firstName = "John "
lastName = "Jae"
name = firstName + lastName
print(name)
```
------

### Properties Of String (คุณสมบัติของสตริง)
•	codeUnits: คืนค่ารหัสตัวอักษรใน unit code หรือค่า Decimal ในตารางแอสกี(ASCII)

•	isEmpty: คืนค่าเป็น true เมื่อสตริงเป็นค่าว่าง

•	isNotEmpty: คืนค่าเป็น false เมื่อสตริงเป็นค่าว่าง

•	length: คืนค่าความยาวของสตริง โดยนับช่องว่าง แท็บ และสตริงบรรทัดใหม่

>ตัวอย่างการแสดงคุณสมบัติของสตริงในภาษา Dart
```dart
void main() {

   	String str = "Hi";

   	print(str.codeUnits);   
   	print(str.isEmpty);     
   	print(str.isNotEmpty);  
	print("The length of the string is: ${str.length}");

}

```
>Output :

```
[72, 105]
false
true
The length of the string is: 2
```
------

### Methods Of String
•	toLowerCase(): แปลงอักขระทั้งหมดในสตริงนี้ให้เป็นตัวพิมพ์เล็ก

•	toUpperCase(): แปลงอักขระทั้งหมดในสตริงนี้เป็นตัวพิมพ์ใหญ่


การแปลงสตริงเป็นตัวพิมพ์ใหญ่และตัวพิมพ์เล็ก

-	สามารถแปลงข้อความในสตริงโดยใช้ .to 
-	การแปลงอักขระเป็นตัวพิมพ์เล็กนั้นจะใช้ .toLowerCase()


>ตัวอย่างการแปลงอักขระเป็นตัวพิมพ์ใหญ่และตัวพิมพ์เล็กในภาษา Dart
```dart
void main() { 
   String address1 = "Florida";
   String address2 = "TexAs";

   print("Address 1 in uppercase: ${address1.toUpperCase()}"); 
   print("Address 1 in lowercase: ${address1.toLowerCase()}"); 
   print("Address 2 in uppercase: ${address2.toUpperCase()}"); 
   print("Address 2 in lowercase: ${address2.toLowerCase()}"); 
}
```
>Output :

```
Address 1 in uppercase: FLORIDA
Address 1 in lowercase: florida
Address 2 in uppercase: TEXAS
Address 2 in lowercase: texas
```

>ตัวอย่างการแปลงอักขระเป็นตัวพิมพ์ใหญ่และตัวพิมพ์เล็กในภาษา C

```c
#include <stdio.h>
#include <ctype.h>	//เรียกใช้ฟังก์ชัน ctype.h ในไลบรารี
#include <string.h>

void convertToUpper(char *str) {	//สร้างฟังก์ชันชื่อ ConvertToUpper เพื่อวนลูปตามอักขระในสตริง
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = toupper(str[i]);	//ใช้ฟังก์ชัน topper เพื่อแปลงอักขระเป็นตัวพิมพ์ใหญ่
    }
}

void convertToLower(char *str) {	//สร้างฟังก์ชันชื่อ ConvertToLower เพื่อวนลูปตามอักขระในสตริง
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = tolower(str[i]);	//ใช้ฟังก์ชัน tolower เพื่อแปลงอักขระเป็นตัวพิมพ์เล็ก
    }
}

int main() {
    char address[] = "Florida TexAs";
    char chr;


    char upperCase[strlen(address) + 1];
    char lowerCase[strlen(address) + 1];

    strcpy(upperCase, address); 
    strcpy(lowerCase, address);

    convertToUpper(upperCase);
    convertToLower(lowerCase);

    printf("Uppercase string: %s\n", upperCase);
    printf("Lowercase string: %s\n", lowerCase);

    return 0;
}
```
>Output :

```
Uppercase string: FLORIDA TEXAS
Lowercase string: florida texas
```

>ตัวอย่างการแปลงอักขระเป็นตัวพิมพ์ใหญ่และตัวพิมพ์เล็กในภาษา Java

```javascript
public class Main {
  public static void main(String[] args) {
    String address = "Florida TexAs";
    System.out.println(address.toUpperCase());
    System.out.println(address.toLowerCase());
  }
}
```
>Output :

```
FLORIDA TEXAS
florida texas
```

>ตัวอย่างการแปลงอักขระเป็นตัวพิมพ์ใหญ่และตัวพิมพ์เล็กในภาษา Python

```python
address = "Florida TexAs"

print(address.upper())
print(address.lower())
```

>Output :

```
FLORIDA TEXAS
florida texas
```

------

## Reference
➔	https://dart-tutorial.com/introduction-and-basics/string-in-dart/

➔	https://api.flutter.dev/flutter/dart-core/String-class.html

➔	https://www.geeksforgeeks.org/strings-in-dart/

➔	https://www.w3schools.com/python/python_strings.asp

➔	https://www.w3schools.com/java/java_strings_concat.asp

➔	https://www.w3schools.com/c/c_strings.php

## Slides & Clip
➔	[Slides](https://github.com/soonklang/dart-tutorial/files/12775171/620710306.-.Sting.In.Dart.Start-ToUpperCase.LowerCase.pdf)

➔	[Clip](https://www.youtube.com/watch?v=7yOTvk1ISeU)
