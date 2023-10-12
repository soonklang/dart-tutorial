
# Class in Dart
ในการเขียนโปรแกรมเชิงวัตถุ Class จะเปรียบเสมือนกับ Blueprint หรือแบบแปลนสำหรับสร้าง Object (วัตถุ) ซึ่ง Class จะประกอบด้วย Properties (คุณลักษณะ) และ Method (กระบวนการ) โดย Class จะเป็นตัวกำหนด Properties และ Method ของ Object ยกตัวอย่างเช่น สร้าง Class ชื่อว่า **Dog (สุนัข)** ก็อาจจะมี Properties อย่างการ **Breed (พันธุ์)** , **Color (สี)** และ Method เป็น  **Bark (เห่า)** , **Run(วิ่ง)**
 

# Declaring Class In Dart
ในภาษา Dart สามารถสร้าง Class ได้โดยใช้ Keyword ว่า **class** ตามด้วย **ชื่อคลาส** และตามด้วย **{ }** โดยในการตั้งชื่อ class ควรตั้งชื่อโดยใช้รูปแบบ **PascalCase** อย่างเช่น **Employee**,  **Student**,  **QuizBrain**
>[!NOTE]
>PascalCase เป็นรูปแบบการตั้งชื่อที่จะขึ้นต้นคำด้วยตัวพิมพ์ใหญ่ทั้งหมด

# Syntax
```dart
class ClassName {
// properties or fields
// methods or functions
}
```
จาก Syntax ด้านบน
- **class** เป็น keyword ที่ใช้ในการสร้าง class
- **ClassName** เป็นชื่อของ class ที่ขึ้นต้นด้วยตัวอักษรพิมพ์ใหญ่
- ภายในตัว Class จะประกอบด้วย **properties** และ **functions**
- **Properties** ใช้ในการเก็บข้อมูล และมันยังมีชื่อเรียกอีกอย่างว่า **fields**  หรือ **attributes**
- **Functions** ใช้ในการปฏิบัติหรือทำงานต่างๆ และมันยังมีชื่อเรียกอีกอย่างว่า  **methods**

### ตัวอย่างที่ 1: Declaring A Class In Dart
ในตัวอย่างด้านล่างจะมี class **Animal** ที่ประกอบด้วย 3 properties คือ**name** ,**numberOfLegs** ,**lifeSpan** โดย class นี้จะมี method **display** ที่ใช้สำหรับพิมพ์ค่าของ properties  
```dart
class Animal {
  String? name;
  int? numberOfLegs;
  int? lifeSpan;
  void display() {
    print("Animal name: $name.");
    print("Number of Legs: $numberOfLegs.");
    print("Life Span: $lifeSpan.");
  }
}
```
 
**โปรแกรมนี้จะยังไม่พิมพ์ค่าอะไรออกมา** เพราะยังไม่มีการสร้าง object ของ class ที่การเรียกใช้งาน method display

### ตัวอย่างที่ 2: Declaring A Person Class In Dart
จากตัวอย่างด้านล่างจะมี class **Person** มีที่ 4 properties คือ **name**,  **phone**,  **isMarried**, **age** และยังมี 1 method คือ **displayInfo** ที่ใช้สำหรับพิมพ์ค่าของ properties
```dart
class Person {
  String? name;
  String? phone;
  bool? isMarried;
  int? age;
  void displayInfo() {
    print("Person name: $name.");
    print("Phone number: $phone.");
    print("Married: $isMarried.");
    print("Age: $age.");
  }
}

```
### ตัวอย่างที่ 3: Declaring Area Class In Dart

จากตัวอย่างด้านล่าง class  **Area**  มี 2 properties คือ **length**  และ **breadth** และยังมี method **calculateArea** ที่ใช้สำหรับคำนวณพื้นที่ของสี่เหลี่ยมผืนผ้า


```dart
class Area {
  double? length;
  double? breadth;
  double calculateArea() {
    return length! * breadth!;
  }
}
```

### ตัวอย่างที่ 4: Declaring A Student Class In Dart

จากตัวอย่างด้านล่าง class   **Student**  ประกอบด้วย 3   properties คือ **name**,  **age**, **grade** และยังมี method **displayInfo** ที่ใช้สำหรับพิมพ์ค่าของ properties
```dart
class Student {
  String? name;
  int? age;
  int? grade;

  void displayInfo() {
    print("Student name: $name.");
    print("Student age: $age.");
    print("Student grade: $grade.");
  }
}
```
# Key Points

-   สามารถประกาศ class โดยใช้ keyword ว่า **class**
-   class คือ blueprint สำหรับสร้าง object ใดๆ
-   ภายในคลาสจะประกอบด้วย properties และ methods.
-   properties เรียกอีกอย่างว่า fields, attributes หรือ data members.
-   methods เรียกอีกอย่างว่า behaviors หรือ member functions.

# Challenge
สร้าง class book โดยมี 3 properties คือ name, author และ prize และสร้าง method display ที่จะแสดงค่าของทั้ง 3 properties
 ```dart
class Book {
  String? name;
  String? author;
  int? prize;
  void display() {
    print("Name: $name");
    print("Author: $author");
    print("Prize: $prize");
  }
}
```
# Difference Between Dart and Java and Python and C
จากตัวอย่างด้านล่างจะเป็นการสร้าง class ของแต่ละภาษา โดย class ชื่อ **Car** จะมี properties คือ **engine** และมี method **disp** สำหรับแสดงค่าของ properties
### Python
```python
class Car:  
    #field or properties
    engine = "E1001";  
    #function or method
    def disp(self): 
      print(self.engine); 
      
```
 
### Java
```java
class Car {  
   // field or properties
   String engine = "E1001";  
   // function or method
   void disp() { 
      System.out.println(engine); 
   } 
}
```

### Dart
```dart
class Car {  
   // field or properties
   String engine = "E1001";     
   // function or method
   void disp() { 
      print(engine); 
   } 
}
```
จากตัวอย่างด้านบน class ของภาษา Dart จะใกล้เคียงกับของภาษา Java แต่จะแตกต่างกับภาษา Python ตรงที่ dart จะใช้ **{ }** ด้านหลังชื่อของ class แต่ python จะใช้ **:** แทน

### C
เนื่องจาก C เป็นภาษา Procedural Programming ไม่ใช่ Object Oriented Programming (OOP) จึงไม่สามารถสร้าง class ได้

 

 

# Reference
https://www.theserverside.com/definition/Pascal-case<br>
https://www.tutorialspoint.com/dart_programming/dart_programming_classes.htm<br>
https://dart-tutorial.com/object-oriented-programming/class-in-dart/<br>


 
# Slides & Clip
https://youtu.be/JJe66ftuMK4<br>

[Slide.pdf](https://github.com/630710676/pl/blob/main/Class%20in%20Dart.pdf?raw=true)<br>
[Slide.pptx](https://github.com/630710676/pl/blob/main/Class%20in%20Dart.pptx?raw=true)<br>
[Slide_2.pdf](https://github.com/630710676/pl/blob/main/Class%20in%20Dart_.pdf?raw=true)<br>
[Slide_2.pdf](https://github.com/630710676/pl/blob/main/Class%20in%20Dart_.pdf)<br>
[Slide_2.pptx](https://github.com/630710676/pl/blob/main/Class%20in%20Dart_.pptx)<br>
