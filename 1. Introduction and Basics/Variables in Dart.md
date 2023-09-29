# Variables in dart
- Variables
 ตัวแปรคือคอนเทนเนอร์ที่ใช้เก็บค่าในโปรแกรม มีตัวแปรหลายประเภทที่คุณสามารถเก็บค่าประเภทต่างๆ ได้ นี่คือตัวอย่างของการสร้างตัวแปรและการเริ่มต้นตัวแปร 
 # Variable Types
 คือชนิดของข้อมูล
 
- String: สำหรับจัดเก็บค่าข้อความ เช่น. “John” [ต้องอยู่ในเครื่องหมายคำพูด]

- int : สำหรับเก็บค่าจำนวนเต็ม เช่น. 10, -10, 8555 [ไม่รวมทศนิยม]

- double: สำหรับจัดเก็บค่าจุดลอยตัว เช่น. 10.0, -10.2, 85.698 [รวมทศนิยม]

- num: สำหรับจัดเก็บหมายเลขประเภทใดๆ เช่น. 10, 20.2, -20 [ทั้ง int และ double]

- bool: สำหรับจัดเก็บข้อมูลจริงหรือเท็จ เช่น. จริง, เท็จ [เก็บเฉพาะค่าจริงหรือเท็จเท่านั้น]

- var: สำหรับจัดเก็บค่าใดๆ เช่น. 'Bimal', 12, 'z' จริง

# Syntax

```dart
type variableName = value;
```

# Exampled

```dart
 void main() {
//Declaring Variables
String name = "John";
String address = "USA";  
num age = 20; // used to store any types of numbers 
num height = 5.9;
bool isMarried = false;
   
// printing variables value   
print("Name is $name");
print("Address is $address");
print("Age is $age");
print("Height is $height");
print("Married Status is $isMarried");
} 
```
# Rules For Creating Variables In Dart
- ชื่อตัวแปรต้องคำนึงถึงขนาดตัวพิมพ์ เช่น a และ A ต่างกัน
- ชื่อตัวแปรอาจประกอบด้วยตัวอักษรและตัวอักษร
- ชื่อตัวแปรไม่สามารถขึ้นต้นด้วยตัวเลขได้
- ไม่อนุญาตให้ใช้คำสำคัญเป็นชื่อตัวแปร
- ไม่อนุญาตให้มีช่องว่างในชื่อตัวแปร
- ไม่อนุญาตให้ใช้อักขระพิเศษ ยกเว้นเครื่องหมายขีดล่าง (_) และเครื่องหมายดอลลาร์ ($)

# Dart Constant
- ค่าคงที่คือประเภทของตัวแปรที่มีค่าไม่เคยเปลี่ยนแปลง ในการเขียนโปรแกรม ค่าที่เปลี่ยนแปลงได้นั้นไม่แน่นอน และค่าที่ไม่เปลี่ยนแปลงนั้นไม่เปลี่ยนรูป บางครั้งคุณไม่จำเป็นต้องเปลี่ยนค่าเมื่อมีการประกาศแล้ว เช่นเดียวกับค่า PI=3.14 มันไม่เคยเปลี่ยนแปลง หากต้องการสร้างค่าคงที่ใน Dart คุณสามารถใช้คีย์เวิร์ด const

```dart
void main(){
const pi = 3.14;
pi = 4.23; // not possible  
print("Value of PI is $pi");
}
```
- output
Constant variables can't be assigned a value
(ไม่สามารถกำหนดค่าตัวแปรคงที่ได้)

# Naming Convention For Variables In Dart
- การปฏิบัติตามแบบแผนการตั้งชื่อถือเป็นนิสัยที่ดี ใน Dart Variables ชื่อตัวแปรควรขึ้นต้นด้วยตัวพิมพ์เล็ก และตัวอักษรแรกของคำทุก ๆ วินาทีจะเป็นตัวพิมพ์ใหญ่ เช่น num1, fullName, isMarried เป็นต้น ในทางเทคนิคแล้ว รูปแบบการตั้งชื่อนี้เรียกว่า lowerCamelCase

```dart
// Not standard way
var fullname = "John Doe";
// Standard way
var fullName = "John Doe";
const pi = 3.14;

```

