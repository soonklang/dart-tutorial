
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

### ตัวอย่างที่ 1
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
จากตัวอย่างด้านล่างจะมี class **Person** มีที่ 4 properties คือ **name**,  **phone**,  **isMarried**, **age** และยังมี 1 method คือ **displayInfo** ที่ใช้สำหรับพิมพ์ค่าของ properties ทั้ง 4
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

จากตัวอย่างด้านล่าง class  **Area**  มี 2 properties คือ **length**  และ** breadth** และยังมี method **calculateArea** ที่ใช้สำหรับคำนวณพื้รที่ของสี่เหลี่ยมผืนผ้า

```dart
class Area {
  double? length;
  double? breadth;

  double calculateArea() {
    return length! * breadth!;
  }
}
```


### Key Points

-   สามารถประกาศ class โดยใช้ keyword ว่า **class**
-   class คือ blueprint สำหรับสร้าง object ใดๆ
-   ภายในคลาสจะประกอบด้วย properties และ methods.
-   properties เรียกอีกอย่างว่า fields, attributes หรือ data members.
-   methods เรียกอีกอย่างว่า behaviors หรือ member functions.
