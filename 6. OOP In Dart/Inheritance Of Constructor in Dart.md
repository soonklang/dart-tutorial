# Inheritance Of Constructor in Dart
ในส่วนนี้เราจะศึกษาเรื่องการสืบทอดคอนสตรักเตอร์ (constructor) ในภาษา Dart ว่าเป็นอย่างไรผ่านตัวอย่างที่จะช่วยให้เข้าใจง่ายขึ้น ก่อนที่เราจะลงสู่รายละเอียดของการสืบทอดคอนสตรักเตอร์ ขอให้คุณมีความเข้าใจพื้นฐานเกี่ยวกับคอนสตรักเตอร์และการสืบทอดใน Dart ในการเข้าใจหัวข้อนี้ จะเป็นประโยชน์หากคุณมีพื้นฐานเกี่ยวกับคลาสและวิธีการสร้างอ็อบเจกต์ใน Dart ถ้าคุณยังไม่มีความรู้เกี่ยวกับเรื่องนี้ คุณสามารถศึกษาในแหล่งข้อมูลเพิ่มเติมก่อนที่จะดำเนินการเรียนรู้ในส่วนนี้ได้

## การสืบทอดคอนสตรักเตอร์ในภาษา Dart
การสืบทอด (Inheritance) ของตัวสร้าง (Constructor) ในภาษาโปรแกรม Dart คือกระบวนการที่ทำให้คอนสตรักเตอร์ของคลาสแม่ถูกส่งต่อให้คลาสลูกไปใช้งาน นั่นคือเราสามารถนำคอนสตรักเตอร์จากคลาสแม่มาใช้ในคลาสลูกได้ เปรียบเสมือนการนำโค้ดที่เคยเขียนไว้ในคลาสแม่มาใช้ซ้ำในคลาสลูก

#### `ตัวอย่างที่ 1` การสืบทอดคอนสตรักเตอร์
>ในตัวอย่างที่1 มีคลาสที่ชื่อว่า "Laptop" ซึ่งมีคอนสตรักเตอร์อยู่ และยังมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดจากคลาส "Laptop" ซึ่งคลาส "MacBook" ก็มีคอนสตรักเตอร์ของตัวเองด้วยเช่นกัน

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

##### `คำอธิบายตัวอย่างที่1` การสร้างคลาสโดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ของตัวเอง
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
    - ผลลัพธ์ที่แสดงจะเป็นตามลำดับของการเรียกคอนสตรักเตอร์โดยเริ่มจาก "Laptop constructor" และตามด้วย "MacBook constructor"

#### `ตัวอย่างที่ 2` การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์
>ในตัวอย่างที่2 มีคลาสที่ชื่อว่า "Laptop" มีคอนสตรักเตอร์ที่รับพารามิเตอร์ และมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดจากคลาส "Laptop" คลาส "MacBook" มีคอนสตรักเตอร์ที่รับพารามิเตอร์ของตัวเองด้วยเช่นกัน

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

##### `คำอธิบายตัวอย่างที่2` การสร้างคลาสโดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ที่รับพารามิเตอร์และแสดงผลลัพธ์เมื่อมีการสร้างอ็อบเจ็กต์
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

#### `ตัวอย่างที่ 3` การสืบทอดคอนสตรักเตอร์แบบที่ส่งค่าพารามิเตอร์ที่รับมาในคลาสลูกไปต่อให้คอนสตรักเตอร์ของคลาสแม่ เพื่อกำหนดค่าในคลาสแม่
>ในตัวอย่างที่3 มีคลาสที่ชื่อว่า "Person" ที่มีคุณสมบัติของชื่อและอายุ และยังมีคลาสอีกอันชื่อ "Student" ที่สืบทอดมาจากคลาส "Person" คลาส "Student" มีคุณสมบัติเพิ่มเติมอย่าง "rollNumber"
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

##### `คำอธิบายตัวอย่างที่3` การสร้างคลาสโดยมีการสร้างคอนสตรักเตอร์สำหรับทั้งสองคลาส และแสดงผลลัพธ์ที่ได้จากการสร้างอ็อบเจ็กต์ของคลาส
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

