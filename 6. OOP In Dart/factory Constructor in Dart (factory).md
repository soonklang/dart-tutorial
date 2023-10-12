# Factory Constructor in Dart (factory)
ในส่วนนี้เราจะเรียนรู้เกี่ยวกับ constructor แบบ factory พร้อมตัวอย่างการใช้งาน ก่อนที่เราจะเรียนรู้เกี่ยวกับ constructor แบบ factory เราควรมีความเข้าใจพื้นฐานเกี่ยวกับclassและobject constructor, abstract class, interface and inheritance in Dart ก่อน
# Factory Constructor In Dart
ทุกconstructorsของที่เราได้เรียนรู้จนถึงตอนนี้เป็น constructor แบบ generative แต่ Dart ยังมี constructor ประเภทพิเศษที่เรียกว่า constructor แบบ factory
constructor แบบ factory มอบความยืดหยุ่นมากขึ้นในการสร้างวัตถุ constructor แบบ generative เพียงแค่สร้างตัวอย่างของคลาสเท่านั้น แต่ constructor แบบ factory สามารถสร้างตัวอย่างของคลาสหรือคลาสย่อยได้เช่นกัน นอกจากนี้ยังใช้ในการส่งคืนตัวอย่างของคลาสที่ถูกเก็บไว้ในแคชได้อีกด้วย
# Syntax
```dart
class ClassName {
  factory ClassName() {
    // TODO: return ClassName instance
  }

  factory ClassName.namedConstructor() {
    // TODO: return ClassName instance
  }
}
```
# Rules For Factory Constructors
- factory Constructor จำเป็นต้องส่งคืนตัวอย่างของคลาสหรือคลาสย่อย
- ไม่สามารถใช้คีย์เวิร์ด this ภายใน factory constructor ได้
- มันสามารถมีชื่อหรือไม่มีชื่อและเรียกใช้เหมือนกับ constructor ทั่วไป
- มันไม่สามารถเข้าถึงสมาชิกของตัวอย่างได้
# Example 1: Without Factory Constructor
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Area ที่มีคุณสมบัติแบบ final คือ length และ breadth รวมถึง area ด้วย โดยเมื่อคุณส่งค่า length และ breadth ไปยัง constructor มันจะคำนวณพื้นที่และเก็บไว้ในคุณสมบัติ area
```dart
class Area {
  final int length;
  final int breadth;
  final int area;

  // Initializer list 
 const Area(this.length, this.breadth) : area = length * breadth;
}

void main() {
  Area area = Area(10, 20);
  print("Area is: ${area.area}");

  // notice that here is a negative value
  Area area2 = Area(-10, 20);
  print("Area is: ${area2.area}");
}
```
Output
```dart
Area is: 200
Area is: -200
```
วัตถุ area2 มีค่าที่เป็นลบ เนื่องจากยังไม่ได้ตรวจสอบข้อมูลเข้าเงื่อนไขการตรวจสอบ ในกรณีนี้เราจะสร้าง factory constructor เพื่อทำการตรวจสอบข้อมูลที่ถูกส่งเข้ามา
# Example 2: With Factory Constructor
ในตัวอย่างด้านล่างนี้ มีการใช้ factory constructor เพื่อทำการตรวจสอบข้อมูลเข้าเกณฑ์ หากข้อมูลเข้าเกณฑ์ถูกต้อง จะส่งคืนอินสแตนซ์ของคลาสใหม่ แต่หากข้อมูลเข้าเกณฑ์ไม่ถูกต้อง จะโยนข้อผิดพลาดออกมา
```dart
class Area {
  final int length;
  final int breadth;
  final int area;

  // private constructor
  const Area._internal(this.length, this.breadth) : area = length * breadth;

  // Factory constructor
  factory Area(int length, int breadth) {
    if (length < 0 || breadth < 0) {
      throw Exception("Length and breadth must be positive");
    }
    // redirect to private constructor
    return Area._internal(length, breadth);
  }
}

void main() {
  // This works
  Area area = Area(10, 20);
  print("Area is: ${area.area}");

  // notice that here is negative value
  Area area2 = Area(-10, 20);
  print("Area is: ${area2.area}");
}
```
Output
```dart
Area is: 200
Unhandled exception:
Exception: Length and breadth must be positive
```
# Example 3: Factory Constructor In Dart
ในตัวอย่างด้านล่างนี้ มี enum ชื่อ ShapeType มีค่าสองค่า คือ circle และ rectangle มีอินเทอร์เฟซชื่อ Shape มี factory constructor ที่สร้างวัตถุของชนิด Shape ที่เป็นวงกลมหรือสี่เหลี่ยม ในเมธอด main มีการสร้างวัตถุสองตัว หนึ่งในแต่ละชนิด และเรียกใช้เมธอด draw() บนแต่ละวัตถุ
```dart
// enum ShapeType
enum ShapeType { circle, rectangle }

// abstract class Shape
abstract class Shape {
  // factory constructor
  factory Shape(ShapeType type) {
    switch (type) {
      case ShapeType.circle:
        return Circle();
      case ShapeType.rectangle:
        return Rectangle();
      default:
        throw 'Invalid shape type';
    }
  }
  // method
  void draw();
}

class Circle implements Shape {
  // implement draw method
  @override
  void draw() {
    print('Drawing circle');
  }
}

class Rectangle implements Shape {
  // implement draw method
  @override
  void draw() {
    print('Drawing rectangle');
  }
}

void main() {
  // create Shape object
  Shape shape = Shape(ShapeType.circle);
  Shape shape2 = Shape(ShapeType.rectangle);
  shape.draw();
  shape2.draw();
}
```
Output
```dart
Drawing circle
Drawing rectangle
```
# Example 4: Factory Constructor In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Person ที่มีฟิลด์ final ชื่อ name นอกจากนี้ยังมี private constructorและฟิลด์ static _cache คลาสยังมี factory constructor ที่ตรวจสอบว่าฟิลด์ _cache มีคีย์ที่ตรงกับพารามิเตอร์ชื่อหรือไม่ หากมีคีย์ที่ตรงกันจะส่งคืนวัตถุ Person ที่เชื่อมโยงกับคีย์นั้น มิฉะนั้นจะสร้างวัตถุ Person ใหม่ นำไปเพิ่มใน _cache และส่งคืนกลับ
```dart
class Person {
  // final fields
  final String name;

  // private constructor
  Person._internal(this.name);

  // static _cache field
  static final Map<String, Person> _cache = <String, Person>{};

  // factory constructor
  factory Person(String name) {
    if (_cache.containsKey(name)) {
      return _cache[name]!;
    } else {
      final person = Person._internal(name);
      _cache[name] = person;
      return person;
    }
  }
}

void main() {
  final person1 = Person('John');
  final person2 = Person('Harry');
  final person3 = Person('John');

  // hashcode of person1 and person3 are same
  print("Person1 name is : ${person1.name} with hashcode ${person1.hashCode}");
  print("Person2 name is : ${person2.name} with hashcode ${person2.hashCode}");
  print("Person3 name is : ${person3.name} with hashcode ${person3.hashCode}");
}
```
Output
```dart
Person1 name is : John with hashcode 117
Person2 name is : Harry with hashcode 118
Person3 name is : John with hashcode 117
```
# Factory ในภาษาต่าง ๆ
Python
```dart
class BurgerStoreFactory(object):
    @staticmethod
    def getBurger(name):
        if name == 'Beef':
            return BeefBurgers()
        elif name == 'Chicken':
            return ChickenBurger()
        elif name == 'Fish':
            return FishBurger()
```
Java
```dart
public class BurgerStoreFactory { 
 public getBurger(name) { 
   if (name.equals("Beef")) {
     return BeefBurgers();
   } else if (name.equals("Chicken")) {
     return ChickenBurger(); 
   } else if (name.equals("Fish")) {
     return FishBurger();
   } 
   return null;
 }
}
```
ในภาษา java จะต่างจาก Python โดยใช้ { หลังคลาสแต่ Python ใช้ : และ java ใช้คำสั่ง.equalแต่ของ Python ใช้ == ในการเช็ค
# ที่มา
https://iq.opengenus.org/factory-pattern-in-python/

https://dart-tutorial.com/object-oriented-programming/factory-constructor-in-dart/

https://stackoverflow.com/questions/545419/using-base-class-constructor-as-factory-in-python
# Video
[Video](https://www.youtube.com/watch?v=c5fTgTG_XF0)
# สไลด์
[Factory Constructor in Dart (factory).pptx](https://github.com/soonklang/dart-tutorial/files/12883011/Factory.Constructor.in.Dart.factory.pptx)

[Factory Constructor in Dart (factory).pdf](https://github.com/soonklang/dart-tutorial/files/12883112/Factory.Constructor.in.Dart.factory.pdf)

https://drive.google.com/file/d/1jXnXznePUg9L8cQyqbW2AjSOrc_0LAsx/view?usp=drive_link
