# Inheritance Of Constructor in Dart
ในส่วนนี้เราจะศึกษาเรื่องการสืบทอดคอนสตรักเตอร์ (constructor) ในภาษา Dart ว่าเป็นอย่างไรผ่านตัวอย่างที่จะช่วยให้เข้าใจง่ายขึ้น ก่อนที่เราจะลงสู่รายละเอียดของการสืบทอดคอนสตรักเตอร์ ขอให้คุณมีความเข้าใจพื้นฐานเกี่ยวกับคอนสตรักเตอร์และการสืบทอดใน Dart ในการเข้าใจหัวข้อนี้ จะเป็นประโยชน์หากคุณมีพื้นฐานเกี่ยวกับคลาสและวิธีการสร้างอ็อบเจกต์ใน Dart ถ้าคุณยังไม่มีความรู้เกี่ยวกับเรื่องนี้ คุณสามารถศึกษาในแหล่งข้อมูลเพิ่มเติมก่อนที่จะดำเนินการเรียนรู้ในส่วนนี้ได้

## การสืบทอดคอนสตรักเตอร์ในภาษา Dart
การสืบทอด (Inheritance) ของตัวสร้าง (Constructor) ในภาษาโปรแกรม Dart คือกระบวนการที่ทำให้คอนสตรักเตอร์ของคลาสแม่ถูกส่งต่อให้คลาสลูกไปใช้งาน นั่นคือเราสามารถนำคอนสตรักเตอร์จากคลาสแม่มาใช้ในคลาสลูกได้ เปรียบเสมือนการนำโค้ดที่เคยเขียนไว้ในคลาสแม่มาใช้ซ้ำในคลาสลูก

#### `ตัวอย่างที่ 1` การสืบทอดคอนสตรักเตอร์
>ในตัวอย่างที่ 1 มีคลาสที่ชื่อว่า "Laptop" ซึ่งมีคอนสตรักเตอร์อยู่ และยังมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดจากคลาส "Laptop" ซึ่งคลาส "MacBook" ก็มีคอนสตรักเตอร์ของตัวเองด้วยเช่นกัน

```dart
class Laptop {
// Constructor
  Laptop() {
    print("Laptop constructor");
  }
}

class MacBook extends Laptop {
// Constructor
  MacBook() {
    print("MacBook constructor");
  }
}

void main() {
  var macbook = MacBook();
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Laptop constructor
MacBook constructor</code>
</pre>
</details>

##### `คำอธิบายตัวอย่างที่ 1` การสร้างคลาสโดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ของตัวเอง
1. `class Laptop`
    - มีคอนสตรักเตอร์ที่ไม่รับพารามิเตอร์ และในส่วนของคอนสตรักเตอร์มีคำสั่ง __print("Laptop constructor");__
    - ซึ่งจะแสดงข้อความ "Laptop constructor" เมื่อมีการสร้างอ็อบเจ็กต์จากคลาส Laptop
2. `class MacBook extends Laptop`
    - คลาส "MacBook" สืบทอดมาจาก "Laptop" ซึ่งมีคอนสตรักเตอร์ของตัวเองอยู่แล้ว
    - คอนสตรักเตอร์ของ "MacBook" ไม่รับพารามิเตอร์ และมีคำสั่ง __print("MacBook constructor");__ ซึ่งจะแสดงข้อความว่า
    "MacBook constructor" เมื่อมีการสร้างอ็อบเจ็กต์จากคลาส "MacBook"
3. `void main()`
    - ในส่วน "main" เราสร้างอ็อบเจ็กต์ของคลาส "MacBook" ด้วย __var macbook = MacBook();__
    - เมื่อสร้างอ็อบเจ็กต์จากคลาส "MacBook" ตัวที่สร้างจะทำการเรียกคอนสตรักเตอร์ของทั้ง "MacBook" และ "Laptop"
    - ผลลัพธ์ที่แสดงจะเป็นตามลำดับของการเรียกคอนสตรักเตอร์โดยเริ่มจาก "Laptop constructor" และตามด้วย "MacBook constructor"<br>

_จากโค้ดตัวอย่างที่ 1 โค้ดด้านล่างต่อไปนี้เป็นการเขียนโค้ดโดยใช้รูปแบบเดียวกัน โดยจะเขียนด้วยภาษา C,Java และ Phyton ที่จะแสดงผลลัพธ์แบบเดียวกันกับตัวอย่าง_

<details> 
   <summary><strong>ตัวอย่างที่ 1 ในรูปแบบภาษา C</strong></summary>

```c
#include <stdio.h>

