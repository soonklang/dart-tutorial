[Assert_in_Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12880887/Assert_in_Dart.pptx)# Assert in Dart
## Assert
ใน Dart "assert" เป็นคำสั่งที่ถูกใช้เพื่อทดสอบเงื่อนไขขณะที่โปรแกรมกำลังทำงานและเป็นส่วนหนึ่งของการพัฒนา (development mode) เท่านั้น ถ้าเงื่อนไขที่ระบุใน "assert" เป็นเท็จ (false) โปรแกรมจะหยุดทำงานและแสดงข้อความข้อผิดพลาด
## How to Run File in Assert Mode
```css
dart --enable-asserts file_name.dart
```
## Syntax
  **1) assert(condition);**
  
  ```dart
  void main(){
    int x = 20;
    int y = 10;
    assert(x > y);
  }
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details open>
  <summary><strong>Output</strong></summary>
  <pre><code>Uncaught Error: Assertion failed</code></pre>
</details>

**2) assert(condition, "message");**

```dart
void main(){
  int x = 5;
  int y = 10;
  assert(x > y, "x should be greater than y");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นเท็จ

<details open>
  <summary><strong>Output1</strong></summary>
  <pre><code>Uncaught Error: Assertion failed: "x should be greater than y"</code></pre>
</details>

```dart
void main(){
  int x = 20;
  int y = 10;
  assert(x > y, "x should be greater than y");
 print("Program continues after than assert");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details open>
  <summary><strong>Output2</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### More Examples
อาจจะประกาศเงื่อนไขเพิ่มเติ่มแบบด้านล่างได้สำหรับคำสั่ง "assert"

 ```dart
// ตรวจสอบว่า text มีค่าที่ไม่ใช่ null
 assert(text != null);
```

```dart
// ตรวจสอบว่า number < 100
assert(number < 100);
```

```dart
// ตรวจสอบว่านี่เป็น URL ที่เริ่มต้นด้วย https
assert(urlString.startsWith('https'));
```

### *< Note1 >*

**condition:** ค่าที่ต้องเป็นจริงเพื่อให้โปรแกรมทำงานต่อไป ถ้าเงื่อนไขเป็นเท็จจะหยุดทำงาน

**message:** ข้อความที่สามารถระบุได้ เพื่ออธิบายเงื่อนไขที่ถูกตรวจสอบ ถ้าเงื่อนไขเป็นเท็จจึงถูกแสดง

# Example: Assert in C, Java, and Python

### C : Syntax assert(int expression);

```c
#include<stdio.h>
#include<assert.h>
void main(){
    int x = 20;
    int y = 10;
    assert(x > y);
    printf("Program continues after than assert\n");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details open>
  <summary><strong>Output</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### Java : Syntax assert booleanExpression; and assert booleanExpression: expression;

 >expression: String ที่แทนข้อความแสดงรายละเอียดของความผิดพลาด

 >javac -source 1.4 Test.java

 >java -ea Test

*ใช้ได้เฉพาะรุ่น 1.4 เป็นต้นไป*

```java
public class Main{
  public static void main(String[] args){
    int x = 20;
    int y = 10;
    assert x > y : "x should be greater than y";
    System.out.println("Program continues after than assert");
 }
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details open>
  <summary><strong>Output</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### Python : Syntax assert condition, "message"

```java
x = 20
y = 10
assert x > y, "x should be greater than y"
print("Program continues after than assert")
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details open>
  <summary><strong>Output</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### *< Note2 >*

ใน C, Java และ Python ถึงจะเป็นภาษาโปรแกรมคนละภาษากัน แต่การใช้งานเงื่อนไขและการทดสอบคือคล้ายกันทุกภาษา สามารถใช้คำสั่ง “assert” หรือการใช้เงื่อนไขกับคำสั่ง “if” จะทำให้โปรแกรมหยุดทำงานเมื่อเงื่อนไขเป็นเท็จและแสดงข้อความข้อผิดพลาด

### *< Caution >*

 >การใช้งาน “assert” ในภาษา C และ Java อาจถูกปิดใช้งานในการรันโปรแกรมบนระบบการใช้งานจริง (production environment)

 >การใช้งาน “assert” ในภาษา Dart และ Python จะแสดงผลผิดพลาดทันทีเมื่อเงื่อนไขไม่ถูกต้อง

# Comparing Assert in Dart with C, Java, and Python

## Syntax
>Dart: assert(condition); and assert(condition, "message");

>C: assert(int expression);

>Java: assert booleanExpression; and assert booleanExpression: expression;

>Python: assert condition, "message"

จะเห็นว่า Syntax ของแต่ละภาษาใช้งานแตกต่างกันเล็กน้อย แต่ในแง่ของหลักการทั้งใน dart, c, java และ python คล้ายกันโดยตรวจสอบเงื่อนไขและการแสดงข้อความข้อผิดพลาดเมื่อเงื่อนไขเป็นเท็จ แต่มีความแตกต่างในวิธีการเปิดใช้งานโหมดเพื่อใช้งาน

>C: ในการประกาศเงื่อนไขจะไม่สามารถระบุข้อความข้อผิดพลาดเพิ่มเติมได้และอาจจะถูกปิดใช้งานการรันระบบจริงๆ

>Java: ตามจริงแล้วไม่มีคำสั่ง "assert" ต้องทำการเปิดโหมดการใช้งานโหมด "assertions" ของ java เพื่อให้ทำงานได้

>การเปิดโหมดใช้งานโดย: java -ea หรือ java -enableassertions

## *< Link Video >*
https://youtu.be/Ebv6g1nUe5A

## *< Slides >*
[Assert in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12881415/Assert.in.Dart.pptx)

[Assert in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12881291/Assert.in.Dart.pdf)

## *< Reference >*
https://dart-tutorial.com/conditions-and-loops/assert-in-dart/

https://dart.dev/language/error-handling

https://www.geeksforgeeks.org/assert-statements-in-dart/

https://dartpad.dev/?id=8be7c091b45258d69cbeeeade76c198f

https://www.onlinegdb.com/

https://www.tutorialspoint.com/c_standard_library/c_macro_assert.htm

https://www.cp.eng.chula.ac.th/~somchai/spj/slides/Java/intro/java_v4_08_Exception.pdf

https://holmskaya.org/what-is-assert-in-java-with-example

https://www.mindphp.com/developer/tips-python/7888-assert-function-python.html

