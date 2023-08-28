# Inheritance In Dart
  การสืบทอด(Inheritance) คือ การที่ class หรือ object ได้รับการถ่ายทอด attributeและ method จากclassอื่น นั่นจะทำให้คลาสดังกล่าวมี attribute และ method เหมือน class ที่มันสืบทอดมา จะเรียกว่า Parent Class,base class หรือ superclass. ส่วน class ที่ได้รับการสืบทอดเรียกว่า Child Class,deprived class หรือ subclass 
# Syntax ใน ภาษา Dart
```dart
class ParentClass {
  // Parent class code
}

class ChildClass extends ParentClass {
  // Child class code
}
```
# Syntax ใน ภาษา ภาษาอื่นๆ
- Java
```java
class Employee{  
   //code
}  
class Programmer extends Employee{  
  //code
} 
```
เมื่อเปรียบเทียบ syntax ของ ภาษา dart กัย java จะมี syntaxที่ใช้ในการ Inheritance ที่เหมือนกัน

- Python
```python
class Parent:
  #code
class Child(Parent):
  #code
```
แต่เมื่อเปรียบเทียบ syntax กับภาษา python แล้ว ตัวภาษา pythonจะใช้ () แทน keyword extand

#  Example 1: Inheritance In Dart
```dart
class Person {
  // Properties
  String? name;
  int? age;

  // Method
  void display() {
    print("Name: $name");
    print("Age: $age");
  }
}
// Here In student class, we are extending the
// properties and methods of the Person class
class Student extends Person {
  // Fields
  String? schoolName;
  String? schoolAddress;

  // Method
  void displaySchoolInfo() {
    print("School Name: $schoolName");
    print("School Address: $schoolAddress");
  }
}

void main() {
  // Creating an object of the Student class
  var student = Student();
  student.name = "John";
  student.age = 20;
  student.schoolName = "ABC School";
  student.schoolAddress = "New York";
  student.display();
  student.displaySchoolInfo();
}
```
จากในตัวอย่าง เราจะสร้างclass Person จากนั้นสร้างclass Student ที่ inheritance คุณสมบัติ และ methodของclass Person

output
```
Name: John
Age: 20
School Name: ABC School
School Address: New York
```
## ข้อดีของInheritance ใน Dart
- ส่งเสริมการนำ code กลับมาใช้ซ้ำได้และลด code ที่ซ้ำซ้อน
- ช่วยในการออกแบบโปรแกรมให้ดีขึ้น
- ช่วยให้ code ง่ายขึ้น สะอาดขึ้น และประหยัดเวลา
- อำนวยความสะดวกในการสร้างclass libraries

# Example 2: Inheritance In Dart
```dart
class Car{
  String? color;
  int? year;

  void start(){
    print("Car started");
  }  
}

class Toyota extends Car{
  String? model;
  int? prize;

  void showDetails(){
    print("Model: $model");
    print("Prize: $prize");
  }
}

void main(){
  var toyota = Toyota();
  toyota.color = "Red";
  toyota.year = 2020;
  toyota.model = "Camry";
  toyota.prize = 20000;
  toyota.start();
  toyota.showDetails();
}
```
จากตัวอย่างนี้ parent class คือ Car และ child class คือ Toyota 
class Toyota จะทำการ inheritance คุณสมบัติและ method ของ Car

output
```
Car started
Model: Camry
Price: 20000
```
# ประเภทของInheritance ใน Dart
ประเภทของinheritnce ใน dart มีอยู่ 4 ประเภทดังนี้

  1.Single Inheritance
  
  2.Multilevel Inheritance
  
  3.Hierarchical Inheritance
  
  4.Multiple Inheritance
  
แต่ในภาษา Java มี 5 ประเภท จะมีการเพิ่ม Hybrid Inheritance เข้ามา

1. Single Inheritance
   inheritance ประเภทนี้ sub classจะสามารถทำการinheritanceจาก super class เดียวเท่านั้น
   ใน Dart เราสามารถ extend ได้ครั้งละหนึ่ง class เท่านั้น
   
   ![image](https://github.com/soonklang/dart-tutorial/assets/141731788/2006eac9-6526-4757-a9c4-0559fb066768)

  #### `Example 1 :` Single Inheritance In Dart
  ```dart
    class Car {
    // Properties
    String? name;
    double? prize;
  }
  
  class Tesla extends Car {
    // Method to display the values of the properties
    void display() {
      print("Name: ${name}");
      print("Prize: ${prize}");
    }
  }
  
  void main() {
    // Create an object of Tesla class
    Tesla t = new Tesla();
    // setting values to the object
    t.name = "Tesla Model 3";
    t.prize = 50000.00;
    // Display the values of the object
    t.display();
  }
  ```
จากตัวอย่างด้านบนนี้ มีsuper classชื่อ Car พร้อมด้วยชื่อคุณสมบัติ มีsub classชื่อ Tesla ซึ่งสืบทอดคุณสมบัติของsuper class 
output
```
Name: Tesla Model 3
Prize: 50000.0
```
 #### `Example 2 :` Single Inheritance In Dart
 ```dart
  class Person{
    void showName(String name){
      print(name);
    }

    void showAge(int age){
      print(age);
    }
  }

  class Jay extends Person {}

  main(){
    var jay = new Jay();

    jay.showName("JD");
    jay.showAge(20);
  }
```
output
```
  JD
  20
```
2. Multilevel Inheritance
   
   ![image](https://github.com/soonklang/dart-tutorial/assets/141731788/840d3601-c5f0-4fe1-9f3b-00866a95c2ef)

3. Hierarchical Inheritance

  ![image](https://github.com/soonklang/dart-tutorial/assets/141731788/c85e6699-feb7-4be4-96e8-3d4de6edb8ed)

4. Multiple Inheritance

   ![image](https://github.com/soonklang/dart-tutorial/assets/141731788/dd87210d-7acb-4feb-84fc-3286f57c4b6f)
