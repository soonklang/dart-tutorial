## ENCAPSULATION IN DART
---

# การห่อหุ้ม (Encapsulation) ใน Dart

การห่อหุ้มหรือ Encapsulation เป็นหนึ่งในแนวคิดสำคัญของการเขียนโปรแกรมแบบวัตถุ (Object-Oriented Programming). ใน Dart, การห่อหุ้มหมายถึงการปกปิดข้อมูลภายในไลบรารี (library) ทำให้ไม่สามารถเข้าถึงจากภายนอกได้ ซึ่งจะช่วยในการควบคุมโปรแกรมของคุณและป้องกันไม่ให้มีความซับซ้อนเกินไป.

## ไลบรารี (Library) คืออะไรใน Dart?

โดยค่าเริ่มต้น, ทุกไฟล์ .dart จะเป็นไลบรารี ซึ่งไลบรารีคือการรวมกันของฟังก์ชันและคลาส และเราสามารถนำไลบรารีหนึ่งมาใช้ในไลบรารีอื่นได้โดยใช้คำสั่ง import.

## การห่อหุ้มใน Dart และความเป็นส่วนตัว

Dart ไม่รองรับคีย์เวิร์ดเฉพาะเช่น public, private, และ protected. แต่ Dart ใช้ _ (underscore) เพื่อทำให้คุณสมบัติหรือเมธอดเป็นแบบส่วนตัว (private). ความสำคัญคือการห่อหุ้มใน Dart จะเกิดขึ้นในระดับไลบรารี (library level) ไม่ใช่ในระดับคลาส (class level).


ขออภัยที่ทำให้คุณสับสนครับ นี่คือการจัดเรียงเนื้อหาในรูปแบบ Markdown ที่คุณสามารถคัดลอกไปวางใน GitHub ได้เลย:

```markdown
## ตัวอย่างการใช้งาน Encapsulation ใน Dart

```dart
class Employee {
  int? _id;
  String? _name;

  int getId() {
    return _id!;
  }

  String getName() {
    return _name!;
  }

  void setId(int id) {
    this._id = id;
  }

  void setName(String name) {
    this._name = name;
  }
}

void main() {
  Employee emp = new Employee();
  emp.setId(1);
  emp.setName("John");

  print("Id: ${emp.getId()}");
  print("Name: ${emp.getName()}");
}
```

**ผลลัพธ์:**
```
Id: 1
Name: John
```

## คุณสมบัติส่วนตัว (Private Properties) ใน Dart

คุณสมบัติส่วนตัวคือคุณสมบัติที่สามารถเข้าถึงได้เฉพาะจากไลบรารีเดียวกันเท่านั้น ใน Dart ไม่มีคำสำคัญเฉพาะเจาะจงเพื่อกำหนดคุณสมบัติเป็นส่วนตัว แต่เราสามารถกำหนดให้คุณสมบัติเป็นส่วนตัวได้โดยการเติมขีดล่าง (_) นำหน้าชื่อคุณสมบัติ

**ตัวอย่าง:**

```dart
class Student {
  final _schoolname = "ABC School";

  String getSchoolName() {
    return _schoolname;
  }
}

void main() {
  var student = Student();
  print(student.getSchoolName());
  // การทำแบบนี้ไม่เป็นไปได้
  //student._schoolname = "XYZ School";
}
```

**ผลลัพธ์:**
```
ABC School
```

## วิธีการสร้างเมธอด Getter และ Setter

คุณสามารถสร้างเมธอด getter และ setter ได้โดยใช้คำว่า `get` และ `set` ในตัวอย่างด้านล่าง เราได้สร้างคลาสชื่อ Vehicle ซึ่งมีคุณสมบัติส่วนตัว 2 ตัวคือ _model และ _year และเรายังสร้างเมธอด getter และ setter สำหรับแต่ละคุณสมบัติ

```dart
class Vehicle {
  String _model;
  int _year;

  // เมธอด Getter
  String get model => _model;

  // เมธอด Setter
  set model(String model) => _model = model;

  // เมธอด Getter
  int get year => _year;

  // เมธอด Setter
  set year(int year) => _year = year;
}

void main() {
  var vehicle = Vehicle();
  vehicle.model = "Toyota";
  vehicle.year = 2019;
  print(vehicle.model);
  print(vehicle.year);
}
```

**ผลลัพธ์:**
```
Toyota
2019
```

## ทำไมการห่อหุ้มข้อมูล (Encapsulation) ถึงสำคัญ?

- **การซ่อนข้อมูล (Data Hiding):** การห่อหุ้มข้อมูลช่วยซ่อนข้อมูลจากโลกภายนอก มันป้องกันไม่ให้ข้อมูลถูกเข้าถึงโดยโค้ดภายนอกคลาส
- **การทดสอบ (Testability):** การห่อหุ้มข้อมูลช่วยให้คุณทดสอบคลาสโดยแยกต่างหาก ทำให้คุณสามารถทดสอบคลาสโดยไม่ต้องทดสอบโค้ดภายนอกคลาส
- **ความยืดหยุ่น (Flexibility):** การห่อหุ้มข้อมูลช่วยให้คุณเปลี่ยนแปลงการดำเนินการของคลาสโดยไม่กระทบกับโค้ดภายนอกคลาส
- **ความปลอดภัย (Security):** การห่อหุ้มข้อมูลช่วยให


