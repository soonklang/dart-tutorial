# Important concepts
ใน tutorial นี้เราจะมาดูเรื่องแนวคิดที่สำคัญของ Dart  โดยที่ภาษา Dart เป็นภาษาโปรแกรมที่มีแนวคิดแบบ Object-Oriented Programming (OOP) ที่ให้ความสำคัญกับการจัดการกับ Object และ Class และใช้ในสร้าง Applications หรือ Project อื่นๆ และจะต้องคำนึงถึงข้อเท็จจริงและแนวคิดดังนี้

## Objects & Class
ใน Dart นั้นทุกอย่างคือวัตถุ และวัตถุทั้งหมดเป็น instance ของ class ซึ่งรวมถึงตัวเลข ฟังก์ชัน และค่าว่างถือเป็นวัตถุ อ็อบเจ็กต์ทั้งหมดจะสืบทอดมาจากคลาส Object ยกเว้นค่า null ถ้าหากใช้ sound null safety

## Null Safety
Dart เวอร์ชัน 2.12 ขึ้นไปที่เปิดใช้งาน null safety เมื่อประกาศตัวแปรจะต้องระบุว่าตัวแปรนั้นจะมีค่า null ซึ่งหมายความว่าตัวแปรไม่สามารถมีค่าว่างได้ 
### Example  
```dart
  void main() {
    String name;  
    print(name);  
  }
```
- Output
  
``` dart
Error: Non-nullable variable 'name' must be assigned before it can be used.
```

จากตัวอย่างจะทำให้เกิดการ runtime error หากต้องการระบุว่าตัวแปรอาจมีค่าเป็น null จะต้องเพื่มเครื่องหมายคำถาม ? ไปที่ประเภทข้อมูล 

### Example 
```dart
  void main() {
    String? name;  // ประกาศตัวแปร name โดยระบุว่าอาจจะมีค่าเป็น null
    print(name);  
  }
```
- Output
  
``` dart
null
```

## Type Annotations & Type Inference
### Type Annotations
คือภาษาที่ต้องมีการประกาศ และบอกว่าตัวแปรนี้จะเป็นข้อมูลประเภทไหนซึ่งตัวเราเองจะต้องกำหนดว่าตัวแปร ฟังก์ชัน วัตถุ นั้นมี type เป็นอะไร 
#### Example 
```dart
void main() {
  String name = "John";
  int age = 30;
  print(name);
  print(age);
}
```
- Output
  
``` dart
John
30
```
จากตัวอย่างจะเป็นการกำหนดประเภทข้อมูลไว้แล้ว String กับ int  

## Type Inference
คือเป็นการปล่อยให้ตัว Dart จัดการเรื่อง type ว่าตัวแปร ฟังก์ชัน วัตถุ ให้เองโดยอัตโนมัติ
โดยที่ compiler สามารถรู้ type ของข้อมูลได้โดยดูจาก literal หรือค่าคงที่ที่กำหนดให้กับตัวแปร
#### Example 
```dart
void main() {
  var name = " John"; 
  var age = 30;
  print(name);
  print(age);
}
```
- Output
  
``` dart
John
30
```
จากตัวอย่างจะมีการกำหนดประเภทข้อมูลเป็น var คือตัวแปรที่ไม่ระบุชนิดข้อมูลตอนประกาศตัวแปร และจะสามารรู้ประเภทข้อมูลได้ตอนที่เรากำหนดค่า

## Dart supports
คุณลักษณะหรือความสามารถที่ Dart สนับสนุนหรือรองรับ ยกตัวอย่างที่สำคัญดังนี้
### Generic Type 
คือการระบุ Data type ของตัวแปรที่จะใช้ใน Class หรือ Method เช่น List<"int"> หรือ List<"Object"> จะเป็นวัตถุหรือประเภทชนิดข้อมูลใดก็ได้
#### Example 
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
- Output
  
``` dart
10
20
50
```
จากตัวอย่างจะเป็นการกำหนดประเภทข้อมูลของ List

### Top-level variables 
ในภาษา Dart คือตัวแปรที่ประกาศที่ด้านนอกของคลาสและฟังก์ชัน ซึ่งอยู่นอกเหนือจากเนื้อหาของคลาสหรือฟังก์ชัน โดยตัวแปรเหล่านี้สามารถเข้าถึงได้ทุกที่ในโปรแกรม แต่ไม่ได้เชื่อมโยงกับคลาสหรืออ็อบเจ็กต์ใดๆ
#### Example
```dart
var myVariable = 42; // Top-level variables 

void main() {
  print(myVariable);
}
```
- Output
  
```dart
42
```

จากตัวอย่างเราจะสามารถเรียกตัวแปรนอก main() ได้โดยที่ไม่จำเป็นต้องเขียนฟังก์ชันหรือคลาส และไม่ต้องมีการสร้างอ็อบเจ็กต์หรือคลาสอื่น

### Access Modifiers 
