# Practice7

## 1.What is the purpose of the ? operator in Dart null safety?

  วัตถุประสงค์ของตัว operator “?” คือให้กำหนดค่าตัวแปรเริ่มต้นให้เป็น null 
หากต้องการใส่ค่าให้ตัวแปร(values) ก็สามารถใส่ได้เลย เพื่อที่จะได้ไม่เกิดการ error 
ในการประกาศตัวแปรแบบปกติ

```dart
void main(){
  String? text;
  text = null; // give null
  print(text);

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

```dart
// late variable
late String name;
void main(){
  // assigning value to late variable
  name = "US";
  print(name);   // give 'US'
}
```

## 3.How do you declare a nullable type in Dart null safety?


## 4.Write a program in a dart to create an age variable and assign a null value to it using ?.

การประกาศตัวแปรในรูปแบบของ nullable type

```bash
 use '?' สามารถใส่ค่า null ลงในตัวแปรได้
```

```dart
void main(){
   int? age; //  <<---
   aeg = null;
   print(aeg);  // give null
}
```

```bash
 not use '?' ไม่สามารถใส่ค่า null ลงในตัวแปรได้
```

```dart
void main(){
   int age;  //  <<---
   aeg = null;
   print(aeg);  // give error
}
```

## 5.Write a function that accepts a nullable int parameter and returns 0 if the value is null using null coalescing operator '??'.

```dart
int returnZeroIfNull(int? value){
    return value ?? 0;  // ถ้าค่าเป็น null จะ return 0
}
void main(){
   int? value1 = null;
   int? value1 = 5;

   print(returnZeroIfNull(value1));  // output 0
   print(returnZeroIfNull(value2));  // output 5
}
```

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
  
  if(randomValue == 1){
    return 100;
  } else {
    return 0;
  }

  //return randomValue >= 1 ? 100 : 0;
}
void main() {
  int? status = generateRandom() ?? 0;
  
 // print("Generated Status: $status");
   
  if(status == 0){
     print("Generated Status: null");
  } else {
     print("Generated Status: $status");
  }
}
```
[Run code](https://dartpad.dev/?id=0b97978a7e5d8a4f830d9bb2648c65a9)

```bash
Random Number: 1
Generated Status: 100
```
```bash
Random Number: 0
Generated Status: null
```