# เปรียบเทียบภาษา Dart กับภาษา C ,Java, Python
# Type Inference
- (การอินเฟอเรนซ์ชนิดข้อมูล) Dart มีการอินเฟอเรนซ์ชนิดข้อมูล ซึ่งหมายความว่าคุณไม่จำเป็นต้องระบุชนิดข้อมูลของตัวแปรเมื่อประกาศตัวแปร ระบบจะพยายามตรวจสอบและกำหนดชนิดข้อมูลให้อัตโนมัติตามค่าที่คุณกำหนดให้
## ตัวอย่าง Type Inference ในภาษา dart

```dart
void main() {
  var number = 42;  // Dart จะอินเฟอเรนซ์ชนิดข้อมูลเป็น int ตามค่า 42
  var text = 'Hello';  // Dart จะอินเฟอเรนซ์ชนิดข้อมูลเป็น String ตามค่า 'Hello'
  var isTrue = true;  // Dart จะอินเฟอเรนซ์ชนิดข้อมูลเป็น bool ตามค่า true

  print(number.runtimeType);  // แสดงชนิดข้อมูลของตัวแปร number
  print(text.runtimeType);  // แสดงชนิดข้อมูลของตัวแปร text
  print(isTrue.runtimeType);  // แสดงชนิดข้อมูลของตัวแปร isTrue
}

```
## ภาษา C
- ต้องระบุชนิดข้อมูล
```
#include <stdio.h>

int main() {
    int number = 42;  // ประกาศตัวแปรชนิด int และกำหนดค่าเป็น 42
    float pi = 3.14159;  // ประกาศตัวแปรชนิด float และกำหนดค่าเป็น 3.14159
    char letter = 'A';  // ประกาศตัวแปรชนิด char และกำหนดค่าเป็น 'A'

    printf("Number: %d\n", number);
    printf("Pi: %f\n", pi);
    printf("Letter: %c\n", letter);

    return 0;
}

```
## ภาษา Java
- ต้องระบุชนิดข้อมูล
```
public class Main {
    public static void main(String[] args) {
        int number = 42;  // ประกาศตัวแปรชนิด int และกำหนดค่าเป็น 42
        double pi = 3.14159;  // ประกาศตัวแปรชนิด double และกำหนดค่าเป็น 3.14159
        char letter = 'A';  // ประกาศตัวแปรชนิด char และกำหนดค่าเป็น 'A'

        System.out.println("Number: " + number);
        System.out.println("Pi: " + pi);
        System.out.println("Letter: " + letter);
    }
}

```
## ภาษา Python
- ระบบจะพยายามตรวจสอบและกำหนดชนิดข้อมูลให้อัตโนมัติตามค่าที่คุณกำหนดให้
```

number = 42  # ไม่ต้องระบุชนิดข้อมูล จะถูกตั้งเป็น int โดยอัตโนมัติ
pi = 3.14159  # ไม่ต้องระบุชนิดข้อมูล จะถูกตั้งเป็น float โดยอัตโนมัติ
text = 'Hello'  # ไม่ต้องระบุชนิดข้อมูล จะถูกตั้งเป็น str โดยอัตโนมัติ

print(type(number))  # แสดงชนิดข้อมูลของตัวแปร number
print(type(pi))  # แสดงชนิดข้อมูลของตัวแปร pi
print(type(text))  # แสดงชนิดข้อมูลของตัวแปร text

```


# Nullable Types 
- (ชนิดข้อมูลที่เป็น Nullable) Dart มีคุณลักษณะที่ชื่อว่า "null safety" ซึ่งทำให้คุณต้องระบุว่าตัวแปรนั้นสามารถเป็นค่า null ได้หรือไม่ได้
 
## ตัวอย่าง Nullable Type ในภาษา Dart
Nullable Type Annotation (Type?): คุณสามารถใส่เครื่องหมายคำถาม (?) หลังจากชนิดข้อมูลเพื่อระบุว่าตัวแปรสามารถเป็นค่า null ได้หรือไม่ได้


```dart
int? nullableNumber = null;  // ตัวแปร nullableNumber สามารถเป็นค่า null ได้

```


- หากไม่ระบุเครื่องหมายคำถาม, ค่าของตัวแปรจะต้องไม่เป็น null


