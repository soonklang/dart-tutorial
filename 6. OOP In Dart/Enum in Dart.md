## Enum in Dart  

Enum คือ ...

## รูปแบบในการใช้ ของ Enum
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
 // Colors.values: It returns all the values of the enum.
  for (Colors color in Colors.values) {
    print(color);
  }
}

```
