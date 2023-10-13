# Conditions in Dart
## เงื่อนไขในภาษา Dart
  ในการเขียนโปรแกรมคอมพิวเตอร์ เราจำเป็นที่จะต้องสามารถบอกคอมพิวเตอร์ได้ว่าต้องทำอะไรในสถานการณ์ต่างๆ ด้วยเงื่อนไขเราจะสามารถควบคุมการไหลของโปรแกรมภาษา Dart ได้
## ประเภทของเงื่อนไข
  1. เงื่อนไข If 
  2. เงื่อนไข If-Else 
  3. เงื่อนไข If-Else-If 
  4. Switch case
## 1. เงื่อนไข If
  เงื่อนไข If เป็นเงื่อนไขที่ง่ายที่สุดในการใช้ควบคุมการไหลของโปรแกรม เรียกใช้งานผ่านการใช้คำสั่ง if โดยโปรแกรมจะทำงานต่อหากเงื่อนไขที่กำหนดเป็นจริง
> ## Flowchart การทำงานของเงื่อนไข If  
  
  ![image](https://github.com/soonklang/dart-tutorial/assets/95902698/3a2481ef-4ee6-4d21-9cd1-4cdbeb5602ad)

> ## Syntax
  ```dart
    if(condition){
      Statement 1;
      Statement 2;    
         .
         .
      Statement n;
    }
  ```
> ## ตัวอย่างการทำงานของเงื่อนไข If
>  โปรแกรมนี้จะทำการพิมพ์คำว่า voter ออกมาหากค่าอายุของคนคนนั้นมากกว่าหรือเท่ากับ 18
 ```dart
  void main(){
    var age = 20;
    
    if(age >= 18){
      print("You are voter.");
    }
  }
```
<details close>
 <summary><b>output</b></summary>
 <pre>
You are voter.
 </pre>
</details>

> ## ตัวอย่างการทำงานเพิ่มเติมของเงื่อนไข If
> โปรแกรมนี้จะทำเปรียบเทียบค่าที่อยู่ในตัวแปร x กับค่าที่อยู่ในตัวแปร y 
```dart
  void main(){
  int x = 10,y=15;
  if(x>y){
    print("$x มากกว่า $y");//ถ้าเงื่อนไขจริง
  }
  print("จบการทำงาน");
  }​
}
```
<details close>
 <summary><b>output</b></summary>
 <pre>
จบการทำงาน
 </pre>
</details>

## 2. เงื่อนไข If-Else
  เงื่อนไข If-Else เป็นเงื่อนไขเพื่อสร้างทางเลือก 2 ทาง ถ้าทางเลือกแรกเป็นเท็จ จึงจะรัน statement ทางเลือกที่สอง
> ## Flowchart การทำงานของเงื่อนไข If-Else
  ![image](https://github.com/soonklang/dart-tutorial/assets/95902698/3614aec4-3bb6-47ef-967f-ddec23f41854)


> ## Syntax
```dart
    if(condition){
      statements;
    }else{
      statements;
    }
```
> ## ตัวอย่างการทำงานของเงื่อนไข If-Else
> โปรแกรมภาษา Dart ที่ทำการพิมพ์ข้อความออกมาว่าบุคคลนั้นเป็นผู้มีสิทธิเลือกตั้งหรือไม่ โดยจะพิจารณาจากค่าอายุ
```dart
  void main(){
    int age = 12;
    if(age >= 18){
      print("You are voter.");
    }else{
      print("You are not voter.");
    }
  }
```
<details close>
<summary><b>output</b></summary>
 <pre>
You are not voter.
 </pre>
</details>

> ## ตัวอย่างการทำงานเพิ่มเติมของเงื่อนไข If-Else
> โปรแกรมนี้จะทำการเช็คว่าค่าตัวเลขที่อยู่ในตัวแปร x นั้นเป็นเลขคู่หรือเลขคี่
```dart
  void main() {
  int x = 4;
    if(x%2 == 0){
      print("$x is even");
    }else{
      print("$x is odd");
    }
  }
```
<details close>
<summary><b>output</b></summary>
 <pre>
4 is even
 </pre>
</details>

> ## เงื่อนไขที่ขึ้นอยู่กับค่าของบูลีน
> ถ้าหากสถานะแต่งงานไม่เป็นจริง โปรแกรมจะพิมพ์ข้อความ you are single ออกมา แต่ถ้าสถานะแต่งงานเป็นจริง โปรแกรมจะพิมพ์ข้อความ you are married ออกมา
```dart
  void main(){
    bool isMarried = false;
    if(isMarried){
      print("You are married.");
    }else{
      print("You are single.");
    }
  }
```
<details close>
<summary><b>output</b></summary>
 <pre>
You are single.
 </pre>
</details>

## 3. เงื่อนไข If-Else-IF
เงื่อนไข If-Else-If เป็นเงื่อนไขที่มีการทำงานคล้ายกันกับเงื่อนไข If-Else แต่เป็นการสร้างทางเลือกมากกว่า 2 ทาง และจะดูเงื่อนไขเรียงลำดับไปเรื่อยๆจนถึงอันที่ถูก จากนั้นก็จะรันคำสั่ง แล้วออกจาก decision

> ## Flowchart การทำงานของเงื่อนไข IF-Else-IF
  ![image](https://github.com/soonklang/dart-tutorial/assets/95902698/072b11db-94c4-463c-ab2c-1eba501cd5f2)

> ## Syntax
```dart
  if(condition1){
    statements1;
  }else if(condition2){
    statements2;
  }else if(condition3){
    statements3;
  }
  .
  .
  .
  else(conditionN){
    statementsN;
  }
```
> ## ตัวอย่างการทำงานของเงื่อนไข If-Else-If
> โปรแกรมต่อไปนี้จะทำการพิมพ์ชื่อของเดือนออกมาตามค่าตัวเลขของเดือนนั้น ผลลัพธ์จะแตกต่างกันออกไปหากเราเปลี่ยนค่าตัวเลขของเดือน
```dart
 void main() {
  int noOfMonth = 5;

  // Check the no of month
  if (noOfMonth == 1) {
    print("The month is jan");
  } else if (noOfMonth == 2) {
    print("The month is feb");
  } else if (noOfMonth == 3) {
    print("The month is march");
  } else if (noOfMonth == 4) {
    print("The month is april");
  } else if (noOfMonth == 5) {
    print("The month is may");
  } else if (noOfMonth == 6) {
    print("The month is june");
  } else if (noOfMonth == 7) {
    print("The month is july");
  } else if (noOfMonth == 8) {
    print("The month is aug");
  } else if (noOfMonth == 9) {
    print("The month is sep");
  } else if (noOfMonth == 10) {
    print("The month is oct");
  } else if (noOfMonth == 11) {
    print("The month is nov");
  } else if (noOfMonth == 12) {
    print("The month is dec");
  } else {
    print("Invalid option given.");
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
The month is may
 </pre>
</details>

## การหาค่าตัวเลขที่มากที่สุดจากทั้งหมด 3 ค่าตัวเลข
  โปรแกรมภาษา Dart ที่ใช้ในการหาค่าตัวเลขที่มากที่สุดจากทั้งหมด 3 ค่าตัวเลข
```dart
  void main(){
        int num1 = 1200;
        int num2 = 1000;
        int num3 = 150;

        if(num1 > num2  && num1 > num3){
            print("Num 1 is greater: i.e $num1");
        }
        if(num2 > num1 && num2 > num3){
           print("Num2 is greater: i.e $num2");
        }
        if(num3 > num1 && num3 > num2){
            print("Num3 is greater: i.e $num3");
        }
    }
```
<details close>
<summary><b>output</b></summary>
 <pre>
Num 1 is greater: i.e 1200
 </pre>
</details>

## ความแตกต่างของเงื่อนไขในภาษา Dart กับ ภาษา C,Java,Python
 ## Syntax
```dart
  ภาษา Dart
  if(condition1){
    // block of code to be executed if condition1 is true
  }else if(condition2){
    block of code to be executed if the condition1 is false and condition2 is true
  }else(condition){
    block of code to be executed if the condition1 is false and condition2 is false
  }
```
```dart
  ภาษา C
  if (condition1) {
    // block of code to be executed if condition1 is true
  } else if (condition2) {
    // block of code to be executed if the condition1 is false and condition2 is true
  } else {
    // block of code to be executed if the condition1 is false and condition2 is false
  }
```
```dart
  ภาษา Java
  if (condition1) {
    // block of code to be executed if condition1 is true
  } else if (condition2) {
    // block of code to be executed if the condition1 is false and condition2 is true
  } else {
    // block of code to be executed if the condition1 is false and condition2 is false
  }
```
```dart
  ภาษา Python
  if condition:
    // block of code to be executed if condition1 is true
  elif condition:
    // block of code to be executed if the condition1 is false and condition2 is true
  else:
    // block of code to be executed if the condition1 is false and condition2 is false
```
>จากการเปรียบเทียบ Syntax ของทั้ง 4 ภาษาพบว่า ภาษา Dart,C และ Java มี Syntax ในการเขียนโปรแกรมที่เหมือนกัน แต่ในภาษา Python นั้นแตกต่างออกไป

 สิ่งที่ภาษา Dart,C และ Java แตกต่างจากภาษา Python 
  > - ภาษา Dart,C และ Java จำเป็นต้องใส่ () ครอบเงื่อนไขที่กำหนดขึ้นต่างจากภาษา Python ที่ไม่จำเป็นต้องใส่
  > - คำสั่งในการเรียกใช้งานเงื่อนไข Else-If ของภาษา Dart,C และ Java ใช้เป็นคำสั่ง else แต่ในภาษา Python นั้นใช้เป็นคำสั่ง elif 
## Video
วิดีโอการศึกษาเกี่ยวกับเงื่อนไขในภาษา Dart

https://www.youtube.com/watch?v=B17QgDSAovk&t=1s

## สไลด์การบรรยาย
[Conditions_in_Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12774769/Conditions_in_Dart.pptx)
[Conditions_in_Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12888702/Conditions_in_Dart.pdf)

## Video การบรรยาย
https://www.youtube.com/watch?v=c5QqVwIRE2c

# Reference
https://dart-tutorial.com/conditions-and-loops/conditions-in-dart/

https://toupawa.com/learn-dart-from-zero-to-standard/

https://www.w3schools.com/c/c_conditions.php

https://www.w3schools.com/java/java_conditions.asp

https://www.w3schools.com/python/python_conditions.asp

https://www.mindphp.com/%E0%B8%9A%E0%B8%97%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%99%E0%B8%AD%E0%B8%AD%E0%B8%99%E0%B9%84%E0%B8%A5%E0%B8%99%E0%B9%8C/%E0%B8%9A%E0%B8%97%E0%B9%80%E0%B8%A3%E0%B8%B5%E0%B8%A2%E0%B8%99-dart-flutter/8904-control-structures-in-dart-language.html

https://www.tutorialspoint.com/dart_programming/dart_programming_if_else_statement.htm
https://www.darttutorial.org/dart-tutorial/dart-if-else-if/
