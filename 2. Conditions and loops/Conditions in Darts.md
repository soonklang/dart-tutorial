# Conditions in Dart
## เงื่อนไขในภาษา Dart
การเขียนโปรแกรมคอมพิวเตอร์ เราจำเป็นที่จะต้องสามารถบอกคอมพิวเตอร์ได้ว่าต้องทำอะไรในสถานการณ์ต่างๆ ด้วยเงื่อนไข เราจะสามารถควบคุมการไหลของโปรแกรมภาษา Dart ได้
## ประเภทของเงื่อนไข
  - เงื่อนไข If 
  - เงื่อนไข If-Else 
  - เงื่อนไข If-Else-If 
  - Switch case
## เงื่อนไข If
เป็นเงื่อนไขที่ง่ายที่สุดในการใช้ควบคุมการไหลของโปรแกรมเรียกใช้งานผ่านการใช้คำสั่ง if โดยโปรแกรมจะทำงานต่อหากเงื่อนไขที่กำหนดเป็นจริง
## Syntax
  ```dart
    if(condition){
      Statement 1;
      Statement 2;    
         .
         .
      Statement n;
    }
  ```
## ตัวอย่างการทำงานของเงื่อนไข If
โค๊ดนี้จะทำการพิมพ์คำว่า voter ออกมา ถ้าหากค่าอายุของคนคนนั้นมากกว่าหรือเท่ากับ 18
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

## เงื่อนไข If-Else
หากผลลัพท์ของเงื่อนไขเป็นจริง โค๊ดที่อยู่ภายใต้เงื่อนไข If จะถูกดำเนินการ แต่ถ้าไม่ โค๊ดที่อยู่ภายใต้เงื่อนไข Else จะถูกดำเนินการ

## Syntax
```dart
    if(condition){
      statements;
    }else{
      statements;
    }
```
## ตัวอย่างการทำงานของเงื่อนไข If-Else
โปรแกรมภาษา Dart จะพิมพ์ข้อความว่าบุคคลนั้นเป็นผู้มีสิทธิเลือกตั้งหรือไม่ โดยจะพิจารณาจากอายุ
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

## เงื่อนไขที่ขึ้นอยู่กับค่าของบูลีน
ถ้าหากสถานะแต่งงานไม่เป็นจริง โปรแกรมจะพิมพ์ข้อความ you are single ออกมา แต่ถ้าสถานะแต่งงานเป็นจริง โปรแกรมจะพิมพ์ข้อความ you are married ออกมา
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

## เงื่อนไข If-Else-IF
หากมีเงื่อนไข If หลายเงื่อนไข สามารถใช้ if-else-if ศึกษาการทำงานได้จากตัวอย่างด้านล่าง 
## Syntax
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
## ตัวอย่างการทำงานของเงื่อนไข If-Else-If
โปรแกรมต่อไปนี้จะทำการพิมพ์ชื่อของเดือนออกมา ตามค่าตัวเลขของเดือนนั้น ผลลัพธ์จะแตกต่างกันออกไปหากเราเปบี่ยนค่าตัวเลขของเดือน
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
