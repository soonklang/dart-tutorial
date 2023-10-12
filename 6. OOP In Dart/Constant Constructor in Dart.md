# Constant Constructor in Dart
ตัวสร้างคงที่ **(Constant Constructor)** เป็น Constructor ที่สร้างวัตถุคงที่ **(Constant Object)** ตัววัตถุคงที่จะไม่มีการเปลี่ยนแปลงค่าใดๆในตัววัตถุ

# Declaring Constant Constructor in Dart
การประกาศ Constant Constructor จะมี keyword: **const** อยู่ด้านหน้า constructor
# Syntax
```dart
const name_constructor(paramiter);
```
ในการประกาศ Constant Constructor จะมีกฎอยู่ 3 ข้อดังนี้
- คุณสมบัติ(Attribute)ทั้งหมดในคลาส ต้องเป็น **final** ทั้งหมด
- ภายใน Constant Constructor จะต้องไม่มีการกำหนดใดๆ หรือ ว่างเปล่า
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
ในตัวอย่างนี้ คลาส "Point" ถูกออกแบบมาเพื่อเก็บข้อมูลพิกัด (x และ y) แบบที่ไม่สามารถเปลี่ยนแปลงได้หลังจากสร้างObjectแล้ว โดยใช้ค่าคงที่ (final) เพื่อป้องกันการเปลี่ยนแปลงค่า คอนสตรักเตอร์จะใช้ในการกำหนดค่า x และ y เมื่อสร้างออบเจกต์ใหม่ 
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

: จากผลลัพธ์ทำให้ได้ข้อสังเกตุว่า การสร้างวัตถุเป็น Costant จะทำให้วัตถุที่มีค่าเหมือนกันจะมีการใช้หน่วยความจำในตำเเหน่งเดียวกันค่าhashcodeจึงเท่ากัน
# Example 2: Constant Constructor With Named Parameters In Dart
ในตัวอย่างด้านล่างนี้ เรามีคลาสชื่อ "Student" ที่มีคุณสมบัติสามอันคือ name, age และ rollNumber คลาสนี้มี Costant constructor หนึ่งตัว โดยถูกใช้ในการกำหนดค่าสามคุณสมบัติที่กล่าวมาแล้ว นอกจากนี้เรายังมี Object ของคลาส "Student" ที่ชื่อว่า student ซึ่งจะมีการส่งค่าผ่านชื่อพารามิตเตอร์ โดยชื่อของพารามิตเตอร์จะตรงกัน และ มีลำดับที่ถูกต้อง
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
>[!NOTE]
> เพิ่มเติม!!!!: **?** มีหมายความว่าตัวแปรเหล่านี้สามารถเป็นค่า **null** ได้


<details>
  <summary><strong>Output</strong></summary>
  <pre><code> 
    Name: John
    Age: 20
    Roll Number: 1
  </code></pre>
</details>

# Benefits Of Constant Constructor In Dart
ปรับปรุงประสิทธิภาพของโปรแกรม เพื่อให้โปรแกรมทำงานได้เร็วขึ้น

# การสร้างConstant Object ในภาษาอื่นๆ 
ในกรณีนี้จะขอพูดถึงใน C++
## C++
ในภาษา C++ จะมีการสร้างวัตถุคงที่(Constant Object)โดยใช้Keyword: **const**
```C++
  // keyword class_name name_Object();
  const date birthday(7,3,9);
```
ซึ่งข้อแตกต่างระหว่าง Dart กับ C++
1. การสร้างConstant Object ใน C++ ไม่จำเป็นต้องมี Constructor ที่เป็น **const** เหมือนในDart

Dart
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
} 
```
C++
```C++
#include <iostream>
using namespace std;
 
class Test {
    int value;
 
public:
    Test(int v = 0) { value = v; }
 
    // const member function
    int getValue() const { return value; }
};
 
int main()
{
    // non const object
    const Test t(20);
    cout << t.getValue();
    return 0;
}
```
2. Constant Object ใน C++ จะสามารถเรียกใช้ฟังก์ชันที่มีการประกาศ const ไว้ในฟังก์ชันเท่านั้น ถ้าไม่ได้ประกาศไว้จะไม่สามารถเรียกใช้ฟังก์ชันนั้นได้ แต่ในDart สามารถใช้ได้ปกติ
   
```C++
#include <iostream>
using namespace std;
 
class Test {
    int value;
 
public:
    Test(int v = 0) { value = v; }
 
    // const member function
    int getValue()  { return value; }
};
 
int main()
{
    //  const object
    const Test t(20);
    cout << t.getValue();
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code> 
main.cpp: In function 'int main()':
main.cpp:19:23: error: passing 'const Test' as 'this' argument discards qualifiers []8;;https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html#index-fpermissive-fpermissive]8;;]
   19 |     cout << t.getValue();
      |             ~~~~~~~~~~^~
main.cpp:12:9: note:   in call to 'int Test::getValue()'
   12 |     int getValue() { return value; }
      |         ^~~~~~~~
  </code></pre>
</details>

Dart
```dart
  class Student {
  final String? name;
  final int? age;
  final int? rollNumber;

  // Constant Constructor
  const Student({this.name, this.age, this.rollNumber});

  getname(){
      return name;
  }
}

void main() {
  // Here student is object of Student.
  const Student student = Student(name: "John", age: 20, rollNumber: 1);
  print(student.getname());
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code> 
  John
  </code></pre>
</details>

# Link Video
-https://drive.google.com/drive/folders/1pFweMcq_S47yTn77I-L3Lhj2r1XQxDK6?usp=sharing
# Slide
[640710061_Constant Constructor in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12753164/640710061_Constant.Constructor.in.Dart.pptx)

# Reference
- https://dart-tutorial.com/object-oriented-programming/constant-constructor-in-dart
- https://www.peachpit.com/articles/article.aspx?p=2468332&seqNum=5
- https://dart.dev/language/constructors
- https://faculty.cs.niu.edu/~mcmahon/CS241/Notes/const_objects_and_member_functions.html
- https://www.geeksforgeeks.org/const-member-functions-c/
