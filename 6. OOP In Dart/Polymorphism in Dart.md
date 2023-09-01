# Polymorphism in Dart

## Introduction
ในบทนี้ คุณจะได้เรียนรู้เกี่ยวกับ POLYMORPHISM ในภาษา Dart ด้วยความช่วยเหลือของตัวอย่าง ก่อนที่จะเรียนรู้เกี่ยวกับ POLYMORPHISM ใน Dart คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับ inheritance ใน Dart

# Polymorphism In Dart
Poly แปลว่า มากมาย และ morph แปลว่า รูปร่าง Polymorphism คือความสามารถของวัตถุที่จะเกิดขึ้นได้หลายรูปแบบ ในการเขียนโปรแกรมเชิงวัตถุ polymorphism คือความสามารถของวัตถุในรูปแบบต่างๆ

# Syntax
```
class ParentClass{
void functionName(){
  }
}
class ChildClass extends ParentClass{
@override 
void functionName(){
  }
}
```


# Polymorphism มีสองรูปแบบใน Dart
 Polymorphism แบบ static (หรือที่เรียกว่า compile-time Polymorphism ) และ Polymorphism แบบ dynamic (หรือที่เรียกว่า Runtime Polymorphism)

# 1. Static Polymorphism
Method Overloading ใน Dart รองรับการโอเวอร์โหลดเมธอด(Overloading) ซึ่งช่วยให้คุณกำหนดวิธีการหลายวิธีด้วยชื่อเดียวกัน แต่มีพารามิเตอร์ต่างกันภายในคลาส วิธีการที่เหมาะสมจะถูกเลือกตามจำนวนและประเภทของอาร์กิวเมนต์(arguments) ณ เวลารวบรวม(compile time)

# Example 1 : Polymorphism By Method Overloading In Dart
ในเมธอด add() แรกมีประเภทเป็น Integer รับพารามิเตอร์เป็น Intrger แต่เมธอด add() ที่สองที่ทำการ Overloading Data Type ต่างกันกันแต่ชื่อเดิม จึงเรียกว่า Overloadinng
```
class MathUtils {
  int add(int a, int b) {
    return a + b;
  }

  double add(double a, double b) {
    return a + b;
  }
}

void main() {
  MathUtils math = MathUtils();
  print(math.add(2, 3));       // Output: 5
  print(math.add(2.5, 3.7));   // Output: 6.2
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>5
6.2</code>
</pre>
</details>

# 2. Dynamic Polymorphism
Method Overriding ใน Dart รองรับการแทนที่เมธอด(Method Overriding) ซึ่งอนุญาตให้คลาสย่อยจัดเตรียมการใช้งานเมธอดที่กำหนดไว้ในซูเปอร์คลาสของตัวเอง วิธีการที่เหมาะสมจะถูกเลือกในขณะรันไทม์ตามประเภทที่แท้จริงของออบเจ็กต์

# Example 2 : Polymorphism By Method Overriding In Dart
ในตัวอย่างด้านล่างนี้ โดยมีคลาสชื่อ Animal และมีเมธอดชื่อ makeSound() ทำการ Overriding ให้คลาสลูกที่ชื่อ cat และ Dog 

![This is an alt text.](https://www.guru99.com/images/2/062920_1112_CPolymorphi1.png)
```
class Animal {
  void makeSound() {
    print('The animal makes a sound.');
  }
}

class Cat extends Animal {
  @override
  void makeSound() {
    print('Meow!');
  }
}

class Cow extends Animal {
  @override
  void makeSound() {
    print('Moow!');
  }
}

void main() {
  Animal cat = Cat();
  Animal cow = Cow();
  
  cat.makeSound();   // Output: Meow!
  cow.makeSound();   // Output: Moow!
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Cat : Meow!
Cow : Moow!</code>
</pre>
</details>

# Example 3: Polymorphism By Method Overriding In Dart
ในตัวอย่างนี้ด้านล่าง มีคลาสชื่อ Vehicle โดยมีเมธอดชื่อ run() วิธีการ run() ถูกแทนที่ในคลาสลูกชื่อ Bus

```
class Vehicle {
  void run() {
    print("Vehicle is running");
  }
}

class Bus extends Vehicle {
  @override
  void run() {
    print("Bus is running");
  }
}

void main() {
  Vehicle vehicle = Vehicle();
  vehicle.run();

  Bus bus = Bus();
  bus.run();
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Vehicle is running
Bus is running</code>
</pre>
</details>

# Example 4: Polymorphism By Method Overriding In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Employee โดยมีเมธอดชื่อเงินเดือน() วิธีการเงินเดือน () ถูกแทนที่ในคลาสย่อยสองคลาสชื่อผู้จัดการและนักพัฒนา

```
class Employee{
  void salary(){
    print("Employee salary is \$1000.");
  }
}

class Manager extends Employee{
  @override
  void salary(){
    print("Manager salary is \$2000.");
  }
}

class Developer extends Employee{
  @override
  void salary(){
    print("Developer salary is \$3000.");
  }
}

void main(){
  Manager manager=Manager();
  Developer developer=Developer();
  
  manager.salary();
  developer.salary();
}
```

<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Manager salary is $2000.
Developer salary is $3000.</code>
</pre>
</details>

## Reference
https://dart-tutorial.com/object-oriented-programming/polymorphism-in-dart/

https://medium.com/@emanyaqoob/polymorphism-in-dart-refers-to-the-ability-of-objects-of-different-classes-to-be-treated-as-9e9d7cc9b4da#:~:text=Polymorphism%20in%20Dart%20refers%20to,a%20common%20interface%20or%20superclass.

https://mobikul.com/polymorphism-in-dart/
