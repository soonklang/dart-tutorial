# Mixin In Dart
  Mixin เป็นวิธีหนึ่งในการ reuse โค้ดในคลาสหลายคลาส การประกาศ mixin ใช้คำสำคัญ "mixin" ตามด้วยชื่อของ mixin นั้น มีคำสำคัญ 3 คำสำคัญที่ใช้เมื่อทำงานกับ mixins: mixin, with, และ on สามารถใช้ mixins หลายๆ ตัวในคลาสได้
# Rules For Mixin
  - **Mixin ไม่สามารถสร้างอ็อบเจ็กต์ได้ เราไม่สามารถสร้างวัตถุ (object) ของ mixin ได้**
  - **ใช้ mixin เพื่อแบ่งปันโค้ดระหว่างคลาสหลายๆ คลาส**
  - **Mixin ไม่มี constructor และไม่สามารถถูกสืบทอด (extended) ได้**
  - **เป็นไปได้ที่จะใช้ mixins หลายตัวในคลาสหนึ่ง**
# Syntax
```dart
mixin Mixin1{
  // code
}

mixin Mixin2{
  // code
}

class ClassName with Mixin1, Mixin2{
  // code
}
```
# Example 1: Mixin In Dart
ในตัวอย่างด้านล่างนี้ มี mixin สองตัวชื่อ ElectricVariant และ PetrolVariant โดย ElectricVariant mixin มีเมธอดชื่อ electricVariant() และ PetrolVariant mixin มีเมธอดชื่อ petrolVariant() คลาส Car ใช้ mixins ทั้งสองตัวคือ ElectricVariant และ PetrolVariant
 ```dart
mixin ElectricVariant {
  void electricVariant() {
    print('This is an electric variant');
  }
}

mixin PetrolVariant {
  void petrolVariant() {
    print('This is a petrol variant');
  }
}
// with is used to apply the mixin to the class
class Car with ElectricVariant, PetrolVariant {
  // here we have access of electricVariant() and petrolVariant() methods
}

void main() {
  var car = Car();
  car.electricVariant();
  car.petrolVariant();
}
}
```
# Example 2: Mixin In Dart
ในตัวอย่างด้านล่างนี้ มี mixin สองตัวชื่อ CanFly และ CanWalk โดย CanFly mixin มีเมธอดชื่อ fly() และ CanWalk mixin มีเมธอดชื่อ walk() คลาส Bird ใช้ mixins ทั้งสองตัวคือ CanFly และ CanWalk ส่วนคลาส Human ใช้ mixin CanWalk
 ```dart
mixin CanFly {
  void fly() {
    print('I can fly');
  }
}

mixin CanWalk {
  void walk() {
    print('I can walk');
  }
}

class Bird with CanFly, CanWalk {
 
}

class Human with CanWalk {
 
}

void main() {
  var bird = Bird();
  bird.fly();
  bird.walk();

  var human = Human();
  human.walk();
}

```
# On Keyword
บางครั้งคุณอาจต้องการใช้ mixin เฉพาะกับคลาสที่กำหนดเจาะจง ในกรณีนี้คุณสามารถใช้ keyword "on"
# Syntax Of On Keyword
```dart
mixin Mixin1 on Class1{
  // code
}
```
# Example 3: On Keyword In Mixin In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสแม่เบี้ยวชื่อ Animal ที่มีคุณสมบัติชื่อและความเร็ว (name และ speed) คลาส Animal ยังมีเมธอด run() ที่เป็น abstract method คลาส CanRun จะถูกใช้เฉพาะกับคลาสที่สืบทอด (extends) จากคลาส Animal คลาส Dog สืบทอดจากคลาส Animal และใช้ mixin CanRun ส่วนคลาส Bird ไม่สามารถใช้ mixin CanRun ได้เนื่องจากไม่ได้สืบทอดคลาส Animal
```dart
abstract class Animal {
  // properties
  String name;
  double speed;

  // constructor
  Animal(this.name, this.speed);

  // abstract method
  void run();
}

// mixin CanRun is only used by class that extends Animal
mixin CanRun on Animal {
  // implementation of abstract method
  @override
  void run() => print('$name is Running at speed $speed');
}

class Dog extends Animal with CanRun {
  // constructor
  Dog(String name, double speed) : super(name, speed);
}

void main() {
  var dog = Dog('My Dog', 25);
  dog.run();
}

// Not Possible
// class Bird with Animal { } 
}
```
# What Is Allowed For Mixin
- **สามารถเพิ่มคุณสมบัติและตัวแปรแบบสแตติก (static variables) ได้**
- **สามารถเพิ่มเมธอดปกติ (regular methods), เมธอด abstract, และเมธอดแบบสแตติก (static methods) ได้**
- **สามารถใช้ mixin หนึ่งหรือมากกว่าหนึ่งในคลาสได้**
# What Is Not Allowed For Mixin
- **ไม่สามารถกำหนดคอนสตรักเตอร์ได้**
- **ไม่สามารถสืบทอด (extend) mixin ได้**
- **ไม่สามารถสร้างอ็อบเจ็กต์ของ mixin ได้**
