# Constructor in Dart (Part 1)
## Constructor ในภาษา Dart
- Constructor เป็นเมธอดพิเศษที่ใช้กำหนดค่าเริ่มต้นให้กับวัตถุ มันจะถูกเรียกอัตโนมัติเมื่อมีการสร้าง Object และสามารถใช้ในการกำหนดค่าเริ่มต้นสำหรับคุณสมบัติของ Object ได้ 
- ตัวอย่างนี้จะเป็นการสร้าง Object class Car เเละตั้งค่าเริ่มต้นสำหรับ สีรถเเละรุ่นของรถยนต์
           
```dart
Person person = Person("John", 30);
```

## ถ้าไม่มี Constructor
    
- หากคุณไม่ได้กำหนด Constructor สำหรับ class คุณจะต้องตั้งค่าของคุณสมบัติด้วยตนเอง ตัวอย่างเช่น โค้ดต่อไปนี้จะสร้าง Object ของ class Car และตั้งค่าสำหรับคุณสมบัติชื่อและอายุ
```     
          Person person = Person();
          person.name = "John";
          person.age = 30;
```

## สิ่งที่ควรจำ
- ชื่อของ Constructor ควรเหมือนกับชื่อคลาส นั่นคือ เมื่อคุณต้องการสร้าง Constructor สำหรับคลาสที่ชื่อว่า Person  ดังนั้น Constructor ควรจะมีชื่อเป็น Person เช่นเดียวกับชื่อคลาส

```dart 
     class Person {
        // Constructor with the same name as the class
         Person() {
          // Constructor code here
         }
        }
``` 

- Constructor ไม่มีประเภทข้อมูลการส่งคืน (return type) นั่นคือ เมื่อคุณประกาศ Constructor ในภาษา Dart คุณไม่ต้องระบุประเภทข้อมูลที่จะส่งคืนจาก Constructor นั้น เนื่องจาก Constructor มีหน้าที่เพียงการกำหนดค่าเริ่มต้นให้กับ instance ที่ถูกสร้างขึ้น และไม่ได้ส่งค่ากลับเหมือนฟังก์ชันทั่วไป

```dart
  class Person {
  String name;

  // Constructor with the same name as the class
  Person(String name) {
    this.name = name;
    // No return statement needed
  }
}
```
  
## Syntax
- วิธีประกาศคอนสตรักเตอร์ในภาษา Dart โดยมีรูปแบบดังนี้

```dart
class ClassName {
// Constructor declaration: Same as class name
ClassName() {
// body of the constructor
}
}
```
> หมายเหตุ เมื่อคุณสร้าง Object ของ class ใดๆ Constructor จะถูกเรียกอัตโนมัติ มันถูกใช้ในการกำหนดค่าเริ่มต้นเมื่อมีการสร้าง Object


##  ตัวอย่างที่ 1: วิธีการประกาศ Constructor ใน Dart
- ในตัวอย่างนี้ด้านล่างมี class Student ที่มีคุณสมบัติสามอย่างคือ  name , age และ rollNumber ใน class นี้จะใช้ constructor เพื่อกำหนดค่าของคุณสมบัติทั้งสาม นอกจากนี้เรายังสร้างวัตถุของ class Student ใน main
```dart
class Student {
  //เราประกาศคลาส Student ซึ่งมีคุณสมบัติ name และ age และ rollNumber โดยใช้คีย์เวิร์ด String? และ int? เพื่อระบุว่าคุณสมบัติเหล่านี้อาจมีค่า null หรือไม่ก็ได้
  String? name;
  int? age;
  int? rollNumber;

  // Constructor
  //ประกาศ constructor ในคลาส Student ด้วยชื่อเหมือนกับ class (Student) ซึ่งรับพารามิเตอร์ name และ age และ rollNumber 
  //เพื่อกำหนดค่าเริ่มต้นให้กับคุณสมบัติของออบเจกต์ ภายใน constructor มีการแสดงข้อความ "Constructor called" ออกทางหน้าจอเพื่อตรวจสอบว่า constructor ถูกเรียกหรือไม่.
  Student(String name, int age, int rollNumber) { 
    print("Constructor called"); // ใช้สำหรับเช็คว่า constructor ถูกเรียกหรือไม่
    this.name = name;
    this.age = age;
    this.rollNumber = rollNumber;
  }
}
void main() {
  // Here student is object of class Student.
  //เราสร้างออบเจกต์ student โดยใช้ constructor ที่เราประกาศไว้ในคลาส Student และส่งพารามิเตอร์เข้าไป.
  //ใช้คำสั่ง print เพื่อแสดงค่าของคุณสมบัติ name และ age และ rollNumber ของออบเจกต์ student.
  Student student = Student("John", 20, 1);
  print("Name: ${student.name}");
  print("Age: ${student.age}");
  print("Roll Number: ${student.rollNumber}");
}
```
- Output
```
Constructor called
Name: John
Age: 20
Roll Number: 1
```

