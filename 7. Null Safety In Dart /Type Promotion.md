# Type Promotion

เป็นการแปลงชนิดข้อมูล โดยข้อมูลที่สร้างขึ้นมามีชนิดข้อมูลเดียวกับค่าที่กำหนด ซึ่งสามารถเปลี่ยนชนิดข้อมูลให้เป็นชนิดอื่นได้

## ตัวอย่างที่ 1.1

```dart
void main(){
  String text;
  print("ข้อความ : $text"); // Error
}
```

จากตัวอย่างที่ 1.1 มีการประกาศตัวแปร "text" ชนิดข้อมูล Stringแต่ไม่ได้ระบุค่า จึงทำให้ตัวแปรนี้มีชนิดข้อมูลเป็น null เมื่อ print ค่าจึงทำให้เกิด error ขึ้นมา

## ตัวอย่างที่ 1.2

```dart
void main(){
  String text;
  text = "Hi!";
  print("ข้อความ : $text");
}
```

จากตัวอย่างที่ 1.2 มีกำหนดค่าตัวแปร "text" ในบรรทัดที่ 3 ซึ่งทำให้สามารถ print ค่าได้ 

#### จากตัวอย่างที่ 1 ที่มีการกำหนดค่าลงไปในตัวแปร

```bash

ถือว่าเป็นการ Promoting nullable types เป็น non-nullable types

```

ตัวแปรที่เป็นค่า null นั้นไม่เท่ากับ ค่า null ที่เปลี่ยนเป็น non-nullable type ซึ่งค่านั้นสามารถใส่ค่าอื่นและใช้ในฟังก์ชันได้ แต่การเปลี่ยนเหมาะกับค่าคงที่ local variables และ พารามิเตอร์ parameters มากกว่า

## ตัวอย่างที่ 2.1

```dart
void main(){
  Object name = "Dart";
  print("ชื่อตัวแปร $name");
  print("มีจำนวนตัวอักษร ${name.length}" ตัว); // Error
}
```
จากตัวอย่างที่ 2.1 มีการประกาศตัวแปร "name" ชนิดข้อมูลเป็น Object เมื่อ print ค่าออกมา แต่บรรทัดที่ 4 จึงทำให้เกิด error เนื่องจาก Object ไม่มี คำสั่ง .length ในชนิดข้อมูล

## ตัวอย่างที่ 2.2

```dart
void main(){
  Object name = "Dart";
  print("ชื่อตัวแปร $name");
  if (name is String){
    print("มีจำนวนตัวอักษร ${name.length} ตัว"); 
  }
}
```

จากตัวอย่างที่ 2.2 มีการเพิ่มเงื่อนไข if เข้ามาในบรรทัดที่ 4-6 ซึ่งเป็นเงื่อนไขเปลี่ยนชนิดข้อมูลจาก Object ไปเป็น String ทำให้ name ที่มีชนิดข้อมูล String สามารถใช้คำสั่ง .length ได้

* name ชนิดข้อมูลที่เป็น String ใช้ได้แค่ภายในเงื่อนไขเท่านั้น

#### จากตัวอย่างที่ 2 ทำให้ชนิดข้อมูลจาก Object เป็น String 
```bash

ถือว่าเป็นการ promoting general types เป็น specific subtypes

```
## Presentation Slide
[Type_Promotion.pdf](https://github.com/soonklang/dart-tutorial/files/12775141/Type_Promotion.pdf)

## Link Video
[Type-Promotion Video](https://www.youtube.com/watch?v=AR9E8RRx5i8)

## ข้อมูลอ้างอิง
[dart-tutorial](https://dart-tutorial.com/null-safety/type-promotion-in-dart/) 

[dart-dev](https://dart.dev/effective-dart/usage#consider-assigning-a-nullable-field-to-a-local-variable-to-enable-type-promotion)

