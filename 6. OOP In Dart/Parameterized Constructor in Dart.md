# Parameterized Constructor in Dart
**Parameterized Constructor** เป็น **constructor** ที่มีการกำหนด **parameters** และ ค่าที่รับมาจะถูกส่งไปใน **constructor** ขณะที่กำลังมีการสร้าง **object**

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
