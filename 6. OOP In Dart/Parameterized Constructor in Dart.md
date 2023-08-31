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

> Show Output
> 
```dart
    Name: John
    Age: 20
    Roll Number: 1
```
