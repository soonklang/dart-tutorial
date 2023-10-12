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
  - [Syntax in Dart](#syntax-in-dart)
  - [Example 1 : Basic Getter & Setter](#example-1-basic-getter-and-setter-in-dart)
  - [Example 2 : Read-Only and Write-Only Property](#example-2-read-only-and-write-only-property-in-dart)
  - [Example 3 : Computed Property using Getter](#example-3-computed-property-using-getter-in-dart)
  - [Example 4 : Getter and Setter with Validation](#example-4-getter-and-setter-with-validation-in-dart)
  - [Presentation Slide](#slide)
  - [Explanation Video](#explanation-video)

  ## *Comparison with Other Language*
  * [Syntax for Other Languages](#syntax-for-other-languages)
  * [Example](#example)
  * [Summary](#summary)
  * [Dart VS Java](#dart-vs-java)
  

## *Syntax in Dart*
เราสามารถเขียน Syntax ของ Getter ใน Dart ได้ดังนี้
```dart
return_type get property_name{
  //Getter body
}
```
เราสามารถเขียนการเรียกใช้ Getter ให้กระชับยิ่งขึ้นโดยใช้เครื่องหมาย arrow syntax

```dart
return_type get property_name => value;
```
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

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
  person.name = 'Ham'; // Using the setter
  print(person.name);   // Using the getter
}
```
ในกรณีนี้เราจะสามารถรับค่าและเปลี่ยนค่าตัวแปรที่เป็น private ได้
## *Example 2* Read Only and Write Only Property in Dart

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

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

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

## *Example 3* Computed Property using Getter in Dart
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
## *Example 4* Getter and Setter with Validation in Dart
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

# Syntax for Other Languages
* C++
  ```C++
      // Setter body
      void setPropertyName(type v) {
        value = v;
     }
      // Getter body
      return_type getPropertyName() {
        return value;
      }
  ```
ในภาษา C++ จะใช้ method get กับ set ที่เป็น public ในการเข้าถึงข้อมูลที่ Encapsulation อยู่ซึ่งจะเป็นการเก็บข้อมูลที่สำคัญไม่ให้ผู้ใช้สามารถแก้ไขได้และจะตั้งให้ตัวแปรนั้นเป็น private

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

* java
```java
  // Getter  body
  public return_type getPropertyName() {
    return value;
  }

  // Setter body
  public void setPropertyName(type v) {
    this.value = v;
  }
```
เช่นเดียวกับภาษา C++ การเข้าถึงข้อมูลที่เป็น Private จะใช้ method get และ set ที่เป็น Public ในการเข้าถึง Private property
ส่วนใหญ่จะนิยมเขียนกันในรูปแบบ get ตามด้วยชื่อของ property นั้นๆ

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

* Python
  ```Python
  class Employee:
    def __init__(self):
        self._salary = 0  # Private attribute with an underscore prefix

    # Getter method
    @property
    def salary(self):
        return self._salary

    # Setter method
    @salary.setter
    def salary(self, value):
        if value >= 0:
            self._salary = value
  ```
Python จะมี Syntax ที่แตกต่างกับภาษาอื่นโดยจะมีการอธิบายอย่างละเอียดในตัวอย่างด้านล่าง

  
## Example
* C++
```C++
#include <iostream>
  using namespace std;

  class bankAccount {
    private:
      int balance;

  public:
    // Setter body
    void setBalance(int m) {
      balance = m;
   }
      // Getter body
      int getBalance() {
        return balance;
      }
  };
```
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

* Java
```java
public class menu {
  private String food;

  // Getter
  public String getFood() {
    return food;
  }
  // Setter
  public void setName(String newFood) {
    this.food = newFood;
  }
}
```
จะเห็นได้ว่า C++,Java,Dart มีการใช้ Getter และ Setter ที่ค่อนข้างคล้ายกันเนื่องจากภาษาข้างต้นนี้มีการออกแบบ Syntax ให้มีลักษณะคล้ายภาษา C
แต่การใช้ Getter&Setter ใน Python จะมีลักษณะที่ต่างออกไป

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

* Python
  
ใน Python จะมีการใช้ Getter&Setter อยู่ 2 วิธีคือใช้ property() function หรือ @property decorator
  
1. ตัวอย่างการใช้ property()
  ```Python
  class MyClass:
    def __init__(self):
        self._my_variable = None  # Private attribute with an underscore prefix

    # Getter method
    def get_my_variable(self):
        return self._my_variable

    # Setter method
    def set_my_variable(self, value):
        self._my_variable = value

    # Create a computed property
    my_variable = property(get_my_variable, set_my_variable)

     # Create an instance of MyClass
     obj = MyClass()

     # Use the computed property
     obj.my_variable = 42
     print(obj.my_variable)  # Output: 42

  ```
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

2. ตัวอย่างการใช้ decorator
  ```Python
    # Getter method
    @property
    def my_variable(self):
        return self._my_variable

    # Setter method
    @my_variable.setter
    def my_variable(self, value):
        # Add process here for validation
        self._my_variable = value

  ```
จากที่เห็นว่าการเขียนแบบ decorator จะอ่านง่ายและเข้าใจง่ายมากกว่าการใช้ property()
และการส่วนใหญ่จะนิยมการเขียนแบบ Decorator มากกว่าเพราะเป็นการเขียนตามสไตล์ภาษา Python (Pythonic way)
## Dart VS Java
หลังจากได้เห็นการเปรียบเทียบกันในแต่ละภาษาแล้ว บางคนอาจเกิดคำถามว่าทั้ง Dart และ Java ต่างก็เป็นภาษาที่รองรับ OO
และมี Syntax ที่คล้ายกับ C base Language ทั้งคู่
แล้วแบบนี้เราควรเลือกใช้ภาษาไหน ?

Dart จะเน้นไปทางการเขียนซอฟต์แวร์เว็บที่มีการปฏิสัมพันธ์ (Interactive Web Software) อีกทั้งยังนิยมในการเขียน Mobile หรือ Web application
โดย Dart จะแยก interface(Abstact class) ออกจาก implementation(Concrete class) เพื่อการจัดการโค้ดให้เป็นระเบียบ
และสามารถนำโค้ดกลับมาใช้ใหม่ได้ทั้ง client และ server
ในเดือนพฤษภาคม ปี 2021 มี Programmer มากกว่า 80,000 คนได้โหวตว่าพวกเขาชอบภาษา Dart ในการเขียน scripting , programming และ markup language


ในทางกลับกัน Java จะสามารถประยุกต์ใช้ได้ในหลายสถานการณ์มากกว่า เนื่องจาก Java มี Package Scope ซึ่งจะทำให้สามารถเรียกใช้ class ของ Package 
เดียวกันได้ทุกเมื่อหากไม่มีการปิดกั้นการเข้าถึง เรื่องนี้จะทำให้ Javaเป็นภาษาที่มีความยืดหยุ่นมากกว่า Dart มาก แต่จะมีข้อจำกัดในการนำโค้ดกลับมาใช้ใหม่
และยากต่อการบำรุงรักษาหากโค้ดถูกจัดเรียงไม่เป็นระเบียบหรือมีขนาดใหญ่

อย่างไรก็ตามทั้ง Dart และ Java ต่างก็เป็นภาษาที่ Programmer ชื่นชอบเพราะเป็นภาษาที่เข้าใจง่ายและใช้ได้ในหลายสถานการณ์

## Summary
Getter กับ Setter ในภาษา C++,Java และ Dart มีหน้าที่หลักคือเป็นตัวที่ใช้เข้าถึงข้อมูลส่วนที่ไม่ต้องการให้มีการดัดแปลง (ทั้งตัวเราหรือโดยคนอื่น) โดยจะจำกัดการเข้าถึง
ได้ด้วยการเขียนโค้ดในลักษณะต่างๆทำให้โค้ดปลอดภัยมีความน่าเชื่อถือ และเราสามารถนำคุณสมบัติที่ว่านี้ไปประยุกต์ใช้ได้กับหลายๆวิธีเช่น[ตัวอย่าง](#content)ข้างบนที่กล่าวมา
แต่ในภาษาอย่าง Python จะเน้นการใช้ประโยชน์ในด้านการตรวจสอบข้อมูลหรือคำนวณมากกว่าเนื่องจาก Private variable ใน Python ไม่ได้ถูกซ่อนเหมือนภาษาที่มีการใช้ 
OOP ภาษาอื่นๆ
## Slide
https://drive.google.com/drive/u/1/folders/1jKhdf0IGkxSQjPQKGSU3jyJa10NxLxrv

## Explanation Video
[https://www.youtube.com/watch?v=D5VMcAhDiNI](https://youtu.be/D5VMcAhDiNI?si=ZqusDjiv2xVcgNv8)

## Reference
https://www.researchgate.net/publication/339143252_JAVA_and_DART_programming_languages_conceptual_comparison

https://www.researchgate.net/publication/358661479_AN_INTERPRETATION_OF_DART_PROGRAMMING_LANGUAGE

https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/?ref=lbp

https://www.geeksforgeeks.org/getter-and-setter-in-python/

https://dart-tutorial.com/object-oriented-programming/getter-and-setter-in-dart/

https://www.darttutorial.org/dart-tutorial/dart-getter-setter/

https://www.w3schools.com/cpp/cpp_encapsulation.asp

https://www.w3schools.com/java/java_encapsulation.asp

https://www.geeksforgeeks.org/getter-and-setter-in-python/
