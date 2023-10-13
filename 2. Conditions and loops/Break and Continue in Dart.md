# BREAK AND CONTINUE IN DART

## Dart Break and Continue
 การใช้งาน Break เเละ Continue ในภาษา Dark ใช้ขณะที่ทำงานกับลูปเป็นการทำงานในทันทีเมื่อเจอคำสั่ง
## Break Statement
 คำสั่ง break เป็นคำสั่งที่ให้โปรแกรมออกจาก loop ทันที โดยไม่ทำคำสั่งที่เหลือต่อ ซึ่งคำสั่ง break นี้ สามารถใช้ได้กับ loop หลาย ๆ loop ไม่ว่าจะเป็น while, do while, for, switch และอื่น ๆ

รูปเเบบการเขียนคำสั่ง

Dart , C , Java | Python
-|-
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
  var noOfMonth = 1;
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
Selected month is January.</pre>
</details>

### * Example : Break In C For Loop
> C
```c
#include <stdio.h>
int main() {
  int i;
  for (i = 0; i < 10; i++) {
    if (i == 4) {
      break;
    }
    printf("%d\n", i);
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
3</pre>
</details>

### * Example : Break In Java For Loop
> Java
```java
public class Main {
  public static void main(String[] args) {
    for (int i = 0; i < 10; i++) {
      if (i == 4) {
        break;
      }
      System.out.println(i);
    }  
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
3</pre>
</details>

### * Example : Break In Python For Loop
> Python
```python
count = 0
while count <= 100:
    print (count)
    count += 1
    if count == 3:
        break
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
3</pre>
</details>

## Continue Statement
 คำสั่ง continue; เป็นคำสั่งที่ใช้เพื่อหยุดการทำงานคล้าย ๆ กับคำสั่ง break; แต่จะหยุดการทำงานในการวนรอบรอบปัจจุบัน แล้วไปเริ่มทำงานในรอบต่อไปใหม่ทันที

รูปเเบบการเขียนคำสั่ง

Dart , C , Java | Python
-|-
continue; | continue

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

### * Example : Continue In C For Loop
> C
```c
#include <stdio.h>
int main() {
  int i;
  for (i = 0; i <= 5; i++) {
    if (i == 4) {
      continue;
    }
    printf("%d\n", i);
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
3
5</pre>
</details>

### * Example : Continue In Java For Loop
> Java
```java
public class Main {
  public static void main(String[] args) {
    for (int i = 0; i <=5; i++) {
      if (i == 4) {
        continue;
      }
      System.out.println(i);
    }  
  }
}
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
3
5</pre>
</details>

### * Example : Continue In Python For Loop
> Python
```java
for i in range(0, 5):
    if i == 3:
        continue
    print(i)
```
<details close>
<summary><b>output</b></summary>
 <pre>
0
1
2
4</pre>
</details>

## Clips And Slide
Vdo link : https://youtu.be/U9qI0j3olEc?si=UyryZNU85180Wwa7

Download slide here : [Break and Continue in Dart](https://github.com/Natthawut630/file/raw/main/BREAK%20AND%20CONTINUE%201.pptx)

## Reference
- https://dart-tutorial.com/conditions-and-loops/break-and-continue-in-dart/
- https://www.w3schools.com/c/c_break_continue.php
- https://www.w3schools.com/java/java_break.asp
- https://www.w3schools.in/python/break-and-continue#google_vignette

- 
