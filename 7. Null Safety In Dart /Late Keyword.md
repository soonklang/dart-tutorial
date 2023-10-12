### Late Keyword In Dart
ใน Dart คำว่า "late" ใช้ในการประกาศตัวแปรหรือฟิลด์ที่จะถูกกำหนดค่าในภายหลัง มันถูกใช้ในการประกาศตัวแปรที่ไม่สามารถเป็น null ได้และไม่ได้รับค่าเริ่มต้นในเวลาที่ประกาศ หรือสรุปง่ายๆก็คือ การประกาศตัวแปรก่อน(ไม่ต้องกำหนดค่า) แล้วค่อยมากำหนดค่าทีหลัง

### Syntax

```dart
late data_type variable_name;
```
### note for use Late Keyword
- อย่าเพิ่งกำหนดค่าให้กับตัวแปรนั้น
- ควรกำหนดค่าหลังจากกำหนดตัวแปร
- ก่อนจะใช้งานตัวแปร ต้องมันใจว่าตัวแปรได้ถูกกำหนดค่าเรียบร้อยเเล้ว

-----------------------

### Example 1: Late Keyword In Dart

ในตัวอย่างนี้ ตัวแปร **name** กำหนดด้วย **late keyword** เพื่อไปเรียกใช้งานใน  **main method**
สังเกตุว่าเราไม่ต้องกำหนดค่าเลยเมื่อประกาศตัวแปร ค่อยมาประกาศทีหลัง
```dart
// late variable
late String name;

void main() {
  // assigning value to late variable
  name = "John";
  print(name);
}
```

### Example 2: Late Keyword In Dart

ในตัวอย่างนี้คล้ายกับตัวอย่างเเรก ต่างกันเเค่มี **method greet()** เพิ่มมาหลักการทำงานจะคล้ายๆกัน
จำไว้เสมอว่าต้องกำหนดค่าให้ตัวแปร **name** ก่อนจะเรียกใช้งาน **method greet()** เพราะใน method มีการเรียนใช้งานตัวแปร **name** ถ้ายังไม่กำหนดค่า **name** จะเกิด **error** ขึ้น
```dart
class Person {
  // late variable
  late String name;

  void greet() {
    print("Hello $name");
  }
}

void main() {
  Person person = Person();
  // late variable is initialized here
  person.name = "John";
  person.greet();
}
```

------------

###  Lazy Initialization
การเลื่อนการกำหนดค่าหรือสร้างวัตถุจนกว่าจะมีการเข้าถึงหรือใช้งานจริง มักใช้เพื่อประหยัดทรัพยากรและเพิ่มประสิทธิภาพในการทำงาน โดยวัตถุหรือค่าจะถูกสร้างหรือกำหนดค่าเมื่อจำเป็นและจำไว้เพื่อใช้งานในครั้งถัดไป เป็นเทคนิคที่ช่วยลดการทำงานที่ไม่จำเป็นและเพิ่มประสิทธิภาพในโปรแกรม


### Example 3: Late Keyword In Dart Lazy Initialization

ตัวแปร **value** จะไม่มีการกำหนดค่าจนกว่าจะมีการเรียกใช้ตัวแปร จากตัวอย่างจะมีการกำหนดค่าเมื่อเรียกใช้  print(value)

```dart
// function
String provideCountry() {
  print("Function is called");
  return "USA";
}

void main() {
  print("Starting");
  // late variable
  late String value = provideCountry();
  print("End");
  print(value); // assigned value
}
```


--------------

### Example 4: Late Keyword In Class

ในตัวอย่างนี้ ระบบจะเรียก  **method heavyComputation** เมื่อใช้ตัวแปร **description** หากคุณลบคีย์เวิร์ด **late** ออกจากตัวแปร **description** ฟังก์ชัน **heavyComputation** จะถูกเรียกใช้เมื่อคลาส **Person** ถูกสร้างอินสแตนซ์

```dart
// Person class
class Person {
  final int age;
  final String name;
  late String description = heavyComputation();

// constructor
  Person(this.age, this.name) {
    print("Constructor is called");
  }
// method
  String heavyComputation() {
    print("heavyComputation is called");
    return "Heavy Computation";
  }
}

void main() {
  // object of Person class
  Person person = Person(10, "John");
  print(person.name);
  print(person.description); 
}
```


### Example 5: Late Keyword In Class

ในตัวอย่างนี้ method  getFullName() จะถูกเรียกใช้เมื่อมีการใช้ตัวแปร fullname , การเรียกใช้ตัวแปร firstName เเละ  lastName จะมีการเรียกใช้ตัวแปร fullName ก่อน ดังนั้นจึกเรียกใช้ method getFullName() ด้วย

```dart
class Person {
  // declaring late variables
  late String fullName = _getFullName();
  late String firstName = fullName.split(" ").first;
  late String lastName = fullName.split(" ").last;

// method
  String _getFullName() {
    print("_getFullName is called");
    return "John Doe";
  }
}
// main method
void main() {
  print("Start");
  Person person = Person();
  print("First Name: ${person.firstName}");
  print("Last Name: ${person.lastName}");
  print("Full Name: ${person.fullName}");
  print("End");
}
```

------------------------

### Late Final Keyword In Dart
การใช้ late final keyword จะใช้ในกรณีที่ต้องการกำหนดเเค่ค่าเดียวในตัวแปรเริ่มต้น ไม่สามารถเปลี่ยนแปลงค่าในตัวแปรได้

### Example 6: Late Final Keyword In Dart
การใช้  late final keyword  สามารถกำหนดค่าได้ครั้งเดียวเท่านั้น ถ้ากำหนดเกิน 1 ครั้งจะเกิดการ error ทันที

```dart
// Student class
class Student {
  // late final variable
  late final String name;

  // constructor
  Student(this.name);
}

void main() {
  // object of Student class
  Student student = Student("John");
  print(student.name);
  student.name = "Doe"; // Error
}
```

บรรทัดสุดท้ายการกำหนกค่า "Doe" เข้าไปในตัวแปร name ไม่สำเร็จเพราะตัวแปรname ได้กำหนดค่าก่อนไปเรียนร้อยเเล้ว

-------------------
### Difference Between Dart and Java and Python

**dart** กับ **java** จะคล้ายกัน เเต่ต่างกับ **python** ตรงที่ **Python** แนวคิดในการประกาศตัวแปรโดยคาดว่าจะได้รับการกำหนดในภายหลังนั้นไม่ได้เข้มงวดเท่ากับในภาษาอย่าง Dart หรือ Java Python ไม่มีค่าเทียบเท่ากับคีย์เวิร์ด late โดยตรง ตัวแปร Python สามารถสร้างได้โดยไม่ต้องใช้ค่าเริ่มต้น แลสามารถกำหนดค่าให้กับตัวแปรเหล่านี้ได้ตลอดเวลา อย่างไรก็ตาม Python นั้นมีการพิมพ์แบบไดนามิก ดังนั้นจึงไม่ประกาศประเภทตัวแปรอย่างชัดเจน

-----------------------
### Reference

[more exaple](https://www.educative.io/answers/what-is-the-late-keyword-in-dart)
[Lazy Initialization](https://dev.to/pktintali/late-variables-in-dart-dart-learning-series-1-2opf)

## Slide
[late keyword in dart](https://drive.google.com/file/d/1WTe1IcG6Dq3Wc6b70MBrslaYR755WfEK/view?usp=sharing)

## Link Vdo
[late keyword in dart](https://www.youtube.com/watch?v=jtz-0pcnAQ4)

## 640710551 ฟาอีซ สาเล็ง
