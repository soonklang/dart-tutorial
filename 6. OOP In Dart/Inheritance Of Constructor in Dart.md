# Inheritance Of Constructor in Dart
### บทนำ
ในส่วนนี้เราจะศึกษาเรื่องการสืบทอดคอนสตรักเตอร์ (constructor) ในภาษา Dart ว่าเป็นอย่างไรผ่านตัวอย่างที่จะช่วยให้เข้าใจง่ายขึ้น ก่อนที่เราจะลงสู่รายละเอียดของการสืบทอดคอนสตรักเตอร์ ขอให้คุณมีความเข้าใจพื้นฐานเกี่ยวกับคอนสตรักเตอร์และการสืบทอดใน Dart ในการเข้าใจหัวข้อนี้ จะเป็นประโยชน์หากคุณมีพื้นฐานเกี่ยวกับคลาสและวิธีการสร้างอ็อบเจกต์ใน Dart ถ้าคุณยังไม่มีความรู้เกี่ยวกับเรื่องนี้ คุณสามารถศึกษาในแหล่งข้อมูลเพิ่มเติมก่อนที่จะดำเนินการเรียนรู้ในส่วนนี้ได้

### การสืบทอดคอนสตรักเตอร์ในภาษา Dart
การสืบทอด (Inheritance) ของตัวสร้าง (Constructor) ในภาษาโปรแกรม Dart คือกระบวนการที่ทำให้คอนสตรักเตอร์ของคลาสแม่ถูกส่งต่อให้คลาสลูกไปใช้งาน นั่นคือเราสามารถนำคอนสตรักเตอร์จากคลาสแม่มาใช้ในคลาสลูกได้ เปรียบเสมือนการนำโค้ดที่เคยเขียนไว้ในคลาสแม่มาใช้ซ้ำในคลาสลูก

#### `ตัวอย่างที่ 1` การสืบทอดคอนสตรักเตอร์ใน Dart
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

##### `คำอธิบายตัวอย่างที่1` การสร้างคลาส "Laptop" และคลาส "MacBook" ในภาษา Dart โดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ของตัวเอง
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

#### `ตัวอย่างที่ 2` การสืบทอดคอนสตรักเตอร์ที่มีพารามิเตอร์ใน Dart
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

##### `คำอธิบายตัวอย่างที่2` การสร้างคลาส "Laptop" และคลาส "MacBook" ในภาษา Dart โดยทั้งสองคลาสนี้มีคอนสตรักเตอร์ที่รับพารามิเตอร์                                          และแสดงผลลัพธ์เมื่อมีการสร้างอ็อบเจ็กต์
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

