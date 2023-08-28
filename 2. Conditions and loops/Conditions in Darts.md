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
    if(กำหนดเงื่่อนไข){
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
