# User Input in Dart

## **บทนำ**
ในภาษาโปรแกรม Dart นั้นจะสามารถรับข้อมูลสำหรับการนำเข้ามาจากผู้ใช้ผ่านคอนโซลได้โดยใช้ฟังก์ชัน .readLineSync() ซึ่งจะใช้ฟังก์ชันนั้นได้ก็ต้องimportไลบรารีที่ชื่อ dart:io จากไลบรารีของ Dart เพื่อรับข้อมูลจากคอนโซล

 ```dart
 import 'dart:io';
```

คลาสนี้อนุญาตให้ผู้ใช้อ่านข้อมูลจากการนำเข้ามาตรฐานได้ทั้งแบบ Synchronous และ Asynchronous ฟังก์ชัน .readLineSync() เป็นหนึ่งในวิธีการที่ใช้ในการรับข้อมูลจากผู้ใช้ ซึ่งมีหลายรูปแบบ
 * String User Input (แบบข้อความ)
 * Integer User Input (แบบจำนวนเต็ม)
 * Floating Point User Input (แบบทศนิยม)

## **ตัวอย่างของการรับข้อมูลทั้ง 3 รูปแบบ** ##
**1.String User Input (แบบข้อความ)** <br>
>ใช้เพื่อเก็บข้อมูลข้อความที่ผู้ใช้ป้อนเข้ามา เช่น ชื่อ, ที่อยู่, คำอธิบาย,etc...
 ```dart
import 'dart:io';
 
void main()
{
    print("Enter your name?");
    String? name = stdin.readLineSync(); 
 
    // Printing the name
    print("Hello, $name! \nWelcome to GeeksforGeeks!!");
}
```
<details open>
<summary><b>Input</b></summary>
 <pre>
Geek
</pre>
</details>
<details open>
<summary><b>output</b></summary>
 <pre>
Enter your name?
Hello, Geek! 
Welcome to GeeksforGeeks!!
</pre>
</details>
