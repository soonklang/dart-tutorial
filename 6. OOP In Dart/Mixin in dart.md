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
# ตัวอย่างของ Mixin ในภาษาที่ Python,JavaScript(ES6),Ruby
 ### ข้อเเตกต่างการใช้งาน
 ### Python
Mixin ใน Python สามารถเรียกใช้เมท็อดและแอตทริบิวต์ในคลาสหรืออ็อบเจ็กต์ที่สืบทอด mixin ได้โดยตรง.
### Ruby
Mixin ใน Ruby สามารถเรียกใช้เมท็อดและแอตทริบิวต์ในคลาสหรืออ็อบเจ็กต์ที่รวม mixin ไปในคลาสด้วยการเรียกใช้เมธอดหรือแอตทริบิวต์.
### JavaScript
Mixin ใน JavaScript สามารถเรียกใช้เมท็อดและแอตทริบิวต์ในอ็อบเจ็กต์ที่ใช้ mixin โดยตรง.
### ตัวอย่าง: การใช้ Mixin เพื่อคำนวณพื้นที่สี่เหลี่ยม
 ### Python
 ```python
 class RectangleMixin:
    def area(self):
        return self.width * self.height

class Rectangle(RectangleMixin):
    def __init__(self, width, height):
        self.width = width
        self.height = height

class Square(RectangleMixin):
    def __init__(self, side_length):
        self.width = self.height = side_length

rectangle = Rectangle(5, 10)
print("Rectangle area:", rectangle.area())

square = Square(7)
print("Square area:", square.area())
```
### Ruby
```ruby
 module RectangleMixin
  def area
    @width * @height
  end
end

class Rectangle
  include RectangleMixin
  def initialize(width, height)
    @width = width
    @height = height
  end
end

class Square
  include RectangleMixin
  def initialize(side_length)
    @width = @height = side_length
  end
end

rectangle = Rectangle.new(5, 10)
puts "Rectangle area: #{rectangle.area}"

square = Square.new(7)
puts "Square area: #{square.area}"

```
### JavaScript (ES6)
```JavaScript
const RectangleMixin = {
  area() {
    return this.width * this.height;
  }
};

class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
}

Object.assign(Rectangle.prototype, RectangleMixin);

class Square {
  constructor(sideLength) {
    this.width = this.height = sideLength;
  }
}

const rectangle = new Rectangle(5, 10);
console.log(`Rectangle area: ${rectangle.area()}`);

const square = new Square(7);
console.log(`Square area: ${square.area()}`);
```
ในตัวอย่างทั้งหมดนี้เราใช้ mixin เพื่อเพิ่มฟังก์ชัน area ในคลาส Rectangle และ Square เพื่อคำนวณพื้นที่ของสี่เหลี่ยม โดยไม่ต้องเขียนโค้ดการคำนวณพื้นที่ซ้ำซ้อนในทุกคลาส ทำให้โค้ดเป็นระเบียบและมีความยืดหยุ่นในการแก้ไขและเพิ่มคุณสมบัติใหม่ ทั้งนี้เป็นตัวอย่างที่แสดงถึงการใช้ mixin ในภาษา Python, Ruby และ JavaScript (ES6) ในทางปฏิบัติ
# What Is Allowed For Mixin
- **สามารถเพิ่มคุณสมบัติและตัวแปรแบบสแตติก (static variables) ได้**
- **สามารถเพิ่มเมธอดปกติ (regular methods), เมธอด abstract, และเมธอดแบบสแตติก (static methods) ได้**
- **สามารถใช้ mixin หนึ่งหรือมากกว่าหนึ่งในคลาสได้**
# What Is Not Allowed For Mixin
- **ไม่สามารถกำหนดคอนสตรักเตอร์ได้**
- **ไม่สามารถสืบทอด (extend) mixin ได้**
- **ไม่สามารถสร้างอ็อบเจ็กต์ของ mixin ได้**
## Reference
[Mixin in dart](https://dart-tutorial.com/object-oriented-programming/mixins-in-dart/)
<br>
[Minin in JavaScript](https://www.tutorialspoint.com/mixins-in-javascript)
<br>
[Minin in ruby](https://www.tutorialspoint.com/ruby/ruby_modules.htm)
<br>
[Example](https://en.wikipedia.org/wiki/Mixin)
<br>
# Video
[Video](https://www.youtube.com/watch?v=it0O8oQBliQ)
# Presentation
[Presentation (3).pdf](https://github.com/soonklang/dart-tutorial/files/12883031/Presentation.3.pdf)
<br>
[Presentation (5).pptx](https://github.com/soonklang/dart-tutorial/files/12889679/Presentation.5.pptx)