struct Laptop {
    // Constructor
    Laptop() {
        printf("Laptop constructor\n");
    }
};

struct MacBook {
    struct Laptop laptop;
};

int main() {
    struct MacBook macbook;
    printf("MacBook constructor\n");
    return 0;
}

```
__คำอธิบายโค้ด__ 
- ในภาษา C ไม่มีโครงสร้างเหมือนในภาษา Dart ดังนั้นเราใช้โครงสร้าง (struct) แทน
- ในภาษา C ไม่มีรูปแบบการประกาศ constructor เหมือนในภาษา Dart
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 1 ในรูปแบบภาษา Java </strong></summary>

```java
class Laptop {
    // Constructor
    Laptop() {
        System.out.println("Laptop constructor");
    }
}

class MacBook extends Laptop {
    // Constructor
    MacBook() {
        System.out.println("MacBook constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        MacBook macbook = new MacBook();
    }
}

```
__คำอธิบายโค้ด__ 
- ในภาษา Java ใช้คำสำคัญ class แทน class ในภาษา Dart
- ไม่ต้องใช้ void กับ constructor เช่นเดียวกับภาษา Dart
- ไม่ต้องใช้ var ในการประกาศตัวแปรแบบประกาศและกำหนดค่าพร้อมกัน (inline initialization) แต่ใช้ชนิดข้อมูลเพื่อประกาศตัวแปร
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 1 ในรูปแบบภาษา Python </strong></summary>

```Python
class Laptop:
    # Constructor
    def __init__(self):
        print("Laptop constructor")

class MacBook(Laptop):
    # Constructor
    def __init__(self):
        super().__init__()
        print("MacBook constructor")

macbook = MacBook()
```
__คำอธิบายโค้ด__ 
- ใน Python ใช้ def แทน fun เพื่อประกาศฟังก์ชัน
- ใช้ super().__init__() เพื่อเรียก constructor ของคลาสแม่และสร้างอ็อบเจ็กต์ใน Python
- ใน Python ไม่ต้องใช้ var ในการประกาศตัวแปรแบบประกาศและกำหนดค่าพร้อมกัน (inline initialization) แต่ใช้เป็นตัวแปรโดยตรง
</details>

#### `ตัวอย่างที่ 2` การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์
>ในตัวอย่างที่ 2 มีคลาสที่ชื่อว่า "Laptop" มีคอนสตรักเตอร์ที่รับพารามิเตอร์ และมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดจากคลาส "Laptop" คลาส "MacBook" มีคอนสตรักเตอร์ที่รับพารามิเตอร์ของตัวเองด้วยเช่นกัน

```dart
class Laptop {
  // Constructor
  Laptop(String name, String color) {
    print("Laptop constructor");
    print("Name: $name");
    print("Color: $color");
  }
}

class MacBook extends Laptop {
  // Constructor
  MacBook(String name, String color) : super(name, color) {
    print("MacBook constructor");
  }
}

void main() {
  var macbook = MacBook("MacBook Pro", "Silver");
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Laptop constructor
Name: MacBook Pro
Color: Silver
MacBook constructor</code>
</pre>
</details>

##### `คำอธิบายตัวอย่างที่ 2` การสร้างคลาสโดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ที่รับพารามิเตอร์และแสดงผลลัพธ์เมื่อมีการสร้างอ็อบเจ็กต์
1. `class Laptop`
    - คลาส "Laptop" มีคอนสตรักเตอร์ที่รับพารามิเตอร์ "name" และ "color"
    - ในส่วนของคอนสตรักเตอร์ของ "Laptop" มีคำสั่ง __print__ เพื่อแสดงข้อความ "Laptop constructor", ชื่อ "Name: [name]" และสี "Color: [color]" 
      โดยแทนค่า [name] และ [color] ด้วยค่าจริงที่รับเข้ามาในคอนสตรักเตอร์
2. `class MacBook extends Laptop`
    - คลาส "MacBook" สืบทอดมาจาก "Laptop" และมีคอนสตรักเตอร์ที่รับพารามิเตอร์ "name" และ "color" เหมือนกับคลาส “Laptop”
    - ในส่วนของคอนสตรักเตอร์ของ "MacBook" มีคำสั่ง __super(name, color);__  เพื่อเรียกใช้คอนสตรักเตอร์ของคลาสแม่ (Laptop) โดยส่งพารามิเตอร์ "name" และ "color" เพื่อกำหนดค่าในคลาสแม่ (Laptop)
3. `void main()`
    - ในส่วน "main" เราสร้างอ็อบเจ็กต์ของคลาส "MacBook" ด้วย __var macbook = MacBook("MacBook Pro", "Silver");__
    - เมื่อสร้างอ็อบเจ็กต์จากคลาส "MacBook" จะทำการเรียกคอนสตรักเตอร์ของทั้ง "MacBook" และ "Laptop" และแสดงผลลัพธ์การสร้างอ็อบเจ็กต์ที่ประกอบด้วยข้อความต่าง 
     ตามที่ระบุในคอนสตรักเตอร์ของคลาส "Laptop" และ "MacBook"

_จากโค้ดตัวอย่างที่ 2 โค้ดด้านล่างต่อไปนี้เป็นการเขียนโค้ดโดยใช้รูปแบบเดียวกัน โดยจะเขียนด้วยภาษา C,Java และ Phyton ที่จะแสดงผลลัพธ์แบบเดียวกันกับตัวอย่าง_

<details> 
   <summary><strong>ตัวอย่างที่ 2 ในรูปแบบภาษา C</strong></summary>

```c
#include <stdio.h>
#include <string.h>

struct Laptop {
    // Constructor
    Laptop(const char *name, const char *color) {
        printf("Laptop constructor\n");
        printf("Name: %s\n", name);
        printf("Color: %s\n", color);
    }
};

struct MacBook {
    struct Laptop laptop;
};

int main() {
    const char *name = "MacBook Pro";
    const char *color = "Silver";
    struct MacBook macbook = {{name, color}};
    printf("MacBook constructor\n");
    return 0;
}
```
__คำอธิบายโค้ด__ 
- ใช้ struct แทน class ในภาษา Dart
- ในภาษา C โครงสร้างข้อมูล struct ต้องถูกประกาศก่อนเรียกใช้งาน
- ใช้ const char * ในการประกาศและกำหนดค่าข้อความใน C
- ใน C ไม่ได้รองรับคุณสมบัติเหมือนภาษา Dart ดังนั้นเราจะต้องใช้ฟังก์ชันเพื่อกำหนดค่าเริ่มต้น
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 2 ในรูปแบบภาษา Java </strong></summary>

```java
class Laptop {
    // Constructor
    Laptop(String name, String color) {
        System.out.println("Laptop constructor");
        System.out.println("Name: " + name);
        System.out.println("Color: " + color);
    }
}

class MacBook extends Laptop {
    // Constructor
    MacBook(String name, String color) {
        super(name, color);
        System.out.println("MacBook constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        MacBook macbook = new MacBook("MacBook Pro", "Silver");
    }
}
```
__คำอธิบายโค้ด__ 
- ในภาษา Java ใช้คำสำคัญ class แทน class ในภาษา Dart
- การสร้าง constructor โดยมีพารามิเตอร์จำเป็นต้องใช้ชื่อเดียวกับคลาส
- ใช้ System.out.println() แทน print() ในภาษา Dart
- ใช้ super(name, color) เพื่อเรียก constructor ของคลาสแม่
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 2 ในรูปแบบภาษา Python </strong></summary>

```Python
class Laptop:
    # Constructor
    def __init__(self, name, color):
        print("Laptop constructor")
        print("Name:", name)
        print("Color:", color)

class MacBook(Laptop):
    # Constructor
    def __init__(self, name, color):
        super().__init__(name, color)
        print("MacBook constructor")

macbook = MacBook("MacBook Pro", "Silver")
```
__คำอธิบายโค้ด__ 
- ใน Python ใช้ def แทน fun เพื่อประกาศฟังก์ชัน
- ใน Python ใช้ self แทน this เพื่ออ้างถึงอ็อบเจ็กต์เอง
- ใช้ super().__init__(name, color) เพื่อเรียก constructor ของคลาสแม่และสร้างอ็อบเจ็กต์ใน Python
</details>

#### `ตัวอย่างที่ 3` การสืบทอดคอนสตรักเตอร์แบบที่ส่งค่าพารามิเตอร์ที่รับมาในคลาสลูกไปต่อให้คอนสตรักเตอร์ของคลาสแม่ เพื่อกำหนดค่าในคลาสแม่
>ในตัวอย่างที่ 3 มีคลาสที่ชื่อว่า "Person" ที่มีคุณสมบัติของชื่อและอายุ และยังมีคลาสอีกอันชื่อ "Student" ที่สืบทอดมาจากคลาส "Person" คลาส "Student" มีคุณสมบัติเพิ่มเติมอย่าง "rollNumber"
```dart
class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);
}

class Student extends Person {
  int rollNumber;

  // Constructor
  Student(String name, int age, this.rollNumber) : super(name, age);
}

void main() {
  var student = Student("John", 20, 1);
  print("Student name: ${student.name}");
  print("Student age: ${student.age}");
  print("Student roll number: ${student.rollNumber}");
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Student name: John
Student age: 20
Student roll number: 1</code>
</pre>
</details>

##### `คำอธิบายตัวอย่างที่ 3` การสร้างคลาสโดยมีการสร้างคอนสตรักเตอร์สำหรับทั้งสองคลาส และแสดงผลลัพธ์ที่ได้จากการสร้างอ็อบเจ็กต์ของคลาส
1. `class Person`
    - คลาส "Person" มีคุณสมบัติ "name" และ "age"
    - มีคอนสตรักเตอร์ที่รับพารามิเตอร์ "name" และ "age" เพื่อกำหนดค่าให้กับคุณสมบัติในคลาส
2. `class Student extends Person`
   	- คลาส "Student" สืบทอดมาจาก "Person" และมีคุณสมบัติเพิ่มเติมคือ "rollNumber"
   	- มีคอนสตรักเตอร์ที่รับพารามิเตอร์ "name", "age", และ "rollNumber" เพื่อกำหนดค่าให้กับคุณสมบัติในคลาส "Student" และใช้คีย์เวิร์ด "super" เพื่อเรียกใช้คอนสตรักเตอร์ของคลาสแม่(Person)
3. `void main()`
    - สร้างอ็อบเจ็กต์ของคลาส "Student" ด้วย __var student = Student("John", 20, 1);__
   	- เมื่อสร้างอ็อบเจ็กต์จากคลาส "Student" ค่า "John" จะถูกส่งให้กับพารามิเตอร์ "name" และ 20 จะถูกส่งให้กับพารามิเตอร์ "age" ในคอนสตรักเตอร์ของ "Person"
   	  และค่า 1 จะถูกส่งให้กับพารามิเตอร์ "rollNumber" ในคอนสตรักเตอร์ของ "Student"
    - ใช้คอนสตรักเตอร์เพื่อสร้างอ็อบเจ็กต์และแสดงผลลัพธ์ที่ได้จากการเข้าถึงค่าของคุณสมบัติ "name", "age", และ "rollNumber" ผ่านอ็อบเจ็กต์ที่สร้าง

_จากโค้ดตัวอย่างที่ 3 โค้ดด้านล่างต่อไปนี้เป็นการเขียนโค้ดโดยใช้รูปแบบเดียวกัน โดยจะเขียนด้วยภาษา C,Java และ Phyton ที่จะแสดงผลลัพธ์แบบเดียวกันกับตัวอย่าง_

<details> 
   <summary><strong>ตัวอย่างที่ 3 ในรูปแบบภาษา C</strong></summary>

```c
#include <stdio.h>
#include <string.h>

struct Person {
    char name[50];
    int age;
};

struct Student {
    struct Person person;
    int rollNumber;
};

int main() {
    struct Student student;
    strcpy(student.person.name, "John");
    student.person.age = 20;
    student.rollNumber = 1;
    
    printf("Student name: %s\n", student.person.name);
    printf("Student age: %d\n", student.person.age);
    printf("Student roll number: %d\n", student.rollNumber);

    return 0;
}
```
__คำอธิบายโค้ด__ 
- ในภาษา C ใช้ struct แทน class ในภาษา Dart
- ใช้ char name[50] แทน String name ใน Dart ในการประกาศอาร์เรย์ของตัวอักษร
- ใช้ int ในการประกาศตัวแปรชนิดเลขจำนวนเต็มใน C
- ใช้ strcpy() ในการคัดลอกข้อความใน C

</details>

<details> 
   <summary><strong>ตัวอย่างที่ 3 ในรูปแบบภาษา Java </strong></summary>

```java
class Person {
    String name;
    int age;

    // Constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

class Student extends Person {
    int rollNumber;

    // Constructor
    Student(String name, int age, int rollNumber) {
        super(name, age);
        this.rollNumber = rollNumber;
    }
}

public class Main {
    public static void main(String[] args) {
        Student student = new Student("John", 20, 1);
        System.out.println("Student name: " + student.name);
        System.out.println("Student age: " + student.age);
        System.out.println("Student roll number: " + student.rollNumber);
    }
}
```
__คำอธิบายโค้ด__ 
- ใน Java ใช้คำสำคัญ class แทน class ในภาษา Dart
- ใช้ String แทน char[] ในการประกาศสตริง
- ใช้ this เพื่ออ้างถึงตัวแปรสมาชิกของคลาส
- ไม่จำเป็นต้องใช้ return เพื่อส่งค่ากลับจาก constructor ใน Java
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 3 ในรูปแบบภาษา Python </strong></summary>

```Python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

class Student(Person):
    def __init__(self, name, age, rollNumber):
        super().__init__(name, age)
        self.rollNumber = rollNumber

student = Student("John", 20, 1)
print("Student name:", student.name)
print("Student age:", student.age)
print("Student roll number:", student.rollNumber)
```
__คำอธิบายโค้ด__ 
- ใน Python ใช้ def แทน fun เพื่อประกาศฟังก์ชัน
- ใน Python ใช้ self แทน this เพื่ออ้างถึงอ็อบเจ็กต์เอง
- ไม่ต้องใช้ return เพื่อส่งค่ากลับจาก constructor ใน Python
</details>

#### `ตัวอย่างที่ 4` การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อ
>ในตัวอย่างที่ 4 มีคลาสที่ชื่อว่า "Laptop" ที่มีคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อ และยังมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดมาจากคลาส "Laptop" คลาส "MacBook" มีคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อด้วย
```dart
class Laptop {
  // Constructor
  Laptop({String name = '', String color=''}) {
    print("Laptop constructor");
    print("Name: $name");
    print("Color: $color");
  }
}

class MacBook extends Laptop {
  // Constructor
  MacBook({String name ='', String color =''}): super(name: name, color: color) {
    print("MacBook constructor");
  }
}

void main() {
  var macbook = MacBook(name: "MacBook Pro", color: "Silver");
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Laptop constructor
Name: MacBook Pro
Color: Silver
MacBook constructor</code>
</pre>
</details>

##### `คำอธิบายตัวอย่างที่ 4` การใช้งานคลาสที่มีการสร้างคอนสตรักเตอร์ที่รับพารามิเตอร์แบบชื่อและการใช้งานการสืบทอดคอนสตรักเตอร์
1. `class Laptop`
    - มีคอนสตรักเตอร์ที่รับพารามิเตอร์แบบชื่อ "name" และ "color"
   	- ในคอนสตรักเตอร์ของ "Laptop" จะมีการแสดงข้อความ "Laptop constructor" และแสดงค่าของ "name" และ "color" ที่รับเข้ามา
2. `class MacBook extends Laptop`
   	- คลาส "MacBook" สืบทอดมาจาก "Laptop" และมีคอนสตรักเตอร์ที่รับพารามิเตอร์แบบชื่อ "name" และ "color"
   	- ในคอนสตรักเตอร์ของ "MacBook" จะมีการเรียกใช้คอนสตรักเตอร์ของคลาสแม่(Laptop) โดยส่งค่าของ "name" และ "color" ที่ได้รับเข้ามาผ่านคีย์เวิร์ด "super"
    - หลังจากเรียกใช้คอนสตรักเตอร์ของคลาสแม่คอนสตรักเตอร์ของ "MacBook" จะแสดงข้อความ "MacBook constructor"
3. `void main()`
    - สร้างอ็อบเจ็กต์ของคลาส "MacBook" โดยส่งค่า "name" เป็น "MacBook Pro" และ "color" เป็น "Silver"
    - เมื่อสร้างอ็อบเจ็กต์แล้วคอนสตรักเตอร์ของ "Laptop" และ "MacBook" จะถูกเรียกตามลำดับ และจะแสดงผลลัพธ์เกี่ยวกับค่าของ "name" และ "color" ที่ได้รับเข้ามา
   	- ท้ายที่สุดจะมีการแสดงข้อความว่า "MacBook constructor" ที่เป็นผลลัพธ์ของคอนสตรักเตอร์ "MacBook"

_จากโค้ดตัวอย่างที่ 4 โค้ดด้านล่างต่อไปนี้เป็นการเขียนโค้ดโดยใช้รูปแบบเดียวกัน โดยจะเขียนด้วยภาษา C,Java และ Phyton ที่จะแสดงผลลัพธ์แบบเดียวกันกับตัวอย่าง_

<details> 
   <summary><strong>ตัวอย่างที่ 4 ในรูปแบบภาษา C</strong></summary>

```c
#include <stdio.h>

struct Laptop {
    char name[50];
    char color[20];
};

void initLaptop(struct Laptop *laptop, const char *name, const char *color) {
    strcpy(laptop->name, name);
    strcpy(laptop->color, color);
    printf("Laptop constructor\n");
    printf("Name: %s\n", laptop->name);
    printf("Color: %s\n", laptop->color);
}

struct MacBook {
    struct Laptop laptop;
};

void initMacBook(struct MacBook *macbook, const char *name, const char *color) {
    initLaptop(&(macbook->laptop), name, color);
    printf("MacBook constructor\n");
}

int main() {
    struct MacBook macbook;
    initMacBook(&macbook, "MacBook Pro", "Silver");
    return 0;
}

```
__คำอธิบายโค้ด__ 
- ในภาษา C, ไม่มีโครงสร้างเหมือนกับคลาสใน Dart ดังนั้นเราใช้โครงสร้าง struct แทน ซึ่งเก็บข้อมูลภายใน
- การสร้าง constructor ในภาษา C ไม่ได้เป็นที่เสริมเช่นใน Dart แทนที่เราสร้างฟังก์ชันแยกในการกำหนดค่าเริ่มต้น
- เราใช้ฟังก์ชัน strcpy() เพื่อคัดลอกข้อความใน C
- การเข้าถึงสมาชิกของโครงสร้างใน C เราใช้ . แทน -> ในภาษา Dart
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 4 ในรูปแบบภาษา Java </strong></summary>

```java
class Laptop {
    Laptop(String name, String color) {
        System.out.println("Laptop constructor");
        System.out.println("Name: " + name);
        System.out.println("Color: " + color);
    }
}

class MacBook extends Laptop {
    MacBook(String name, String color) {
        super(name, color);
        System.out.println("MacBook constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        MacBook macbook = new MacBook("MacBook Pro", "Silver");
    }
}

```
__คำอธิบายโค้ด__ 
- ในภาษา Java ใช้คีย์เวิร์ด class แทนคีย์เวิร์ด class ในภาษา Dart
- ใน Java การเรียก constructor ของคลาสแม่เราใช้ super(name, color) แทน super(name: name, color: color) ใน Dart
- การประกาศและกำหนดค่าตัวแปรใน Java เราต้องระบุชนิดข้อมูล เช่น String name
- ใน Java ใช้ System.out.println() แทน print() ใน Dart
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 4 ในรูปแบบภาษา Python </strong></summary>

```Python
class Laptop:
    def __init__(self, name='', color=''):
        print("Laptop constructor")
        print("Name:", name)
        print("Color:", color)

class MacBook(Laptop):
    def __init__(self, name='', color=''):
        super().__init__(name, color)
        print("MacBook constructor")

macbook = MacBook(name="MacBook Pro", color="Silver")

```
__คำอธิบายโค้ด__ 
- ใน Python คำสั่ง class แทนคำสั่ง class ในภาษา Dart
- Python ไม่ต้องระบุชนิดข้อมูลของตัวแปรเมื่อประกาศ
- ใช้ def แทน fun เพื่อประกาศฟังก์ชันใน Python
- ใช้ super().__init__(name, color) เพื่อเรียก constructor ของคลาสแม่
- การพิมพ์ผลลัพธ์ใน Python ใช้ print() โดยไม่ต้องใส่วงเล็บ
</details>

##### จากตัวอย่างที่ 4 : การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อใน Dart มีประโยชน์อย่างไร
1. **ความยืดหยุ่นในการเรียกใช้งาน**<br>การใช้พารามิเตอร์แบบชื่อทำให้คุณสามารถเรียกใช้คอนสตรักเตอร์ของคลาสลูกได้โดยระบุชื่อพารามิเตอร์ที่ต้องการ ซึ่งทำให้ไม่จำเป็นต้องเรียงลำดับพารามิเตอร์ตามลำดับที่กำหนดในคลาสแม่
2. **การรับค่าเริ่มต้นที่ชัดเจน**<br>การระบุค่าเริ่มต้นในพารามิเตอร์แบบชื่อ จะแสดงความชัดเจนเกี่ยวกับค่าเริ่มต้นของแต่ละพารามิเตอร์ ทำให้โค้ดอ่านและเข้าใจง่ายขึ้น
3. **การเพิ่มพารามิเตอร์ในอนาคต**<br>เมื่อต้องการเพิ่มพารามิเตอร์ในคอนสตรักเตอร์ของคลาสลูก สามารถทำได้โดยไม่ต้องแก้ไขคอนสตรักเตอร์ในคลาสแม่ ทำให้การเปลี่ยนแปลงเป็นไปอย่างเป็นระบบและปลอดภัย
4. **การอ่านและการบำรุงรักษา**<br>รหัสที่มีการใช้พารามิเตอร์แบบชื่อมักจะมีความชัดเจนและง่ายต่อการอ่าน นี่จะช่วยให้เข้าใจการทำงานของโค้ดและการบำรุงรักษาได้ง่ายขึ้น

ดังนั้นการใช้งานการสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อช่วยให้โค้ดเป็นระบบและสามารถปรับปรุงได้ง่าย เพิ่มความชัดเจนและความยืดหยุ่นในการเขียนโปรแกรม

#### `ตัวอย่างที่ 5` เรียกใช้งาน Named Constructor ของคลาสแม่
>ในตัวอย่างที่ 5 มีคลาสชื่อ "Laptop" ที่มีคอนสตรักเตอร์เริ่มต้นและคอนสตรักเตอร์แบบชื่อหนึ่งตัว มีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดคุณสมบัติจากคลาส "Laptop" และมีคอนสตรักเตอร์ของตัวเองที่สามารถเรียกใช้งานคอนสตรักเตอร์แบบชื่อของคลาสแม่ได้โดยใช้คีย์เวิร์ด "super"
```dart
class Laptop {
  // Default Constructor
  Laptop() {
    print("Laptop constructor");
  }

  // Named Constructor
  Laptop.named() {
    print("Laptop named constructor");
  }
}

class MacBook extends Laptop {
  // Constructor
  MacBook() : super.named() {
    print("MacBook constructor");
  }
}

void main() {
  var macbook = MacBook();
}
```
<details>
<summary><strong>แสดงผลลัพธ์</strong></summary>
<pre>
<code>Laptop named constructor
MacBook constructor</code>
</pre>
</details>

##### `คำอธิบายตัวอย่างที่ 5` เรียกใช้งาน Named Constructor ของคลาสแม่
1. `class Laptop`
    - มี constructor แบบ default ซึ่งจะแสดงข้อความว่า "Laptop constructor" เมื่อถูกเรียก 
    - และมี named constructor ที่ชื่อว่า __named__ ซึ่งจะแสดงข้อความว่า "Laptop named constructor" เมื่อถูกเรียกใช้งาน
2. `class MacBook extends Laptop`
    - คลาส "MacBook" ที่สืบทอดคุณสมบัติจากคลาส "Laptop" และมี constructor ของตัวเองซึ่งจะแสดงข้อความว่า
      "MacBook constructor" 
    - และมีการใช้ constructor แบบ super กับ named constructor __super.named()__ เพื่อเรียก named constructor ของคลาสแม่(Laptop) 
3. `void main()`
    - สร้างอ็อบเจ็กต์ของคลาส "MacBook" ด้วย __var macbook = MacBook();__
    - เมื่อสร้างอ็อบเจ็กต์จากคลาส "MacBook" ตัวสร้างจะทำการเรียกคอนสตรักเตอร์ของทั้ง "MacBook" และ "Laptop" โดยจะเรียกคอนสตรักเตอร์จากคลาส "Laptop"
      ที่มีชื่อว่า __Laptop.named()__ เท่านั้น
    - ผลลัพธ์ที่แสดงจะเป็นตามลำดับของการเรียกคอนสตรักเตอร์โดยเริ่มจากคลาสแม่(Laptop) ตามด้วยคอนสตรักเตอร์ของคลาสลูก(MacBook) ซึ่งจะได้ผลลัพธ์เป็นการแสดง
      ข้อความว่า "Laptop named constructor" และตามด้วย "MacBook constructor"

_จากโค้ดตัวอย่างที่ 5 โค้ดด้านล่างต่อไปนี้เป็นการเขียนโค้ดโดยใช้รูปแบบเดียวกัน โดยจะเขียนด้วยภาษา C,Java และ Phyton ที่จะแสดงผลลัพธ์แบบเดียวกันกับตัวอย่าง_

<details> 
   <summary><strong>ตัวอย่างที่ 5 ในรูปแบบภาษา C</strong></summary>

```c
#include <stdio.h>

struct Laptop {
    // Default Constructor
    Laptop() {
        printf("Laptop constructor\n");
    }

    // Named Constructor
    static struct Laptop named() {
        struct Laptop laptop;
        printf("Laptop named constructor\n");
        return laptop;
    }
};

struct MacBook {
    struct Laptop laptop;
};

int main() {
    struct MacBook macbook;
    macbook.laptop = Laptop_named();
    printf("MacBook constructor\n");
    return 0;
}

```
__คำอธิบายโค้ด__ 
- ในภาษา C ไม่ได้มีการรองรับคุณสมบัติเหมือนในภาษา Dart ดังนั้นต้องใช้โครงสร้าง (struct) แทน
- ในภาษา C ไม่มีการสนับสนุนชื่อ constructor แบบที่มีในภาษา Dart แทนที่จะใช้ฟังก์ชันเสมือน constructor และกำหนดค่าเริ่มต้นเป็นส่วนหนึ่งของการเรียกฟังก์ชันนั้น
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 5 ในรูปแบบภาษา Java </strong></summary>

```java
class Laptop {
    // Default Constructor
    Laptop() {
        System.out.println("Laptop constructor");
    }

    // Named Constructor
    Laptop(String named) {
        System.out.println("Laptop named constructor");
    }
}

class MacBook extends Laptop {
    // Constructor
    MacBook() {
        super("named");
        System.out.println("MacBook constructor");
    }
}

public class Main {
    public static void main(String[] args) {
        MacBook macbook = new MacBook();
    }
}

```
__คำอธิบายโค้ด__ 
- ในภาษา Java ใช้คำสำคัญ class แทน class ในภาษา Dart
- ในภาษา Java การสร้าง constructor แบบที่มีชื่อเรียกว่า "named constructor" ทำได้โดยการสร้าง constructor พร้อมกับ parameter ที่ตรงกับชื่อ constructor ที่เราต้องการ
</details>

<details> 
   <summary><strong>ตัวอย่างที่ 5 ในรูปแบบภาษา Python </strong></summary>

```Python
class Laptop:
    # Default Constructor
    def __init__(self):
        print("Laptop constructor")

    # Named Constructor
    @classmethod
    def named(cls):
        laptop = cls()
        print("Laptop named constructor")
        return laptop

class MacBook(Laptop):
    # Constructor
    def __init__(self):
        super().named()
        print("MacBook constructor")

macbook = MacBook()
```
__คำอธิบายโค้ด__ 
- ในภาษา Python ใช้ def แทน fun เพื่อประกาศฟังก์ชัน
- ใช้ decorator @classmethod เพื่อประกาศเมธอดชื่อเดียวกับคลาส เพื่อทำให้เป็นเมธอดที่สามารถเรียกใช้ได้จากคลาสและไม่จำเป็นต้องสร้างอ็อบเจ็กต์ก่อน
- ใน Python ใช้ super().named() เพื่อเรียก constructor ของคลาสแม่และสร้างอ็อบเจ็กต์
</details>

## Silde นำเสนอ
- [Inheritance Of Constructor.pdf](https://drive.google.com/file/d/1veqfkulIit1M0HviQd9ufydO05yx8DYP/view?usp=sharing)
- [Inheritance Of Constructor.pptx](https://docs.google.com/presentation/d/1y8xHc8P-gVhJJkAmNzXFunSN065MxiJo/edit?usp=sharing&ouid=116662538381881581640&rtpof=true&sd=true)

## Link Video
- [คลิกเพื่อดูวิดีโอ](https://youtu.be/z-5hnCX3f9I?feature=shared)

## Reference
- https://dart-tutorial.com/object-oriented-programming/inheritance-of-constructor-in-dart<br>
- https://www.w3schools.com/c/c_structs.php<br>
- https://www.geeksforgeeks.org/inheritance-in-python<br>
- https://www.javatpoint.com/order-of-execution-of-constructors-in-java-inheritance<br>
