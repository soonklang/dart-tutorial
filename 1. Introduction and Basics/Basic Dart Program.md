# Basic Dart Program
นี่เป็นโปรแกรม dart ที่พิมพ์ hello world บนหน้าจอโปรแกรมเมอร์ส่วนใหญ่เขียนโปรแกรมhello world เป็นโปรแกรมแรกของพวกเขา

 ```dart
 void main() { 
   print("Hello World!"); 
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Hello World!
</pre>
</details>

อธิบายโปรแกรม dart พื้นฐาน
 * void main ( )เป็นจุดเริ่มต้นที่โปรแกรมจะเริ่มทํางาน
 * แต่ละโปรแกรมเริ่มต้นด้วยฟังก์ชันหลัก
 * วงเล็บ{ }ระบุจุดเริ่มต้นและจุดสิ้นสุดของบล็อกโค้ด
 * print ("hello world ! "); พิมพ์ hello world ! บนจอ.
 * แต่ละคําสั่งรหัสต้องสิ้นสุดด้วยเครื่องหมายอัลกอริทึม

## **โปรแกรม dart พื้นฐานสําหรับพิมพ์ชื่อ** ##
```dart
 void main()
{
    var name = "Wikorn";
    print(name);
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## **โปรแกรมdartพื้นฐานที่เชื่อมต่อตัวแปรอย่างน้อยหนึ่งตัว** ##
ที่นี่ $variableName ใช้สําหรับการเชื่อมต่อตัวแปร. กระบวนการเชื่อมต่อนี้ในdartเรียกว่าการแก้ไขสตริง
```dart
 void main(){
  var firstName = "Wikorn";
  var lastName = "Sangsuk";
  print("Full name is $firstName $lastName");
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## **โปรแกรม dart สําหรับการคํานวณพื้นฐาน** ##
ดําเนินการบวกการลบการคูณและการหารในdart
```dart
void main() {
int num1 = 20; //declaring number1
int num2 = 10; //declaring number2
  
// Calculation
int sum = num1 + num2;
int diff = num1 - num2;
int mul = num1 * num2;
double div = num1 / num2; // It is double because it outputs number with decimal.
  
// displaying the output
print("The sum is $sum");
print("The diff is $diff");
print("The mul is $mul");
print("The div is $div");
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

## **สร้างโครงการ dart สมบูรณ์** ##
การจัดการไฟล์เดียวเป็นสิ่งที่ดีแต่ถ้าโครงการของคุณมีขนาดใหญ่ขึ้นคุณต้องจัดการการกําหนดค่าแพคเกจและไฟล์สินทรัพย์ ดังนั้นการสร้างโครงการdartจะช่วยให้คุณสามารถจัดการทั้งหมดนี้ได้
```dart
 dart create <project_name>
```
ซึ่งจะสร้างโครงการdartที่เรียบง่ายด้วยโค้ดสําเร็จรูปบางอย่าง

## **ขั้นตอนในการสร้างโครงการdart** ##
 * เปิดตําแหน่งโฟลเดอร์ที่พร้อมคําสั่ ง / เทอร์ มินัล
 * พิมพ์dart create project_name ( ตัวอย่างเช่น dart create first_app )
 * พิมพ์ cd first _ app
 * รหัสประเภท เปิดโครงการโดยใช้โค้ดสตูดิโอภาพ
 * หากต้องการตรวจสอบไฟล์dartหลักให้ไปที่bin/first_app.dartและแก้ไขโค้ดของคุณ

## **เรียกใช้ โครงการ dart** ##
ขั้นแรกให้เปิดตําแหน่งโครงการบนคําสั่ง/เทอร์มินัลและใช้คําสั่งนี้เพื่อเรียกใช้โครงการ

```dart
 dart run
```

## **แปลงรหัส dart เป็น Javascript** ##
คําสั่ง | คําอธิบาย
------------ | -------------
dart รวบรวมแฟ้ม js ชื่อแฟ้ม.dart | คอมไพล์ dart ไปเป็นJavascript. คุณสามารถเรียกใช้ไฟล์นี้ด้วยNode.js

# Reference
https://www.javatpoint.com/dart-first-program
https://www.tutorialspoint.com/dart_programming/index.htm
https://dart-tutorial.com/introduction-and-basics/basic-dart-program/
