## Enum in Dart  

Enum  คือ type ประเภทหนึ่ง เหมือนกับ class ใช้สำหรับกำหนดค่า constant values ที่เรารู้หรือจะเป็นค่า status ต่างๆที่เรารู้อยู่ก่อนแล้วก็ได้  เมื่อเรารู้ค่าล่วงหน้าอยู่แล้ว ว่า values ของเรามีอะไรบ้าง เราก็กำหนดมันเข้าไปได้ตั้งแต่ต้นเลย  พูดง่ายๆคือกำหนดค่าไว้ใช้งาน ซึ่งเป็นการกำหนดไว้ล่วงหน้า ประโยชน์ของมันคือ ทำให้ code เราอ่านง่ายและเข้าใจได้ทัน


## รูปแบบในการใช้ ของ Enum ในภาษา Dart
```dart
enum cars {
  Toyota,
  Honda,
  Nissan,
  Ferrari,
  Bugatti,
  Benz,
  Volvo
}
```
## ตัวอย่างการใช้ Enum
```dart
enum cars {
  Toyota,
  Honda,
  Nissan,
  Ferrari,
  Bugatti,
  Benz,
  Volvo
}

void main() {
  var Mycartoday = cars.Volvo;
  switch (Mycartoday) {
    case cars.Toyota:
      print("Today I choose Toyota.");
      break;
    case cars.Honda:
      print("Today I choose Honda.");
      break;
    case cars.Nissan:
      print("Today I choose Nissan.");
      break;
    case cars.Ferrari:
      print("Today I choose Ferrari.");
      break;
    case cars.Bugatti:
      print("Today I choose Bugatti.");
      break;
    case cars.Benz:
      print("Today I choose Benz.");
      break;
    case cars.Volvo:
      print("Today I choose Volvo.");
      break;
  }
}
```

Output  
```
Today I choose Volvo.
```

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum


```dart
enum Colors { Green, Red, Blue, Yellow, Pink, Black, Rainbow }

void main() {
 // Colors.values: จะคืนค่าทั้งหมดที่อยู่ใน Enum(Colors).
  for (Colors color in Colors.values) {
    print(color);
  }
}

```
Output  
```
Colors.Green
Colors.Red
Colors.Blue
Colors.Yellow
Colors.Pink
Colors.Black
Colors.Rainbow
```