```dart
String nonNullableText = 'Hello';  // ตัวแปร nonNullableText ต้องไม่เป็นค่า null

```

```dart
void main() {
  int? nullableNumber = null; // ตัวแปร nullableNumber สามารถเป็นค่า null ได้
  String nonNullableText = 'Hello'; // ตัวแปร nonNullableText ต้องไม่เป็นค่า null

  print(nullableNumber); // แสดงค่า nullableNumber (null)
  print(nonNullableText); // แสดงค่า nonNullableText ('Hello')

  // ตรวจสอบว่าตัวแปร nullableNumber เป็น null หรือไม่
  if (nullableNumber == null) {
    print('nullableNumber is null');
  } else {
    print('nullableNumber is not null');
  }
}
```


## ภาษา C
- ภาษา C ไม่มีระบบ nullable types อย่างที่มีในภาษาอื่น ๆ ที่เป็นแบบจังหวะ (dynamically typed) ซึ่งเป็นคุณลักษณะที่ช่วยจัดการกับค่า null ในการประกาศและใช้งานตัวแปรในภาษา C ตัวแปรที่ไม่ได้กำหนดค่าเริ่มต้นจะมีค่าไม่ถูกกำหนด (uninitialized) และอาจจะเกิดค่าที่ไม่คาดคิดเมื่อใช้งาน

```
#include <stdio.h>

int main() {
    int number = 42;  // ประกาศตัวแปรชนิด int
    char letter = 'A';  // ประกาศตัวแปรชนิด char

    printf("Number: %d\n", number);
    printf("Letter: %c\n", letter);

    return 0;
}
```
## ภาษา Java
- ภาษา Java ไม่มีระบบ nullable types ที่เเป็นแบบจังหวะ (dynamically typed) ที่รองรับความยืดหยุ่นในการจัดการกับค่า null โดยใช้ nullable types แต่ในภาษา Java เป็นภาษาที่เป็นแบบชนิด (statically typed) และไม่มีระบบที่จัดการ nullable values อย่างใกล้ชิด
 
```
public class Main {
    public static void main(String[] args) {
        String nullableText = null;  // ประกาศตัวแปร nullableText และกำหนดค่าเป็น null
        String nonNullableText = "Hello";  // ประกาศตัวแปร nonNullableText และกำหนดค่า

        System.out.println("Nullable Text: " + nullableText);  // แสดงค่า nullableText (null)
        System.out.println("Non-Nullable Text: " + nonNullableText);  // แสดงค่า nonNullableText ("Hello")
    }
}
```
## ภาษา Python
- ภาษา Python เป็นภาษาที่เป็นแบบจังหวะ (dynamically typed) และไม่ต้องระบุชนิดข้อมูลของตัวแปร ซึ่งทำให้ทุกตัวแปรสามารถเป็นค่า None ได้ เทียบเท่ากับค่า null ในภาษาอื่น ๆ เพื่อแสดงความไม่มีข้อมูลหรือค่าว่าง

```
nullable_value = None  # ประกาศตัวแปรที่สามารถมีค่า None
non_nullable_value = "Hello"  # ประกาศตัวแปรที่ไม่สามารถเป็น None

print("Nullable Value:", nullable_value)  # แสดงค่า nullable_value (None)
print("Non-Nullable Value:", non_nullable_value)  # แสดงค่า non_nullable_value ("Hello")

# ตรวจสอบว่าตัวแปร nullable_value เป็น None หรือไม่
if nullable_value is None:
    print("Nullable Value is None")
else:
    print("Nullable Value is not None")
```
# Reference

https://dart-tutorial.com/introduction-and-basics/

https://expert-programming-tutor.com/tutorial/article/L01_DART_INTRO.php

https://www.tamemo.com/post/172/dart-101-intro/

https://www.geeksforgeeks.org/introduction-to-python/

https://chat.openai.com/

# file การนำเสนอ


[Variables in dart.pptx](https://github.com/soonklang/dart-tutorial/files/12765103/Variables.in.dart.pptx)


# วีดีโอการนำเสนอ

https://youtu.be/8jklk8WcByQ?si=0hw3paTl4JrBZZW4
