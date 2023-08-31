# Constant Constructor in Dart
ตัวสร้างคงที่ **(Constant Constructor)** เป็น Constructor ที่สร้างวัตถุคงที่ **(Constant Object)** ตัววัตถุคงที่จะไม่มีการเปลี่ยนแปลงค่าใดๆในตัววัตถุ

# Declaring Constant Constructor in Dart
การประกาศ Constant Constructor จะมี keyword: **const** อยู่ด้านหน้า constructor
# Syntax
```dart
const name_constructor(this.fieldname);
```
ในการประกาศ Constant Constructor จะมีกฎอยู่ 3 ข้อดังนี้
- คุณสมบัติ(field)ทั้งหมดในคลาส ต้องเป็น **final** ทั้งหมด
- ภายใน Constructor จะต้องไม่มีการกำหนดใดๆ หรือ ว่างเปล่า
- เฉพาะคลาสที่สร้างตัวมีการประกาศ **const** ไว้เท่านั้นจึงสร้างวัตถุคงที่ได้

ตัวอย่างในการประกาศ Constant Constructor 
```dart
class Test  {
  final int x;
  final int y;

  const Test(this.x, this.y);
}

void main(){

  // Object of class test
  const Test test = Test(0,1);
}
```
# Example 1: Constant Constructor In Dart
ในตัวอย่างนี้ คลาส "Point" ถูกออกแบบมาเพื่อเก็บข้อมูลพิกัด (x และ y) แบบที่ไม่สามารถเปลี่ยนแปลงได้หลังจากสร้างออบเจกต์แล้ว โดยใช้ค่าคงที่ (final) เพื่อป้องกันการเปลี่ยนแปลงค่า คอนสตรักเตอร์จะใช้ในการกำหนดค่า x และ y เมื่อสร้างออบเจกต์ใหม่ 
```dart
class Point {
  final int x;
  final int y;

  const Point(this.x, this.y);
}

void main() {
  // p1 and p2 has the same hash code.
  Point p1 = const Point(1, 2);
  print("The p1 hash code is: ${p1.hashCode}");

  Point p2 = const Point(1, 2);
  print("The p2 hash code is: ${p2.hashCode}");
  // without using const
  // this has different hash code.
  Point p3 = Point(2, 2);
  print("The p3 hash code is: ${p3.hashCode}");

  Point p4 = Point(2, 2);
  print("The p4 hash code is: ${p4.hashCode}");
}
```
<details>
  <summary><strong>Output</strong></summary>
    <pre><code> 
      The p1 hash code is: 305520010
      The p2 hash code is: 30552001
      The p3 hash code is: 343990408
      The p4 hash code is: 629594949
    </code></pre>
</details>

: จากผลลัพธ์ทำให้ได้ข้อสังเกตุว่า การใช้ **const** ในการสร้างออบเจกต์ทำให้เกิดการแชร์ออบเจกต์เดียวกันระหว่างที่ใช้งาน จึงส่งผลให้มี **hashCode** เดียวกัน ในทางตรงกันข้าม การสร้างออบเจกต์โดยไม่ใช้ **const** จะทำให้เกิดออบเจกต์ที่แยกกัน และมี hashCode ที่แตกต่างกัน

# Example 2: Constant Constructor With Named Parameters In Dart
ในตัวอย่างด้านล่างนี้ เรามีคลาสชื่อ "Student" ที่มีคุณสมบัติสามอันคือ name, age และ rollNumber คลาสนี้มีคอนสตรักเตอร์ค่าคงที่หนึ่งตัว โดยคอนสตรักเตอร์นี้ถูกใช้ในการกำหนดค่าสามคุณสมบัติที่กล่าวมาแล้ว นอกจากนี้เรายังมีออบเจกต์ของคลาส "Student" ที่ชื่อว่า student
```dart
class Student {
  final String? name;
  final int? age;
  final int? rollNumber;

  // Constant Constructor
  const Student({this.name, this.age, this.rollNumber});
}

void main() {
  // Here student is object of Student.
  const Student student = Student(name: "John", age: 20, rollNumber: 1);
  print("Name: ${student.name}");
  print("Age: ${student.age}");
  print("Roll Number: ${student.rollNumber}");
}
```

> เพิ่มเติม!!!!: **?** มีหมายความว่าตัวแปรเหล่านี้สามารถเป็นค่า **null** ได้


<details>
  <summary><strong>Output</strong></summary>
  <pre><code> 
    Name: John
    Age: 20
    Roll Number: 1
  </code></pre>
</details>
: คลาส Student มีคอนสตรักเตอร์ที่เป็นค่าคงที่ โดยมีการสร้างออบเจกต์โดยใช้รูปแบบชื่อพารามิเตอร์ ซึ่งแตกต่างจากรูปแบบที่สร้างโดยใช้การอ้างถึงตำแหน่งของพารามิเตอร์ ในคอนสตรักเตอร์นี้เราสามารถระบุพารามิเตอร์ที่ต้องการให้ค่าได้ และสามารถปล่อยว่างไว้เพื่อให้ค่าคงที่นั้นเป็น null ได้

# Benefits Of Constant Constructor In Dart
ปรับปรุงประสิทธิภาพของโปรแกรม เพื่อให้โปรแกรมทำงานได้เร็วขึ้น

# Reference
https://dart-tutorial.com/object-oriented-programming/constant-constructor-in-dart/
