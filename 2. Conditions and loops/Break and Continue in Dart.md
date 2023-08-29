# BREAK AND CONTINUE IN DART

## Dart Break and Continue
 การใช้งาน Break เเละ Continue ในภาษา Dark ใช้ขณะที่ทำงานกับลูปเป็นการทำงานในทันทีเมื่อเจอคำสั่ง
## Break Statement
 คำสั่ง break เป็นคำสั่งที่ให้โปรแกรมออกจาก loop ทันที โดยไม่ทำคำสั่งที่เหลือต่อ ซึ่งคำสั่ง break นี้ สามารถใช้ได้กับ loop หลาย ๆ loop ไม่ว่าจะเป็น while, do while, for, switch และอื่น ๆ

รูปเเบบการเขียนคำสั่งในเเต่ล่ะภาษา

Dart , C , Java | Python
break; | break

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
<details close>
<summary><b>output</b></summary>
 <pre>
1
2
3
4</pre>
</details>

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
<details close>
<summary><b>output</b></summary>
 <pre>
10
9
8</pre>
</details>

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
<details close>
<summary><b>output</b></summary>
 <pre>
1
2
3
4
5</pre>
</details>

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
<details close>
<summary><b>output</b></summary>
 <pre>
Selected month is February.</pre>
</details>

>Example : Break In C For Loop

>Example : Break In Java For Loop

>Example : Break In Python For Loop

## Continue Statement
 คำสั่ง continue; เป็นคำสั่งที่ใช้เพื่อหยุดการทำงานคล้าย ๆ กับคำสั่ง break; แต่จะหยุดการทำงานในการวนรอบรอบปัจจุบัน แล้วไปเริ่มทำงานในรอบต่อไปใหม่ทันที

รูปเเบบการเขียนคำสั่งในภาษา Dark , C , Java 
```dart
  continue;
```
รูปเเบบการเขียนคำสั่งในภาษา python
 ```python
   continue
 ```
### Example 1: Continue In Dart
```dart
void main() {
  for (int i = 1; i <= 3; i++) {
    if (i == 2) {
      continue;
    }
    print(i);
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
1
3</pre>
</details>

### Example 2: Continue In For Loop Dart
```dart
void main() {
  for (int i = 5; i >= 1; i--) {
    if (i == 3) {
      continue;
    }
    print(i);
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
5
4
2
1</pre>
</details>

### Example 3: Continue In Dart While Loop
```dart
void main() {
  int i = 1;
  while (i <= 5) {
    if (i == 3) {
      i++;
      continue;
    }
    print(i);
    i++;
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
1
2
3
4
5</pre>
</details>

C | Java 
------------ | -------------

>Example : Continue In C For Loop

>Example : Continue In Java For Loop

>Example : Continue In Python For Loop

## Reference
