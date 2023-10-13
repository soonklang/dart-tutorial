# Practice7

## 1.What is the purpose of the ? operator in Dart null safety?
In Dart null safety, the ? operator serves as a key component to indicate nullable types and to help prevent null-related errors during compilation and runtime. It is used in several contexts:

  วัตถุประสงค์ของตัว operator “?” คือให้กำหนดค่าตัวแปรเริ่มต้นให้เป็น null 
หากต้องการใส่ค่าให้ตัวแปร(values) ก็สามารถใส่ได้เลย และตรวจจับ error ขณะ run code เพื่อที่จะได้ไม่เกิดการ error 
ในการประกาศตัวแปรแบบปกติ

### ตัวอย่างการใช้ ?

```dart
void main(){
  String? text;
 
  print(text); // give null

  String str;
  str = null; // error
  print(str);
}
```
```bash
 output: null
 output: error
```

## 2.Create a late variable named address, assign a US value to it and print it.
สร้างตัวแปร name address เป็นแบบ late variable ทำการ assign ค่า แล้วปริ้นดู
```dart
// late variable
late String name,address;
void main(){
  // assigning value to late variable
  name = "Jame";
  address = "Bangkok";
  print("Name: $name");   
  print("Address: $address");
}
```
```bash
 output:
Name: Jame
Address: Bangkok
```

## 3.How do you declare a nullable type in Dart null safety?
Nullable Types: When you declare a variable, parameter, or return type with ?, you're indicating that the value can be either of the specified type or null. For instance, int? signifies a nullable integer, meaning it can hold an integer value or be null.

การประกาศตัวแปรประเภท nullable type ทำได้โดยการเพิ่ม “?” ด้านหลังการประกาศ ชนิดข้อมูล int,double,String หรือ class ก็ใข้ได้ และอื่นๆ ทำให้เราสามารถกำหนดค่าของตัวแปรเป็นการระบุค่าหรือเป็นnullได้

### ตัวอย่างการประกาศ nullable type

```dart
int? nullableInt;      // Nullable integer
double? nullableDouble; // Nullable double
bool? nullableBool;    // Nullable boolean

String? nullableString = null;
```
```dart
class MyClass {
  // ...
}
MyClass? nullableInstance; // Nullable instance of custom class
```
## 4.Write a program in a dart to create an age variable and assign a null value to it using ?.
เขียนโปรแกรม create an age variable และกำหนดค่าให้เป็น null โดยใช้ “?”
การประกาศตัวแปรในรูปแบบของ nullable type

```bash
 use '?' สามารถใส่ค่า null ลงในตัวแปรได้
```

```dart
void main(){
   int? age; //  <<---
   age = null;
   print(age);  // give null
}
```
[Run code](https://dartpad.dev/?iex4wegg.1)
```bash
 not use '?' ไม่สามารถใส่ค่า null ลงในตัวแปรได้
```

```dart
void main(){
   int age;  //  <<---
   age = null;
   print(age);  // give error
}
```
[Run code](https://dartpad.dev/?iex4glrutfu2)
## 5.Write a function that accepts a nullable int parameter and returns 0 if the value is null using null coalescing operator '??'.
เขียนฟังก์ชัน ที่รับพารามิเตอร์เป็นประเภท int nullable และส่งค่าคืนเป็น 0 ถ้าค่าที่รับมาเป็น null โดยใช้ operator ‘??’
```dart
int returnZeroIfNull(int? value){
    return value ?? 0;  // ถ้าค่าเป็น null จะ return 0
}
void main(){
   int? value1;
        value1 = null;
   int? value2 = 5;

   print(returnZeroIfNull(value1));  // output 0
   print(returnZeroIfNull(value2));  // output 5
}
```
[Run code](https://dartpad.dev/?idex.5)

## 6.Write a function named generateRandom() in dart that randomly returns 100 or null. Also, assign a return value of the function to a variable named status that can’t be null. Give status a default value of 0, if generateRandom() function returns null.

เขียนฟังก์ชัน generatRandom() เพื่อสุ่มว่าจะคืนค่า 100 หรือ null 
กำหนดค่าส่งคืนมาให้ status ซึ่งไม่สามารถเป็น null ได้ 
ให้ status มี default เป็น 0 หากฟังก์ชันคืนค่าเป็น null

```dart
import 'dart:math';

int? generateRandom() {
  // Generate a random number between 0 and 1.
  int? randomValue = Random().nextInt(2);

  print("Random Number: $randomValue");
  
  // กำหนดเอง
  if(randomValue == 1){
    return randomValue = 100;
  } else {
    return randomValue = null;
  }
  
  //return randomValue ;
  
}
void main() {
  int? status = generateRandom() ?? 0;
   
  print("Generated Status: $status");
}
```

```bash
Random Number: 1
Generated Status: 100
```
```bash
Random Number: 0
Generated Status: 0  // return null จะถูกเปลี่ยนเป็น 0
```
[Run code](https://dartpad.dev/?iex6)

</details>

## Link Video

https://youtu.be/Pi0YifTRdm8

## file การนำเสนอ

[Practice7]

[Null safety in dart.pdf](https://github.com/soonklang/dart-tutorial/files/12888861/Null.safety.in.dart.pdf)

[Null safety in dart.pptx](https://github.com/soonklang/dart-tutorial/files/12888874/Null.safety.in.dart.pptx)




## References

- https://dart.dev/codelabs/null-safety#:~:text=Null-aware%20operators,-If%20a%20variable&text=Sometimes%20the%20flow%20of%20the,this%20operator%20throws%20an%20exception.

- https://dart-tutorial.com

- https://dev.to/pktintali/late-variables-in-dart-dart-learning-series-1-2opf

- https://dartpad.dev/?

- ChatGPT


```bash

640710553 นาย ภานุวัฒน์ เจนภพ CS
```
[try to project](https://www.educative.io/learn/home)




