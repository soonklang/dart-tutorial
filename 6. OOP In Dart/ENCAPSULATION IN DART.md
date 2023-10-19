# ENCAPSULATION IN DART
---

## การห่อหุ้ม (Encapsulation) ใน Dart

การห่อหุ้มหรือ Encapsulation เป็นหนึ่งในแนวคิดสำคัญของการเขียนโปรแกรมแบบวัตถุ (Object-Oriented Programming). ใน Dart, การห่อหุ้มหมายถึงการปกปิดข้อมูลภายในไลบรารี (library) ทำให้ไม่สามารถเข้าถึงจากภายนอกได้ ซึ่งจะช่วยในการควบคุมโปรแกรมของคุณและป้องกันไม่ให้มีความซับซ้อนเกินไป.


## ไลบรารี (Library) คืออะไรใน Dart?

โดยค่าเริ่มต้น, ทุกไฟล์ .dart จะเป็นไลบรารี ซึ่งไลบรารีคือการรวมกันของฟังก์ชันและคลาส และเราสามารถนำไลบรารีหนึ่งมาใช้ในไลบรารีอื่นได้โดยใช้คำสั่ง import.


## การห่อหุ้มใน Dart และความเป็นส่วนตัว

Dart ไม่รองรับคีย์เวิร์ดเฉพาะเช่น public, private, และ protected. แต่ Dart ใช้ _ (underscore) เพื่อทำให้คุณสมบัติหรือเมธอดเป็นแบบส่วนตัว (private). ความสำคัญคือการห่อหุ้มใน Dart จะเกิดขึ้นในระดับไลบรารี (library level) ไม่ใช่ในระดับคลาส (class level).



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
---

## Private Properties ใน Dart

คุณสมบัติส่วนตัวคือคุณสมบัติที่สามารถเข้าถึงได้เฉพาะจากไลบรารีเดียวกันเท่านั้น ใน Dart ไม่มีคำสำคัญเฉพาะเจาะจงเพื่อกำหนดคุณสมบัติเป็นส่วนตัว แต่เราสามารถกำหนดให้คุณสมบัติเป็นส่วนตัวได้โดยการเติมขีดล่าง (_) นำหน้าชื่อคุณสมบัติ

### สรุป Private Properties ใน Dart:

Properties ที่เริ่มต้นด้วยขีดล่าง (_) ใน Dart ถือว่าเป็น "private" หรือ "ส่วนตัว". นั่นหมายความว่า properties นั้นสามารถเข้าถึงได้เฉพาะภายในไลบรารี (library) ที่ประกาศ properties นั้น, แต่ไม่สามารถเข้าถึงจากไลบรารีอื่นได้.

---

## Read-only Properties

คุณสามารถควบคุมการเข้าถึง properties และประยุกต์ใช้การห่อหุ้มข้อมูล (encapsulation) ใน Dart ได้โดยใช้ properties แบบอ่านเท่านั้น คุณสามารถทำได้โดยการเติมคำว่า `final` นำหน้าการประกาศ properties ดังนั้นคุณสามารถเข้าถึงค่าของมันได้เท่านั้น แต่ไม่สามารถเปลี่ยนแปลงค่าได้

> **ข้อมูลเพิ่มเติม:**  
> properties ที่ประกาศด้วยคำว่า `final` ต้องถูกกำหนดค่าเริ่มต้นในขณะที่ประกาศ หรือคุณสามารถกำหนดค่าเริ่มต้นใน constructor ได้

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
> **ข้อมูลเพิ่มเติม:**  
> คุณสามารถกำหนด getter และ setter โดยใช้คำว่า `get` และ `set` ดูตัวอย่างเพิ่มเติมด้านล่าง

### สรุป Read-only Properties ใน Dart:
Properties แบบอ่านเท่านั้น (Read-only properties) ใน Dart ช่วยให้คุณป้องกันไม่ให้ properties นั้นถูกแก้ไขหลังจากที่ถูกกำหนดค่าเริ่มต้นแล้ว. การประกาศ properties ด้วยคำว่า `final` จะทำให้คุณสามารถกำหนดค่าให้กับ properties นั้นได้เพียงครั้งเดียวเท่านั้น - ไม่ว่าจะเป็นในขณะประกาศหรือผ่าน constructor.

