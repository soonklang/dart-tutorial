# BREAK AND CONTINUE IN DART

## Dart Break and Continue
 การใช้งาน Break เเละ Continue ใน๓าษา Dark ใช้ขณะที่ทำงานกับลูปเป็นการทำงานในทันทีเมื่อเจอคำสั่งนี้
## Break Statement
 การทำงานของ Break คือการหยุดคำสั่งนั้นในทันทีเช่นเมื่ออยู่ในลูปจะทำการหยุดลูปนั้นในทันทีเเละเข้าสู่ขั้นตอนต่อไป
 รูปเเบบการเขียนภาษา Dark , C , Java 
 ```dart
   break;
 ```
 รูปเเบบการเขียนภาษา python
 ```python
   break
 ```
### Example 1: Break In Dart For Loop
```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    if (i == 5) {
      break;
    }
    print(i);
  }
}
```
### Example 2: Break In Dart Negative For Loop
```dart
void main() {
  for (int i = 10; i >= 1; i--) {
    if (i == 7) {
      break;
    }
    print(i);
  }
}
```
### Example 3: Break In Dart While Loop
```dart
void main() {
 int i =1;
 while(i<=10){
  print(i);
   if (i == 5) {
      break;
    }
    i++;
 }
}
```
### Example 4: Break In Switch Case
```dart
void main() {
  var noOfMoneth = 2;
  switch (noOfMoneth) {
    case 1:
      print("Selected month is January.");
      break;
    case 2:
      print("Selected month is February.");
      break;
    default:
      print("Invalid month.");
      break;
  }
}
```
## Continue Statement
```dart
  continue;
```
### Example 1: Continue In Dart
```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    if (i == 5) {
      continue;
    }
    print(i);
  }
}
```
### Example 2: Continue In For Loop Dart
```dart
void main() {
  for (int i = 10; i >= 1; i--) {
    if (i == 4) {
      continue;
    }
    print(i);
  }
}
```
### Example 3: Continue In Dart While Loop
```dart
void main() {
  int i = 1;
  while (i <= 10) {
    if (i == 5) {
      i++;
      continue;
    }
    print(i);
    i++;
  }
}
```
## Reference