>หมายเหตุ: คำว่า "this" ถูกใช้เพื่ออ้างอิงถึง instance ปัจจุบันของคลาส มันถูกใช้ในการเข้าถึงคุณสมบัติของคลาสปัจจุบัน 
>ในตัวอย่างข้างต้น ชื่อพารามิเตอร์และคุณสมบัติของคลาสใน constructor Student เป็นเหมือนกัน ดังนั้นเพื่อป้องกันความสับสน เราใช้คำว่า "this" เพื่อแยกแยะการอ้างอิง เป็นลักษณะที่ชัดเจน
>ในทางปฏิบัติ, การใช้คำว่า "this" ในการเขียนโปรแกรมทำให้คุณสามารถเข้าถึงคุณสมบัติของ instance ที่กำลังถูกสร้างขึ้นได้อย่างชัดเจน 
>แม้ว่าชื่อพารามิเตอร์และคุณสมบัติของคลาสจะเหมือนกันก็ตาม การใช้ "this" ช่วยแยกแยะและทำให้โค้ดเข้าใจง่ายขึ้น.

## ถ้าเรานำโค้ดด้านบนมาแปลงเป็นภาษา Java จะได้ดังนี้:

```dart
class Student {
    String name;
    int age;
    int rollNumber;

    // Constructor
    Student(String name, int age, int rollNumber) {
        System.out.println("Constructor called");
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
    }
}
public class Main {
    public static void main(String[] args) {
        // Here student is an object of the Student class.
        Student student = new Student("John", 20, 1);
        System.out.println("Name: " + student.name);
        System.out.println("Age: " + student.age);
        System.out.println("Roll Number: " + student.rollNumber);
    }
}
```

## ตัวอย่างที่ 2: ตัวสร้างใน Dart

- ในตัวอย่างด้านล่างนี้ มี class ชื่อ Teacher มีคุณสมบัติทั้งหมด 4 ค่า คือ name, age, subject, และ salary คลาสนี้มี constructor 1 ตัวที่ใช้ในการกำหนดค่าเริ่มต้นของคุณสมบัติต่าง ๆ ใน class 
- นอกจากนี้ class ยังมี method ชื่อ display() ที่ใช้ในการแสดงค่าของคุณสมบัติต่าง ๆ ใน class  เราได้สร้าง Object 2 ตัวของ class Teacher โดยตั้งชื่อว่า teacher1 และ teacher2

```dart
class Teacher {
  String? name;
  int? age;
  String? subject;
  double? salary;

  // Constructor
  //class Teacher มีคุณสมบัติ 4 อย่าง คือ name, age, subject, และ salary.
  Teacher(String name, int age, String subject, double salary) {
    this.name = name;
    this.age = age;
    this.subject = subject;
    this.salary = salary;
  }
  // Method
  //method display() ใช้สำหรับแสดงค่าของคุณสมบัติใน class
  void display() {
    print("Name: ${this.name}");
    print("Age: ${this.age}");
    print("Subject: ${this.subject}");
    print("Salary: ${this.salary}\n"); // \n is used for new line
  }
}

void main() {
  //ในฟังก์ชัน main, เราสร้างออบเจกต์ 2 ตัวของคลาส Teacher และเรียกใช้เมธอด display() เพื่อแสดงข้อมูลของออบเจกต์ทั้ง 2 ตัว.
  // สร้าง teacher1 object ของ class Teacher
  Teacher teacher1 = Teacher("John", 30, "Maths", 50000.0);
  teacher1.display();

  // สร้าง teacher2 object ของ class Teacher
  Teacher teacher2 = Teacher("Smith", 35, "Science", 60000.0);
  teacher2.display();
}
```