#### `ตัวอย่างที่ 4` การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อ
>ในตัวอย่างที่4 มีคลาสที่ชื่อว่า "Laptop" ที่มีคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อ และยังมีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดมาจากคลาส "Laptop" คลาส "MacBook" มีคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อด้วย
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

##### `คำอธิบายตัวอย่างที่4` การใช้งานคลาสที่มีการสร้างคอนสตรักเตอร์ที่รับพารามิเตอร์แบบชื่อและการใช้งานการสืบทอดคอนสตรักเตอร์
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

##### จากตัวอย่างที่ 4 : การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อใน Dart มีประโยชน์อย่างไร
1. **ความยืดหยุ่นในการเรียกใช้งาน**<br>การใช้พารามิเตอร์แบบชื่อทำให้คุณสามารถเรียกใช้คอนสตรักเตอร์ของคลาสลูกได้โดยระบุชื่อพารามิเตอร์ที่ต้องการ ซึ่งทำให้ไม่จำเป็นต้องเรียงลำดับพารามิเตอร์ตามลำดับที่กำหนดในคลาสแม่
2. **การรับค่าเริ่มต้นที่ชัดเจน**<br>การระบุค่าเริ่มต้นในพารามิเตอร์แบบชื่อ จะแสดงความชัดเจนเกี่ยวกับค่าเริ่มต้นของแต่ละพารามิเตอร์ ทำให้โค้ดอ่านและเข้าใจง่ายขึ้น
3. **การเพิ่มพารามิเตอร์ในอนาคต**<br>เมื่อต้องการเพิ่มพารามิเตอร์ในคอนสตรักเตอร์ของคลาสลูก สามารถทำได้โดยไม่ต้องแก้ไขคอนสตรักเตอร์ในคลาสแม่ ทำให้การเปลี่ยนแปลงเป็นไปอย่างเป็นระบบและปลอดภัย
4. **การอ่านและการบำรุงรักษา**<br>รหัสที่มีการใช้พารามิเตอร์แบบชื่อมักจะมีความชัดเจนและง่ายต่อการอ่าน นี่จะช่วยให้เข้าใจการทำงานของโค้ดและการบำรุงรักษาได้ง่ายขึ้น

ดังนั้นการใช้งานการสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์แบบชื่อช่วยให้โค้ดเป็นระบบและสามารถปรับปรุงได้ง่าย เพิ่มความชัดเจนและความยืดหยุ่นในการเขียนโปรแกรม

#### `ตัวอย่างที่ 5` เรียกใช้งาน Named Constructor ของคลาสแม่
>ในตัวอย่างที่5 มีคลาสชื่อ "Laptop" ที่มีคอนสตรักเตอร์เริ่มต้นและคอนสตรักเตอร์แบบชื่อหนึ่งตัว มีคลาสอีกอันชื่อ "MacBook" ที่สืบทอดคุณสมบัติจากคลาส "Laptop" และมีคอนสตรักเตอร์ของตัวเองที่สามารถเรียกใช้งานคอนสตรักเตอร์แบบชื่อของคลาสแม่ได้โดยใช้คีย์เวิร์ด "super"
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

##### `คำอธิบายตัวอย่างที่5` เรียกใช้งาน Named Constructor ของคลาสแม่
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

## การสืบทอดคอนสตรักเตอร์ในภาษาโปรแกรม Dart เมื่อเทียบกับภาษาโปรแกรมอื่น ๆ
ในส่วนนี้คุณจะได้เรียนรู้เกี่ยวกับการสืบทอดของคอนสตรักเตอร์ในภาษาอื่น ๆ ด้วยวิธีการเปรียบเทียบโค้ดตัวอย่างในภาษาโปรแกรม Dart เมื่อเทียบกับโค้ด ตัวอย่างในภาษาอื่น ซึ่ง**อาจจะ**แสดงกระบวนการที่ใช้ในการหาผลลัพธ์ที่แตกต่างกัน แต่จะให้ผลลัพธ์ที่เหมือนกัน
### จากตัวอย่างที่ 1-5 ในภาษาโปรแกรม Dart เมื่อเทียบกับภาษา C 
|ในภาษา Dart | ในภาษา C  |
| ```dart
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
|
