# *Getter and Setter in Dart*
Getter และ Setter เป็นวิธีการเข้าถึงหรือเปลี่ยนแปลงคุณสมบัติ (Properties) ในวัตถุ(Object)นั้นๆ
ในการเขียนภาษา Dart เราจะใช้คำว่า get กับ set เป็น Keywords ในการกำหนด Getter กับ Setter
โดยที่ Getter ทำหน้าที่รับค่าคุณสมบัติของวัตถุและทำหน้าที่เป็นตัวเข้าถึง ส่วน Setter มีหน้าที่แก้ไขค่าของคุณสมบัติในวัตถุและทำหน้าที่เป็นตัวปรับเปลี่ยนค่าของคุณสมบัตินั้น


  # *ข้อดีของการใช้ Getter&Setter*
  - สามารถตรวจสอบการส่งข้อมูลก่อนจะทำการอ่านหรือเขียนข้อมูล
  - จำกัดการอ่านและเขียนข้อมูลได้ทำให้ข้อมูลปลอดภัยมากยิ่งขึ้น
  - สามารถทำให้โค้ดเป็นแบบ Read-Only หรือ Write-Only
  - สามารถสั่งให้ทำ action บางอย่างก่อนที่จะอ่านหรือเขียนข้อมูล เช่น การคำนวณก่อนบันทึกข้อมูล
  

  ## *Content*
  - [Syntax](#syntax)
  - [Example 1 : Basic Getter & Setter](#example-1-basic-getter-and-setter-in-dart)
  - [Example 2 : Read-Only and Write-Only Property](#example-2-read-only-and-write-only-property-in-dart)
  - [Example 3 : Computed Property using Getter](example-3-computed-property-using-getter-in-dart)
  - [Example 4 : Getter and Setter with Validation](example-4-getter-and-setter-with-validation-in-dart)

  ## *Comparison with Other Language*
  * [Syntax](#syntax)
  * [Example](#example)
  * [Summary](#summary)
  

## *Syntax*
เราสามารถเขียน Syntax ของ Getter ได้ดังนี้
```dart
return_type get property_name{
  //Getter body
}
```
เราสามารถเขียนการเรียกใช้ Getter ให้กระชับยิ่งขึ้นโดยใช้เครื่องหมาย arrow syntax

```dart
return_type get property_name => value;
```
ส่วน Syntax ของ Setter สามารถเขียนได้ดังนี้
```dart
set property_name (value) {
  // Setter body
}
```
เช่นเดียวกันกับ Getter เราสามารถทำให้โค้ดเราสั้นขึ้นโดยใช้ arrow syntax
```dart
set property_name(value_type value) => this.private_property = value;
```

## *Example 1* Basic Getter and Setter in Dart
ในตัวอย่างต่อไปนี้จะแสดงถึงการเรียกใช้ Getter&Setter โดยทั่วไป
```dart
class Person {
  String _name = '';

  String get name => _name;

  set name(String value) {
    if (value.isNotEmpty) {
      _name = value;
    }
  }
}

void main() {
  var person = Person();
  person.name = 'John'; // Using the setter
  print(person.name);   // Using the getter
}
```
ในกรณีนี้เราจะสามารถรับค่าและเปลี่ยนค่าตัวแปรที่เป็น private ได้
## Basic Getter and Setter in Other Language

## *Example 2* Read Only and Write Only Property

ในตัวอย่างต่อไปนี้จะแสดงถึงการเขียนโค้ดแบบ Read-Only
```dart
class Person {
  String _name;

  Person(this._name);

  // Read-Only property
  String get name => _name;
}

void main() {
  var person = Person('Japon');

  // Accessing read-only property
  print('Name: ${person.name}');
}
```
ในกรณีนี้เราไม่สามารถเปลี่ยนข้อมูลในคลาส Person ได้เนื่องจากไม่มีการเขียน Setter ในนั้นทำให้สามารถอ่านข้อมูลได้อย่างเดียว

ต่อไปเราจะมาพูดถึงการเขียนโค้ดแบบ Write-Only ซึ่งตรงข้ามกันกับกรณีด้านบน
```dart
class WriteOnlyProperty {
  String _secretValue;

  WriteOnlyProperty(this._secretValue);

  // Write-Only property
  void set _secret(String newValue) {
    _secretValue = newValue;
  }
  void setSecret(String newValue) {
  //Write-Only property
    _secret = newValue;
  }
}

void main() {
  var example = WriteOnlyProperty('initialSecret');
  example.setSecret('newSecret');
}
```
จากโค้ดนี้คือเราสามารถเปลี่ยนแปลงค่าที่เป็น Private property ได้แต่จะไม่สามารถอ่านค่าได้ว่าข้อมูลนั้นมีค่าเท่าไร

## *Example 3* Computed Property using Getter
ในตัวอย่างต่อไปนี้แสดงถึงการคำนวณก่อนจะทำการบันทึกข้อมูล
```dart
class Rectangle {
  double _length;
  double _width;

  Rectangle(this._length, this._width);

  double get area => _length * _width; // Computed property using getter
}

void main() {
  var myRectangle = Rectangle(5.0, 3.0);
  print('Area: ${myRectangle.area}');
}
```
จะเห็นได้ว่า Getter ได้ทำการคำนวณหาค่า Area ก่อนที่จะคืนค่ามาให้
## *Example 4* Getter and Setter with Validation
ในตัวอย่างนี้จะเป็นการตรวจสอบความถูกต้องของข้อมูลก่อนจะทำการบันทึกค่านั้นลงไป
```dart
class Student {
  String _name;
  int _age;

  Student(this._name, this._age);

  String get name => _name;
  int get age => _age;

  set age(int newAge) {
    if (newAge >= 0 && newAge <= 100) {
      _age = newAge;
    } else {
      print('Invalid Age');
    }
  }
}

void main() {
  var student = Student('Son', 20);
  print('Name: ${student.name}');
  student.age = -10; 
}
```
เราจะเห็นว่าหากอายุของนักเรียนติดลบหรือมากกว่า 100 ปีตัว Setter จะไม่ทำการบันทึกอายุลงไปแต่จะแจ้งผู้ใช้ว่ามีการใส่อายุผิด

## Comparison with Other Language
## Example
## Summary
## Reference
https://www.researchgate.net/publication/339143252_JAVA_and_DART_programming_languages_conceptual_comparison
https://www.researchgate.net/publication/358661479_AN_INTERPRETATION_OF_DART_PROGRAMMING_LANGUAGE
https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/?ref=lbp
https://dart-tutorial.com/object-oriented-programming/getter-and-setter-in-dart/
https://www.darttutorial.org/dart-tutorial/dart-getter-setter/
https://www.w3schools.com/cpp/cpp_encapsulation.asp
