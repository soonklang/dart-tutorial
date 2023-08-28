## Enum in Dart  

Enum คือ ...

## syntax ของ enum
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
## example of enum
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

## how to print all of Enum


```dart
enum Days { Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday }

void main() {
 // Days.values: It returns all the values of the enum.
  for (Days day in Days.values) {
    print(day);
  }
}

```