- Output
```
Name: John
Age: 30
Subject: Maths
Salary: 50000

Name: Smith
Age: 35
Subject: Science
Salary: 60000
```
## ถ้าเรานำโค้ดด้านบนมาแปลงเป็นภาษา Java จะได้ดังนี้:
```dart
    class Teacher {
    String name;
    int age;
    String subject;
    double salary;

    // Constructor
    Teacher(String name, int age, String subject, double salary) {
        this.name = name;
        this.age = age;
        this.subject = subject;
        this.salary = salary;
    }

    // Method
    void display() {
        System.out.println("Name: " + this.name);
        System.out.println("Age: " + this.age);
        System.out.println("Subject: " + this.subject);
        System.out.println("Salary: " + this.salary + "\n");
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating teacher1 object of class Teacher
        Teacher teacher1 = new Teacher("John", 30, "Maths", 50000.0);
        teacher1.display();

        // Creating teacher2 object of class Teacher
        Teacher teacher2 = new Teacher("Smith", 35, "Science", 60000.0);
        teacher2.display();
    }
}
```
>หมายเหตุ: คุณสามารถสร้าง object หลายตัวของ class เดียวกันได้ แต่ละ object จะมีสำเนาของคุณสมบัติต่างๆ ของมันเอง
>เมื่อคุณสร้าง object ของ class แต่ละ Object นั่นคือ ถึงแม้คุณสร้าง Object หลายตัวที่เป็นของ class เดียวกัน แต่แต่ละ Object จะมีสำเนาของคุณสมบัติที่แตกต่างกันเอง
>นั่นหมายความว่าการเปลี่ยนแปลงค่าคุณสมบัติใน Object หนึ่งจะไม่กระทบถึงค่าคุณสมบัติใน Object อื่น ทำให้แต่ละ Object มีความอิสระในการจัดการค่าของตัวเองโดยไม่ส่งผลกระทบกับ Object อื่นใด ๆ ที่เป็นของ class เดียวกัน

## ตัวอย่างที่ 3: ตัวสร้างใน Dart

- ในตัวอย่างด้านล่างนี้, มี class ชื่อ Car ที่มีคุณสมบัติ 2 อย่างคือ name และ prize class นี้มี constructor 1 ตัวสำหรับกำหนดค่าเริ่มต้นของคุณสมบัติต่าง ๆ ใน class
- นอกจากนี้ class ยังมี method ชื่อ display() ที่ใช้สำหรับแสดงค่าของคุณสมบัติต่าง ๆ ใน class เราได้สร้าง object 1 ตัวของ class  Car และตั้งชื่อว่า car
```dart
 class Car {
  String? name;
  double? prize;

  // Constructor
  //มี constructor สำหรับ class Car ที่รับพารามิเตอร์ต่าง ๆ และกำหนดค่าเริ่มต้นให้กับคุณสมบัติต่าง ๆ ใน class
  Car(String name, double prize) {
    this.name = name;
    this.prize = prize;
  }

  // Method
      //method display() ใช้สำหรับแสดงค่าของคุณสมบัติใน class .
  void display() {
    print("Name: ${this.name}");
    print("Prize: ${this.prize}");
  }
}

void main() {
      // สร้างออบเจกต์ 1 ตัวของคลาส Car และเรียกใช้เมธอด display() เพื่อแสดงข้อมูลของออบเจกต์.
  Car car = Car("BMW", 500000.0);
  car.display();
}
```
- Output
```
Name: BMW
Prize: 500000
```

## ถ้าเรานำโค้ดด้านบนมาแปลงเป็นภาษา Java จะได้ดังนี้:

```dart
class Car {
     // class Car มีคุณสมบัติ 2 อย่างคือ name และ prize
    String name;
    double prize;

    // Constructor
    Car(String name, double prize) {
        this.name = name;
        this.prize = prize;
    }

    // Method
    void display() {
        System.out.println("Name: " + this.name);
        System.out.println("Prize: " + this.prize);
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car("BMW", 500000.0);
        car.display();
    }
}
```
## ตัวอย่างที่ 4: ตัวสร้างใน Dart
- ในตัวอย่างด้านล่างนี้, มี class ชื่อ Staff ที่มีคุณสมบัติ 4 อย่างคือ name, phone1, phone2, และ subject class นี้มี constructor 1 
- ตัวสำหรับกำหนดค่าเริ่มต้นของคุณสมบัติบางส่วนใน class นอกจากนี้ class ยังมี method ชื่อ display() ที่ใช้สำหรับแสดงค่าของคุณสมบัติต่าง ๆ ใน class เราได้สร้าง object 1 ตัวของ class Staff และตั้งชื่อว่า staff
```dart
    //class Staff มีคุณสมบัติ 4 อย่างคือ name, phone1, phone2, และ subject.
    class Staff {
    String? name;
    int? phone1;
    int? phone2;
    String? subject;

    // Constructor
    //มี constructor สำหรับclass Staff ที่รับพารามิเตอร์บางส่วน และกำหนดค่าเริ่มต้นให้กับคุณสมบัติต่าง ๆ ในclass
    Staff(String name, int phone1, String subject) {
        this.name = name;
        this.phone1 = phone1;
        this.subject = subject;
    }

    // Method to display information
    //method display() ใช้สำหรับแสดงค่าของคุณสมบัติใน class.
    void display() {
         print("Name: ${this.name}");
         print("Phone1: ${this.phone1}");
         print("Phone2: ${this.phone2}");
         print("Subject: ${this.subject}");
    }
}

      void main(){
        // Creating an object of the Staff class
        Staff staff = new Staff("John", 1234567890 , "Maths");
        staff.display();
      }
```
>output
```
Name: John
Phone1: 1234567890
Phone2: null
Subject: Maths
```

## ถ้าเรานำโค้ดด้านบนมาแปลงเป็นภาษา Java จะได้ดังนี้:

```dart
class Staff {
    String name;
    int phone1;
    int phone2;
    String subject;

    // Constructor
    Staff(String name, int phone1, String subject) {
        this.name = name;
        this.phone1 = phone1;
        this.subject = subject;
    }

    // Method to display information
    void display() {
        System.out.println("Name: " + this.name);
        System.out.println("Phone 1: " + this.phone1);
        System.out.println("Phone 2: " + this.phone2);
        System.out.println("Subject: " + this.subject);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating an object of the Staff class
        Staff staff = new Staff("John", 1234567890 , "Maths");
        staff.display();
    }
}
```
## ข้อมูลเพิ่มเติมที่น่าสนใจ
## Constructor จะไม่ถูกสืบทอด
- Subclasses ไม่ได้สืบทอด Constructor จาก Superclass เสมอไป Subclasses ที่ไม่ได้ประกาศ Constructor ใด ๆ จะมีเพียง Constructor เริ่มต้น (Default constructor) เท่านั้น Constructor เริ่มต้นจะไม่มีอาร์กิวเมนต์และไม่มีชื่อ ใน Subclasses
- โดยปกติแล้ว, Constructor ใน Subclassesจะต้องถูกประกาศและเรียกใช้เอง และไม่สามารถสืบทอดคอนสตรักเตอร์จากคลาสหลักได้

## reference(s)
- https://dart-tutorial.com
- https://dart.dev
- https://www.tutorialspoint.com

## Link Video
- https://drive.google.com/file/d/1PVGuoFsVUwQ-qNr7e58RGVs9f1fgOYrx/view?usp=sharing

## Silde นำเสนอ
- [Constructor in Dart Part 1'.pdf](https://github.com/soonklang/dart-tutorial/files/12816686/Constructor.in.Dart.Part.1.pdf)
- [Constructor in Dart Part 1'.pptx](https://github.com/soonklang/dart-tutorial/files/12816687/Constructor.in.Dart.Part.1.pptx)