**ข้อดีของการใช้ Read-only Properties**:
1. **ความปลอดภัย**: ป้องกันไม่ให้ properties ถูกแก้ไขโดยไม่ได้ตั้งใจ, ซึ่งสามารถนำไปสู่ข้อผิดพลาดในโปรแกรม.
2. **ความชัดเจน**: เมื่อเห็นคำว่า `final`, นักพัฒนาสามารถรู้ได้ทันทีว่า properties นั้นไม่สามารถถูกแก้ไขหลังจากที่ถูกกำหนดค่าเริ่มต้นแล้ว.


> **ข้อมูลเพิ่มเติม:** 
> ตัวอย่าง, ในคลาส `Student` ข้างต้น, `_schoolname` เป็น properties แบบอ่านเท่านั้น เนื่องจากมันถูกประกาศด้วย `final`. ดังนั้น, คุณสามารถเข้าถึงค่าของมันผ่าน `getSchoolName()` แต่คุณไม่สามารถกำหนดค่าใหม่ให้กับ `_schoolname` ได้.

---

## วิธีการสร้างเมธอด Getter และ Setter

คุณสามารถสร้างเมธอด getter และ setter ได้โดยใช้คำว่า `get` และ `set` ในตัวอย่างด้านล่าง เราได้สร้างคลาสชื่อ Vehicle ซึ่งมี properties ส่วนตัว 2 ตัวคือ _model และ _year และเรายังสร้างเมธอด getter และ setter สำหรับแต่ละ properties

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

### สรุป การสร้างเมธอด Getter และ Setter ใน Dart:

ใน Dart, getter และ setter ใช้สำหรับการเข้าถึงและการกำหนดค่าให้กับ properties ของคลาส โดยทั่วไปเราจะใช้ getter และ setter เมื่อเราต้องการจัดการกับข้อมูลก่อนที่จะเข้าถึงหรือก่อนที่จะกำหนดค่าให้กับ properties นั้นๆ

1. **Getter**: เป็นเมธอดที่ใช้สำหรับการเข้าถึงค่าของ properties ไม่ต้องการพารามิเตอร์ และคืนค่าของ properties นั้นๆ ในตัวอย่างข้างต้น, `String get model => _model;` เป็น getter สำหรับ properties `_model`.

2. **Setter**: เป็นเมธอดที่ใช้สำหรับการกำหนดค่าให้กับ properties ต้องการพารามิเตอร์ 1 ตัว และไม่คืนค่าใดๆ ในตัวอย่างข้างต้น, `set model(String model) => _model = model;` เป็น setter สำหรับ properties `_model`.


## การเปรียบเทียบการสร้างเมธอด Getter และ Setter ใน Dart และ Java:

**Dart**:
```dart
class Student {
  String _name; // private property

  Student(this._name);

  // Getter
  String get name => _name;

  // Setter
  set name(String newName) => _name = newName;
}

void main() {
  var student = Student("John");
  print(student.name); // John
  student.name = "Doe";
  print(student.name); // Doe
}
```

**Java**:
```java
public class Student {
    private String name; // private property

    public Student(String name) {
        this.name = name;
    }

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String newName) {
        this.name = newName;
    }

    public static void main(String[] args) {
        Student student = new Student("John");
        System.out.println(student.getName()); // John
        student.setName("Doe");
        System.out.println(student.getName()); // Doe
    }
}
```


1. **การประกาศ properties ส่วนตัว**: ใน Dart, คุณใช้ขีดล่าง (_) นำหน้าชื่อ properties เพื่อทำให้มันเป็น private. ใน Java, คุณใช้คำว่า `private` นำหน้าการประกาศ properties.
2. **Getter และ Setter**: ใน Dart, คุณสามารถใช้คำว่า `get` และ `set` สำหรับการสร้าง getter และ setter. ใน Java, คุณต้องสร้างเมธอด `getName()` และ `setName()` แบบปกติ.


