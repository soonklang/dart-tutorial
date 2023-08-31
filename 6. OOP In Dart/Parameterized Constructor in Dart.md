# Parameterized Constructor in Dart
**Parameterized Constructor** เป็น **constructor** ที่มีการกำหนด **parameters** และ ค่าที่รับมาจะถูกส่งไปใน **constructor** ขณะที่กำลังมีการสร้าง **object** อาจเพื่อใช้กำหนดค่าให้  **Instance Variables** ของ **Class**

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
หรือจะเขียนกำหนดค่าให้ **Instance Variables** แบบนี้ก็ได้
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
