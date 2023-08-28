# Important concepts
ใน tutorial นี้เราจะมาดูเรื่องแนวคิดที่สำคัญของ Dart  โดยที่ภาษา Dart เป็นภาษาโปรแกรมที่มีแนวคิดแบบ Object-Oriented Programming (OOP) ที่ให้ความสำคัญกับการจัดการกับ Object และ Class และใช้ในสร้าง Applications หรือ Project อื่นๆ และจะต้องคำนึงถึงข้อเท็จจริงและแนวคิดดังนี้

## Objects & Class
ใน Dart นั้นทุกอย่างคือวัตถุ และวัตถุทั้งหมดเป็น instance ของ class ซึ่งรวมถึงตัวเลข ฟังก์ชัน และค่าว่างถือเป็นวัตถุ อ็อบเจ็กต์ทั้งหมดจะสืบทอดมาจากคลาส Object ยกเว้นค่า null ถ้าหากใช้ sound null safety

## Null Safety
Dart เวอร์ชัน 2.12 ขึ้นไปที่เปิดใช้งาน null safety เมื่อประกาศตัวแปรจะต้องระบุว่าตัวแปรนั้นจะมีค่า null ซึ่งหมายความว่าตัวแปรไม่สามารถมีค่าว่างได้ 
### Example : สร้างตัวแปรโดยที่ไม่ได้กำหนดค่า
```dart
  void main() {
    String name;  
    print(name);  
  }
```
>จากตัวอย่างจะทำให้เกิดการ runtime error หากต้องการระบุว่าตัวแปรอาจมีค่าเป็น null จะต้องเพื่มเครื่องหมายคำถาม ? ไปที่ประเภทข้อมูล

- Output
  
``` dart
Error: Non-nullable variable 'name' must be assigned before it can be used.
```

 

### Example : สร้างตัวแปรโดยที่ไม่ได้กำหนดค่าโดยการใช้ ?
```dart
  void main() {
    String? name;  // ประกาศตัวแปร name โดยระบุว่าอาจจะมีค่าเป็น null
    print(name);  
  }
```
>จากตัวอย่างมีการเพื่มเครื่องหมาย ? หลังประเภทข้อมูล ทำให้ค่าของ name สามารถเป็น null ได้และจะไม่เกิดการ runtime error

- Output
  
``` dart
null
```

## Type Annotations & Type Inference
### Type Annotations
คือภาษาที่ต้องมีการประกาศ และบอกว่าตัวแปรนี้จะเป็นข้อมูลประเภทไหนซึ่งตัวเราเองจะต้องกำหนดว่าตัวแปร ฟังก์ชัน วัตถุ นั้นมี type เป็นอะไร 
#### Example : การสร้างตัวแปรและกำหนดชนิดข้อมูล 
```dart
void main() {
  String name = "John";
  int age = 30;
  print(name);
  print(age);
}
```
>จากตัวอย่างจะเป็นการกำหนดประเภทข้อมูลไว้แล้ว String กับ int

- Output
  
``` dart
John
30
```


### Type Inference
คือเป็นการปล่อยให้ตัว Dart จัดการเรื่อง type ว่าตัวแปร ฟังก์ชัน วัตถุ ให้เองโดยอัตโนมัติ
โดยที่ compiler สามารถรู้ type ของข้อมูลได้โดยดูจาก literal หรือค่าคงที่ที่กำหนดให้กับตัวแปร
#### Example : การสร้างตัวแปรแต่ไม่ได้กำหนดชนิดข้อมูล
```dart
void main() {
  var name = " John"; 
  var age = 30;
  print(name);
  print(age);
}
```
>จากตัวอย่างจะมีการกำหนดประเภทข้อมูลเป็น var คือตัวแปรที่ไม่ระบุชนิดข้อมูลตอนประกาศตัวแปร และจะสามารรู้ประเภทข้อมูลได้ตอนที่เรากำหนดค่า

- Output
  
``` dart
John
30
```


## Dart supports
คุณลักษณะหรือความสามารถที่ Dart สนับสนุนหรือรองรับมีตัวอย่างที่สำคัญดังนี้
### Generic Type 
คือการระบุ Data type ของตัวแปรที่จะใช้ใน Class หรือ Method เช่น List<"int"> หรือ List<"Object"> จะเป็นวัตถุหรือประเภทชนิดข้อมูลใดก็ได้
#### Example : กำหนดชนิดข้อมูลของ List
```dart
main() { 
  List<int> listEx = <int>[]; // ส่วนของการระบุประเภทข้อมูลของ List
  listEx.add(10); 
  listEx.add(20); 
  listEx.add(50); 
    
  for (int element in listEx) { 
     print(element); 
  } 
}
```
>จากตัวอย่างจะเป็นการกำหนดประเภทข้อมูลของ List

- Output
  
``` dart
10
20
50
```


### Top-level functions 
เป็นฟังก์ชันในระดับสูงสุดของโปรแกรมจะอยู่ด้านบนสุดของลำดับชั้นของคลาสหรือฟังก์ชัน และสามารถสร้างฟังก์ชันที่เชื่อมโยงกับ Class หรือ Object ได้ เช่น ฟังก์ชัน main() 
เราสามารถเขียนฟังก์ชันระดับบนสุดอีกฟังก์ชันหนึ่งไว้ที่ด้านบนของฟังก์ชัน main() ได้และ static methods กับ instance methods สามารถสร้างฟังก์ชันไว้ภายในฟังก์ชัน local functions