---

## ตัวอย่างการใช้งาน Encapsulation ด้วยการกำหนด Constructor

ใน Dart, คุณสามารถใช้ constructor เพื่อกำหนดค่าเริ่มต้นให้กับคุณสมบัติส่วนตัว:

```dart
class Person {
  String _name;
  int _age;

  Person(this._name, this._age);

  String get personInfo => 'Name: $_name, Age: $_age';
}

void main() {
  var person = Person('Alice', 30);
  print(person.personInfo);
}
```

**ผลลัพธ์:**

```
Name: Alice, Age: 30
```

> **ข้อมูลเพิ่มเติม:**  
> การห่อหุ้มใน Dart ช่วยในการปกปิดข้อมูลและป้องกันไม่ให้ข้อมูลถูกเข้าถึงหรือแก้ไขโดยโค้ดภายนอกคลาส ซึ่งเป็นหนึ่งในแนวคิดสำคัญของการเขียนโปรแกรมแบบวัตถุ.

---

## ทำไมการห่อหุ้มข้อมูล (Encapsulation) ถึงสำคัญ?


- **การซ่อนข้อมูล (Data Hiding):** การห่อหุ้มข้อมูลช่วยซ่อนข้อมูลจากโลกภายนอก มันป้องกันไม่ให้ข้อมูลถูกเข้าถึงโดยโค้ดภายนอกคลาส
- **การทดสอบ (Testability):** การห่อหุ้มข้อมูลช่วยให้คุณทดสอบคลาสโดยแยกต่างหาก ทำให้คุณสามารถทดสอบคลาสโดยไม่ต้องทดสอบโค้ดภายนอกคลาส
- **ความยืดหยุ่น (Flexibility):** การห่อหุ้มข้อมูลช่วยให้คุณเปลี่ยนแปลงการดำเนินการของคลาสโดยไม่กระทบกับโค้ดภายนอกคลาส
- **ความปลอดภัย (Security):** การห่อหุ้มข้อมูลช่วยให้คุณจำกัดการเข้าถึงสมาชิกของคลาส ทำให้คุณสามารถจำกัดการเข้าถึงข้อมูลที่สำคัญได้
- **ป้องกันการเข้าถึงไม่คาดคิด:** ช่วยในการปกปิดข้อมูลภายในคลาสหรือไลบรารี ป้องกันการเข้าถึงหรือแก้ไขข้อมูลจากภายนอกที่ไม่คาดคิด.

## สรุป Encapsulation ใน Dart !!
การห่อหุ้มใน Dart ช่วยในการป้องกันการเข้าถึงแบบไม่คาดคิด ให้ความสามารถในการจัดการข้อมูลและสถานะภายในคลาสอย่างมีประสิทธิภาพ เพิ่มความยืดหยุ่นโดยไม่กระทบกับโค้ดภายนอกคลาสและป้องกันการเข้าถึงหรือแก้ไขข้อมูลจากภายนอกได้ โดยใช้ฟีเจอร์ต่างๆ ของภาษา เพื่อให้แน่ใจว่าโค้ดของคุณมีความปลอดภัยและทำงานได้อย่างถูกต้อง ซึ่งเป็นหนึ่งในแนวคิดสำคัญของการเขียนโปรแกรมแบบ OOP.

---
# Reference
- https://dart-tutorial.com/object-oriented-programming/

## Video
- https://youtu.be/5siEPvu0KWs
## Slide  ver.1
- [ENCAPSULATION.IN.DART.pdf](https://github.com/soonklang/dart-tutorial/files/12882177/ENCAPSULATION.IN.DART.pdf)

## Slide  ver.2
- [ENCAPSULATION IN DART-640710062.pdf](https://github.com/soonklang/dart-tutorial/files/12880636/ENCAPSULATION.IN.DART-640710062.pdf)

640710062 เมธิสศรต์ ปล้องเจริญ

