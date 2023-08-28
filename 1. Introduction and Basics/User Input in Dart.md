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
>ใช้เพื่อเก็บข้อมูลข้อความที่ผู้ใช้ป้อนเข้ามา เช่น ชื่อ, ที่อยู่, คำอธิบาย,etc.
 ```dart
import 'dart:io';
 
void main()
{
    print("Enter your name?");
    String? name = stdin.readLineSync(); 
 
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

**2.Integer User Input (แบบจำนวนเต็ม)** <br>
>สามารถรับข้อมูลจำนวนเต็มเพื่อรับค่าตัวเลขจากผู้ใช้โดยที่ไม่มีจุดทศนิยม เช่น 10, 100, -800 ,etc.
 ```dart
import 'dart:io';
 
void main()
{
    print("Enter your favourite number:");
 
   // Scanning number
    int? n = int.parse(stdin.readLineSync()!);
   // Here ? and ! are for null safety
 
    print("Your favourite number is $n");
}
```

<details open>
<summary><b>Input</b></summary>
 <pre>
300
</pre>
</details>
<summary><b>output</b></summary>
 <pre>
Enter your favourite number:
Your favourite number is 300
</pre>
</details>

**3.Floating Point User Input (แบบทศนิยม)** <br>
>คุณสามารถใช้ข้อมูลแบบ float หากคุณต้องการรับค่าตัวเลขจากผู้ใช้ที่มีจุดทศนิยม เช่น 10.5, 100.5, -800.9, etc.

```dart

import 'dart:io';

void main() {
  print("Enter a floating number:");
  double n = double.parse(stdin.readLineSync()!);
  print("The entered num is $n");
}
```
<details open>
<summary><b>Input</b></summary>
 <pre>
15.2
</pre>
</details>
<summary><b>output</b></summary>
 <pre>
Enter a floating number:
The entered num is 15.2
</pre>
</details>