#### Example : เปรียบเทียบฟังก์ชันในระดับสูงสุด
```dart
void aTopLevelFunction() {} // A top-level function
main() {
Function anyFunctionInsideTopLevelFunction;

  // เปรียบเทียบ top-level functions.
  anyFunctionInsideTopLevelFunction = aTopLevelFunction;
  if (aTopLevelFunction == anyFunctionInsideTopLevelFunction) {
    print('A top level function is same as any function '
        ' inside a top-level function.');
  }
}
```
>จากตัวอย่างเป็นการสร้างฟังก์ชันไว้นอก ฟังก์ชัน main()  และกำหนดค่าฟังก์ชันใน main() ที่ชื่อ anyFunctionInsideTopLevelFunction ให้เป็น aTopLevelFunction หรือฟังก์ชันระดับสูงสุด และทำการเปรียบเทียบ

- Output

```dart
A top level function is same as any function  inside a top-level function.
```

#### Example : สร้างฟังก์ชันไว้ภายในฟังก์ชัน local functions
```dart
void outerFunction() {
  void innerFunction() {
    print("Inner function");
  }
  print("Outer function");
  innerFunction();
}
void main() {
  outerFunction();
}
```


- Output
  
```dart
Outer function
Inner function
```


### Top-level variables 
ในภาษา Dart คือตัวแปรที่ประกาศที่ด้านนอกของคลาสและฟังก์ชัน ซึ่งอยู่นอกเหนือจากเนื้อหาของคลาสหรือฟังก์ชัน โดยตัวแปรเหล่านี้สามารถเข้าถึงได้ทุกที่ในโปรแกรม แต่ไม่ได้เชื่อมโยงกับคลาสหรืออ็อบเจ็กต์ใดๆ 
#### Example : สร้างตัวแปรนอกฟังก์ชัน main()
```dart
var myVariable = 42; // Top-level variables 

void main() {
  print(myVariable);
}
```
>จากตัวอย่างเราจะสามารถเรียกตัวแปรนอก main() ได้โดยที่ไม่จำเป็นต้องเขียนฟังก์ชันหรือคลาส และไม่ต้องมีการสร้างอ็อบเจ็กต์หรือคลาสอื่น 

- Output
  
```dart
42
```






### Access Modifiers 
คือการกำหนดระดับในการเข้าถึงของ คลาส แอตทริบิวต์ เมธอด โดยมีประโยชน์ในเรื่องของสิทธิในการเข้าใช้งาน และการซ้อนข้อมูล


ใน Dart จะต่างจาก Java หรือ C++ ตรงที่ไม่มีคีย์เวิร์ด public protected และ private หากตัวระบุขึ้นต้นด้วยขีดล่าง (_) จะถูกกำหนดเป็น private 
#### Example : 1 กำหนดระดับการเข้าถึงของ attribute 
```dart
class Point {
  int _x = 0; //กำหนดให้ x เป็น private
  int _y = 0; //กำหนดให้ ั เป็น private

  Point({int x = 0, int y = 0}) { //c
    this._x = x;
    this._y = y; 
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();
}
```

- Output
  
```dart
Point(x=10,y=20)
```

#### Example : 2 พยายามเข้าถึง ฟิลด์ _x และ ฟิลด์ _y ที่เป็น private ในฟังก์ชัน main()

```dart
class Point {
  int _x = 0; //กำหนดให้ x เป็น private
  int _y = 0; //กำหนดให้ y เป็น private

  Point({int x = 0, int y = 0}) { //c
    this._x = x;
    this._y = y; 
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();

  p1._x = 100; // เป็นการแก้ไขตัวแปร x ที่เป็น private
  p1._y = 200; // เป็นการแก้ไขตัวแปร y ที่เป็น private
  p1.show();
}
```
>จากตัวอย่างเป็นการที่พยายามเข้าถึงตัวแปรที่เป็นแบบ private จึงทำให้เปลี่ยนแปลงค่าภายในตัวแปร x กับ y
- Output

```dart
Point(x=10,y=20)
Point(x=100,y=200)
```

ใน Dart จะมีความเป็น private ที่ระดับเดียวกับ library มากกว่าระดับ class การเพิ่ม (_) ให้กับตัวแปรจะทำให้ library เป็นแบบ private ไม่ใช่คลาสแบบ private

เพื่อป้องกันไม่ให้ฟังก์ชันอื่นเข้าถึงฟิลด์ที่เป็น private ของ class Point จะต้องสร้าง library ใหม่และวางคลาสไว้ในนั้น

#### Example : วิธีการป้องกันการเข้าถึงของฟิลด์ที่เป็น private

> 1.  ให้สร้างไฟล์ใหม่ที่เรียกว่า point.dart และเพิ่ม class Point ให้กักับไฟล์
  
```dart
class Point {
  int _x = 0;
  int _y = 0;

  Point({int x = 0, int y = 0}) {
    this._x = x;
    this._y = y;
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}
```

> 2.  import point.dart library ลงใน main.dart เพื่อให้สามารถอ้างอิงถึง class Point

```dart
import 'point.dart';

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();
}
```

>  3.  หากพยายามแก้ไขหรือเข้าถึงตัวแปร _x และ_y จาก main.dart จะเกิด error

```dart
import 'point.dart';

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();

  // errors
  p1._x = 100;
  p1._y = 200;
}
```
