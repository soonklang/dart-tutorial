# Assert in Dart
## Assert
ใน Dart "assert" เป็นคำสั่งที่ถูกใช้เพื่อทดสอบเงื่อนไขขณะที่โปรแกรมกำลังทำงานและเป็นส่วนหนึ่งของการพัฒนา (development mode) เท่านั้น ถ้าเงื่อนไขที่ระบุใน "assert" เป็นเท็จ (false) โปรแกรมจะหยุดทำงานและแสดงข้อความข้อผิดพลาด
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

<details>
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

<details>
  <summary><strong>Output1</strong></summary>
  <pre><code>Uncaught Error: Assertion failed: "x should be greater then y"</code></pre>
</details>

```dart
void main(){
  int x = 20;
  int y = 10;
  assert(x > y, "x should be greater then y");
 print("Program continues after than assert");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details>
  <summary><strong>Output2</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### *< Note1 >*

**condition:** ค่าที่ต้องเป็นจริงเพื่อให้โปรแกรมทำงานต่อไป ถ้าเงื่อนไขเป็นเท็จจะหยุดทำงาน

**message:** ข้อความที่สามารถระบุได้ เพื่ออธิบายเงื่อนไขที่ถูกตรวจสอบ ถ้าเงื่อนไขเป็นเท็จจึงถูกแสดง

## Example: Assert in C, Java and Python

### C : Syntax assert(int expression);

```c
#include<stdio.h>
#include<assert.h>
int main(){
    int x = 20;
    int y = 10;
    assert(x > y);
    printf("Program continues after than assert\n");
    return 0;
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x > y เป็นจริง

<details>
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

<details>
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

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Program continues after than assert</code></pre>
</details>

### *< Note2 >*

ใน C, Java และ Python ถึงจะเป็นภาษาโปรแกรมคนละภาษากัน แต่การใช้งานเงื่อนไขและการทดสอบคือคล้ายกันทุกภาษา สามารถใช้คำสั่ง “assert” หรือการใช้เงื่อนไขกับคำสั่ง “if” จะทำให้โปรแกรมหยุดทำงานเมื่อเงื่อนไขเป็นเท็จและแสดงข้อความข้อผิดพลาด

### *< Caution >*

 >การใช้งาน “assert” ในภาษา C และ Java อาจถูกปิดใช้งานในการรันโปรแกรมบนระบบการใช้งานจริง (production environment)

 >การใช้งาน “assert” ในภาษา Dart และ Python จะแสดงผลผิดพลาดทันทีเมื่อเงื่อนไขไม่ถูกต้อง

### *< Reference >*
https://dart-tutorial.com/conditions-and-loops/assert-in-dart/
https://dart.dev/language/error-handling
https://www.geeksforgeeks.org/assert-statements-in-dart/
https://dartpad.dev/?id=8be7c091b45258d69cbeeeade76c198f
https://www.onlinegdb.com/
https://www.tutorialspoint.com/c_standard_library/c_macro_assert.htm
https://www.cp.eng.chula.ac.th/~somchai/spj/slides/Java/intro/java_v4_08_Exception.pdf
https://www.mindphp.com/developer/tips-python/7888-assert-function-python.html





