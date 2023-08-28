# User Input in Dart

## **บทนำ**
การรับข้อมูลจากผู้ใช้ (User Input) ในภาษา Dart สามารถทำได้โดยใช้ฟังก์ชัน .readLineSync() ซึ่งจะใช้ฟังก์ชันนั้นได้ก็ต้อง import ไลบรารีที่ชื่อ dart:io จากไลบรารีของ Dart เพื่อรับข้อมูลจากคอนโซล 

 ```dart
 import 'dart:io';
```

คลาสนี้อนุญาตให้ผู้ใช้อ่านข้อมูลจากการนำเข้ามาตรฐานได้ทั้งแบบ Synchronous และ Asynchronous ฟังก์ชัน .readLineSync() เป็นหนึ่งในวิธีการที่ใช้ในการรับข้อมูลจากผู้ใช้ โดยรูปแบบการใช้งาน .readLineSync() ดังนี้
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

# **Comparing user Input in Dart with Java python and c** #
**User Input in python** <br>
การรับข้อมูลจากผู้ใช้ (User Input) ในภาษา Python สามารถทำได้โดยใช้ฟังก์ชัน input() ซึ่งสามารถรับข้อมูลได้ทั้งตัวอักษรและตัวเลขได้ตามต้องการ
ตัวอย่าง การใช้งาน input()

**1.String User Input (แบบข้อความ)** <br>
```python
name = input("กรุณากรอกชื่อของคุณ: ")
print("สวัสดี, " + name + "~") 
```
<details open>
<summary><b>Input</b></summary>
 <pre>
อิ่มบุญ
</pre>
</details>
<summary><b>output</b></summary>
 <pre>
กรุณากรอกชื่อของคุณ : อิ่มบุญ
สวัสดี, อิ่มบุญ~
</pre>
</details>

**2.Integer User Input (แบบจำนวนเต็ม)** <br>
```python
name = input("กรุณาป้อนชื่อของคุณ : ")
age = int(input("กรุณาป้อนอายุของคุณ : "))

current_year = 2023
birth_year = current_year - age

print(f"สวัสดีคุณ {name} คุณเกิดในปี {birth_year}")
```
<details open>
<summary><b>Input</b></summary>
 <pre>
อิ่มบุญ
22
</pre>
</details>
<summary><b>output</b></summary>
 <pre>
กรุณากรอกชื่อของคุณ : อิ่มบุญ
กรุณาป้อนอายุของคุณ : 22
สวัสดีคุณ อิ่มบุญ คุณเกิดในปี 2001
</pre>
</details>

**3.Floating Point User Input (แบบทศนิยม)** <br>
>ตัวอย่างการคำนวณหาพื้นที่สามเหลี่ยม
```python
base = float(input("ป้อนความยาวฐาน: "))
height = float(input("ป้อนความสูง: "))

area = 0.5 * base * height

print(f"พื้นที่สามเหลี่ยมคือ {area:.2f}")
```

<details open>
<summary><b>Input</b></summary>
 <pre>
อิ่มบุญ
22
</pre>
</details>
<summary><b>output</b></summary>
 <pre>
ป้อนความยาวฐาน: 10
ป้อนความสูง: 5
พื้นที่สามเหลี่ยมคือ 25.00
</pre>
</details>
