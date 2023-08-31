# Parameterized Constructor in Dart
**Parameterized Constructor** เป็น **constructor** ที่มีการกำหนด **parameters** และ ค่าที่รับมาจะถูกส่งไปใน **constructor** ขณะที่กำลังมีการสร้าง **object** อาจเพื่อใช้กำหนดค่าให้  **instance variables** หรือ **ตัวแปร** ของ **Class**

## Syntax
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(this.number, this.name);
    }
```
หรือจะเขียนแบบนี้ก็ได้
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(int number, String name){
	      this.number = number;
	      this.name = name;
      }
    }
```
### Example 1: Parameterized Constructor In Dart
ในตัวอย่างที่ 1 มี **Class Student** ที่มี ตัวแปร 3 ตัว คือ **name** , **age** และ **rollNumber**
ใน **Class Student** มี **constructor** ตัวเดียว ที่มีการรับ **parameters** มากำหนดค่าให้**ตัวแปร**ใน class ทั้ง 3 ตัว
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
      // Constructor
      Student(this.name, this.age, this.rollNumber);
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student("John", 20, 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
ในภาษา **Dart** สามารถกำหนดค่าตัวแปรของ **Class** ใน **parameters** ของ **constructor** ได้เลย โดยใช้ ***this*.*ชื่อตัวแปร*** ของ **Class** เช่นในตัวอย่าง ***this*.*name*** 

> Output
> 
```dart
    Name: John
    Age: 20
    Roll Number: 1
```
## 

### Example 2: Parameterized Constructor With Named Parameters In Dart
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      }**strong text**
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student(name: "John", age: 20, rollNumber: 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
ในตัวอย่างที่ 2 ใช้ **Class** เดียวกับตัวอย่างที่ 1 แต่มีการใช้ **name parameters** ใน **constructor**แทน สังเกตจากการใส่ **{ }** ครอบ **parameter**  ทำให้การสร้าง **object** ง่ายขึ้น เพราะ ไม่จำเป็นต้อง เรียง **argument** ที่จะส่งไปให้ตรงกับ **parameter** ของ **constructor** เช่น **constructor** ของ **Class Student** มี **parameters** เป็น **name** , **age** และ **rollNumber** ตามลำดับ
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      } 
    }
```
เราสามารถสร้าง **object** โดยส่ง **argument** ไม่ตรงกับ **parameters** ได้ เพระ มี **name parameters** คอยกำกับอยู่ เช่น
```dart
    void main(){
        Student student = Student(rollNumber: 1, age: 20, name: "John" );
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```

> Output
> 
```dart
	Name: John
	Age: 20
	Roll Number: 1
```
## 
### Example 3: Parameterized Constructor With Default Values In Dart
ในตัวอย่างที่ 3 มี **Class Student** ที่มี ตัวแปร 2 ตัว คือ **name** และ **age**
ใน **Class Student** มี **constructor** ตัวเดียวและมีการกำหนดค่าให้ตัว **parameters** เพื่อใช้กำหนดค่าให้ตัวแปรใน **Class**
จะสังเกตได้ว่าจะมีการใส่ **{ }** ครอบ **parameter** เหมือนตัวอย่างที่ 2 แต่จะมีการกำหนดค่าให้ **parameters**
```dart
    class Student {
      String? name;
      int? age;
    
      // Constructor
      Student({String? name = "John", int? age = 0}) {
        this.name = name;
        this.age = age;
      }
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student();
        print("Name: ${student.name}");
        print("Age: ${student.age}");
    }
```
จาก code จะมีการกำหนดค่าให้ **parameters** name = "John" และ age = 0
```dart
      Student({String? name = "John", int? age = 0}) {
        this.name = name;
        this.age = age;
      }
```
> Output
> 
```dart
	Name: John
	Age: 0
```

# Reference

 - https://dart-tutorial.com/object-oriented-programming/parameterized-constructor-in-dart/
 - https://dart.dev/language/constructors
