# Inheritance In Dart
  การสืบทอด(Inheritance) คือ การที่ class หรือ object ได้รับการถ่ายทอด attributeและ method จากclassอื่น นั่นจะทำให้คลาสดังกล่าวมี attribute และ method เหมือน class ที่มันสืบทอดมา จะเรียกว่า Parent Class,base class หรือ superclass. ส่วน class ที่ได้รับการสืบทอดเรียกว่า Child Class,deprived class หรือ subclass 
#### `Syntax ใน ภาษา Dart ` 
```dart
class ParentClass {
  // Parent class code
}

class ChildClass extends ParentClass {
  // Child class code
}
```
#### `Syntax ในภาษาอื่นๆ `
<details>
  <summary><strong>Java</strong></summary>
  <pre>
  <code>
class Employee{  
   //code
}  
class Programmer extends Employee{  
  //code
} </code>
  </pre>
  </details>

<details>
  <summary><strong>Python</strong></summary>
  <pre>
  <code>
class Parent:
  #code
class Child(Parent):
  #code </code>
  </pre>
  </details>

#### `Example 1: `Inheritance In Dart
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

#### `Example 2: `Inheritance In Dart
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
# Inheritance ใน Dart
ประเภทของinheritnce ใน dart มีอยู่ 4 ประเภทดังนี้

  1.Single Inheritance -> subclass ทำการสืบทอด คุณสมสบัติต่างๆมาจาก class parent
  <details>
  <summary><strong>Syntax</strong></summary>
  <pre>
  <code>
class parent_class{
...
}
class child_class extends parent_class{
...
}</code>
  </pre>
  </details>
  
  2.Multilevel Inheritance -> subclass ทำการสืบทอด subclass อื่น 
                              Dart อนุญาตให้ class สืบทอดวิธีการและคุณสมบัติจากsubclass
  <details>
  <summary><strong>Syntax</strong></summary>
  <pre>
  <code>
class A {
    ...
}
class B extends A {
    ...
}
class C extends A {
    ...
}</code>
  </pre>
  </details>
  
  3.Hierarchical Inheritance -> การมี 2 subclass สืบทอดคุณสมบัติต่างๆ จาก class parent เดียวกัน
  <details>
  <summary><strong>Syntax</strong></summary>
  <pre>
  <code>
class A {
    ...
}
class B extends A {
    ...
}
class C extends A {
    ...
}</code>
  </pre>
  </details>
  
  4.Multiple Inheritance -> subclass  ทำการสืบทอดคุณสมบัติจาก class super มากว่า 1  
  <details>
  <summary><strong>Syntax</strong></summary>
  <pre>
  <code>
class A{
...
}
class B extends A{
...
}
class C extends B{
...
}</code>
  </pre>
  </details>
  
แต่ในภาษา Java มี 5 ประเภท จะมีการเพิ่ม Hybrid Inheritance เข้ามา

1. Single Inheritance
   subclass ทำการสืบทอด คุณสมสบัติต่างๆมาจาก class parent 
   
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
`
จากตัวอย่างด้านบนนี้ มี class parent ชื่อ Car โดยที่มี attribute ชื่อ name และ prize
จากนั้น เราสร้าง subclass ชื่อ Tesla พร้อมด้วยฟังก์ชัน display() ที่สืบทอดคุณสมบัติของ class parent
main() จะทำการสร้างวัตถุของ class และ กำหนดค่าให้กับ attribute โดยใช้ objects ของclass และ เรียกใช้ฟังก์ชัน
`

output
```
Name: Tesla Model 3
Prize: 50000.0
```

 #### `Example 2 :` Single Inheritance In Dart
 ```dart
// Dart program to show hierarchical inheritance
  
// Creating the parent class
class Animal{
    // Creating an attribute
    String breed;
  // Creating a function
  void display(){
    print("This is the Animal class called Parent class");
  }
}

// Creating a child class
class Cat extends Animal{
  // Creating a function
  void meow(){
      print("$breed meow everytime.");
  }
}
  
void main() {
  // Creating an object of the class Cat
  var cat = Cat();
  cat.breed = "Maine Coon";
  cat.meow();

  // Creating an object of the superclass Animal
  var animal = Animal();
  animal.display();
}
```
` จากตัวอย่าง เราสร้าง class parent ชื่อ Animal โดยมี attribute ที่ชื่อ breed และ ฟังก์ชัน display()
  จากนั้น เราสร้าง subclass ชื่อ Cat พร้อมด้วยฟังก์ชัน meow() ที่สืบทอดคุณสมบัติของ class parent
  และ ใน mian class เราสร้างวัตถุของclass Cat และ Animal สุดท้ายนี้ เรากำหนดค่าให้กับ attribute โดยใช้ objects ของclass และเรียกใช้ฟังก์ชัน 
`
      
output
```
  Maine Coon meow everytime.
  This is the Animal class called Parent class
```
## Slide & Clip
[Slide Inheritance in dart](https://drive.google.com/file/d/1NHjKkStk0nrNAavgxp4eK9byH1hSmsh1/view?usp=drive_link)

[Clip Inheritance in dart](https://drive.google.com/file/d/1--KlgR73pPHzkugaX9_tKHgzbB50wK3e/view?usp=drive_link)
## แหล่งอ้างอิง

https://www.geeksforgeeks.org/dart-concept-of-inheritance/

https://blog.devgenius.io/object-oriented-programming-in-java-57202e7c0abd

http://marcuscode.com/lang/python/inheritance

https://www.educative.io/answers/what-is-single-level-inheritance-in-dart

https://www.tutorialspoint.com/hierarchical-inheritance-in-dart-programming#:~:text=Hierarchical%20inheritance%20is%20the%20case,classes%20inherit%20a%20single%20class.&text=In%20the%20above%20syntactic%20representation,(or%20extending)%20class%20A.

https://www.educative.io/answers/what-is-multi-level-inheritance-in-dart
