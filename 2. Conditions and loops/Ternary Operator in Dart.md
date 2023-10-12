# TERNARY OPERATOR IN DART

## Ternary Operator In Dart
ในหัวข้อนี้จะอธิบายเกี่ยวกับ Ternary Operator ในภาษา Dart โดย Ternary Operator คือ วิธีในการจัดการเงื่อนไขและคืนค่าในบรรทัดเดียว เพื่อให้โค้ดอ่านได้ง่ายขึ้น และส่วนใหญ่จะใช้แทนที่คำสั่ง if-else หรือเรียกว่า if-else แบบลดรูป ซึ่งจะมีรูปแบบเหมือนกับคำสั่ง if-else แต่มีการทำงานที่สั้นและกระชับกว่า โดยใช้เครื่องหมาย ? และ : ในการตรวจสอบเงื่อนไข เพื่อเลือกคืนค่าใดค่าหนึ่ง ซึ่งขึ้นอยู่กับผลลัพธ์ของเงื่อนไขที่กำหนด

> [!IMPORTANT]
> จุดประสงค์หลักของ Ternary Operator คือ ลดจำนวนบรรทัดในการเขียนโค้ดและใช้ในกรณีที่เงื่อนไขไม่ซับซ้อน

## ประโยชน์ของ Ternary Operator
- ทำให้โค้ดกระชับและสามารถอ่านได้ง่าย
- ช่วยลดความยุ่งยากของโค้ด
- ช่วยเพิ่มความรวดเร็วในการเขียนโค้ด

## Syntax ของ Ternary Operator ในภาษา Dart
  
```dart
condition ? expr1 : expr2
```
> **คำอธิบาย** <br>
>- **condition :** เงื่อนไขที่จะถูกประเมินเพื่อตรวจสอบว่าเป็นจริงหรือเท็จ <br>
>- **expr1 :** นิพจน์ที่จะถูกคืนค่าถ้าเงื่อนไข (condition) เป็นจริง (ค่าหลังเครื่องหมาย ? ) <br>
>- **expr2 :** นิพจน์ที่จะถูกคืนค่าถ้าเงื่อนไข (condition) เป็นเท็จ (ค่าหลังเครื่องหมาย : ) <br>

### ตัวอย่าง
```dart
void main(){
   var ans = 10;
   ans == 10 ? print("Answer is 10") : print("Oh no!");
}
```
> แสดงผลลัพธ์ที่ได้โดยตรวจสอบเงื่อนไขว่า ค่าของตัวแปร ans เท่ากับ 10 หรือไม่
> - ถ้าเงื่อนไขเป็นจริงจะแสดงผลลัพธ์เป็น "Answer is 10"
> - ถ้าเงื่อนไขเป็นเท็จจะแสดงผลลัพธ์เป็น "Oh no!"


<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Answer is 10</code></pre>
</details> 
<br>

## เปรียบเทียบ Syntax ในภาษาอื่นๆ
รูปแบบการใช้งานและ Syntax อาจเหมือนหรือคล้ายคลึงกัน แต่จะมีการใช้งานเพิ่มเติมหรือการเขียนที่แตกต่างกันในแต่ละภาษา

- Java
```java
condition ? expr1 : expr2;
 ```
- C
```c
condition ? expr1 : expr2;
 ```
- Python
```python
expr1 if condition else expr2
 ```  

> [!NOTE]
> ในภาษา Python ไม่มี Ternary Operator ในรูปแบบเดียวกันกับภาษาอื่น แต่มี Conditional Expression ที่ใช้เพื่อสร้างเงื่อนไขและคืนค่าในรูปแบบที่คล้ายกับ Ternary Operator 
<br>


<br>

### ตัวอย่างในภาษาอื่นๆ

- Java
```java
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    
    // รับค่าคะแนนจากผู้ใช้
    Scanner input = new Scanner(System.in);
    System.out.println("Enter your marks: ");
    double marks = input.nextDouble();

    // ตรวจสอบค่าคะแนนว่าเกิน 40 หรือไม่
    String result = (marks > 40) ? "pass" : "fail";

    System.out.println("You " + result + " the exam.");
    input.close();
  }
}
 ```
> แสดงผลลัพธ์โดยตรวจสอบเงื่อนไขว่า คะแนนที่ผู้ใช้ป้อนเข้ามาเกิน 40 หรือไม่
> - ถ้าเงื่อนไขเป็นจริง จะกำหนดค่า result และแสดงผลลัพธ์เป็น "pass" 
> - ถ้าเงื่อนไขเป็นเท็จ จะกำหนดค่า result และแสดงผลลัพธ์เป็น "fail"

<details>
  <summary><strong>Output 1</strong></summary>
  <pre><code>Enter your marks: 75
You pass the exam.</code></pre>
</details>

<details>
  <summary><strong>Output 2</strong></summary>
  <pre><code>Enter your marks: 24
You fail the exam.</code></pre>
</details>


- C
```c
#include <stdio.h>
int main() {
  int age;

  // รับค่าอายุจากผู้ใช้
  printf("Enter your age: ");
  scanf("%d", &age);

  // ตรวจสอบเงื่อนไขว่าอายุมากกว่าหรือเท่ากับ 18 หรือไม่
  (age >= 18) ? printf("You can vote") : printf("You cannot vote");

  return 0;
}
 ```
> แสดงผลลัพธ์โดยตรวจสอบเงื่อนไขว่า ผู้ใช้มีอายุมากกว่าหรือเท่ากับ 18 หรือไม่ ด้วยการรับข้อมูลอายุจากผู้ใช้
> - ถ้าเงื่อนไขเป็นจริงจะแสดงผลลัพธ์เป็น "You can vote" 
> - ถ้าเงื่อนไขเป็นเท็จจะแสดงผลลัพธ์เป็น "You cannot vote" 

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Enter your age: 12
You cannot vote</code></pre>
</details>

- Python
```python
to_check = 6
msg = "Even" if to_check%2 == 0 else "Odd"
print(msg)
 ```
> แสดงผลลัพธ์ว่าตัวแปร to_check เป็นเลขคู่หรือเลขคี่ โดยตรวจสอบเงื่อนไขว่า ค่าของตัวแปรหารด้วย 2 แล้วเหลือเศษเป็น 0 หรือไม่ (กล่าวคือเป็นเลขคู่)
> - ถ้าเงื่อนไขเป็นจริง msg (เป็นเลขคู่) จะถูกกำหนดค่าและแสดงผลลัพธ์เป็น "Even" 
> - ถ้าเงื่อนไขเป็นเท็จ msg (เป็นเลขคี่) จะถูกกำหนดค่าและแสดงผลลัพธ์เป็น "Odd" 

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Even</code></pre>
</details>
 

<br>

## Ternary Operator Vs If Else
เปรียบเทียบการใช้ if-else แบบทั่วไป กับการใช้ Ternary Operator ในการจัดการเงื่อนไข
### - Dart
- ##### ตัวอย่าง : ใช้ If else
```dart
void main() {
  int num1 = 10;
  int num2 = 15;
  int max = 0;
  if(num1> num2){
    max = num1;
  }else {
    max = num2;
  }
  print("The greatest number is $max");
}
```
> แสดงผลลัพธ์เป็นตัวเลขที่มากที่สุดระหว่างสองตัวเลขโดยตรวจสอบเงื่อนไขว่า ค่าของตัวแปร num1 มากกว่า num2 หรือไม่
> - ถ้าเงื่อนไขเป็นจริงจะกำหนดค่า max เป็นค่าของ num1
> - ถ้าเงื่อนไขเป็นเท็จจะกำหนดค่า max เป็นค่าของ num2 <br>
> - แสดงผลลัพธ์ว่า "The greatest number is [ค่าที่มากที่สุด]" โดยใช้ค่าของ max

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

- ##### ตัวอย่าง : ใช้ Ternary Operation
```dart
void main() {
  int num1 = 10;
  int num2 = 15;
  int max = (num1 > num2) ? num1 : num2;
  print("The greatest number is $max");
}
```

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

> [!NOTE]
> สังเกตได้ว่า Ternary operator ทำให้โค้ด if-else สั้นลงและอ่านง่ายมากขึ้น
<br>

## ตัวอย่างเดียวกันในภาษาอื่นๆ
### - Java
- ##### ตัวอย่าง : ใช้ If else
```java
public class Main {
    public static void main(String[] args) {
        int num1 = 10;
        int num2 = 15;
        int max;
        if (num1 > num2) {
            max = num1;
        } else {
            max = num2;
        }
        System.out.println("The greatest number is " + max);
    }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

- ##### ตัวอย่าง : ใช้ Ternary Operation
```java
public class Main {
    public static void main(String[] args) {
        int num1 = 10;
        int num2 = 15;
        int max = (num1 > num2) ? num1 : num2;
        System.out.println("The greatest number is " + max);
    }
}
 ```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

### - C
- ##### ตัวอย่าง : ใช้ If else
```c
#include <stdio.h>
int main() {
    int num1 = 10;
    int num2 = 15;
    int max;
    if (num1 > num2) {
        max = num1;
    } else {
        max = num2;
    }
    printf("The greatest number is %d\n", max);
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

- ##### ตัวอย่าง : ใช้ Ternary Operation
```c
#include <stdio.h>
int main() {
    int num1 = 10;
    int num2 = 15;
    int max = (num1 > num2) ? num1 : num2;
    printf("The greatest number is %d\n", max);
    return 0;
}
 ```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

### - Python
- ##### ตัวอย่าง : ใช้ If else
```python
num1 = 10
num2 = 15
if num1 > num2:
    max = num1
else:
    max = num2
print("The greatest number is", max)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

- ##### ตัวอย่าง : ใช้ Ternary Operation
```python
num1 = 10
num2 = 15
max = num1 if num1 > num2 else num2
print("The greatest number is", max)
 ```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

## Summary
Ternary Operator สามารถใช้เป็นวิธีแทนที่คำสั่ง if-else ได้ นอกจากช่วยลดจำนวนบรรทัดในการเขียนโค้ด ยังเพิ่มประสิทธิภาพในการจัดการเงื่อนไขและคืนค่าในรูปแบบที่สั้นและกระชับด้วย<br>

  แต่อย่างไรก็ตาม Ternary Operator ก็ไม่สามารถแทนที่คำสั่ง If-Else ได้อย่างสมบูรณ์เสมอไป สำหรับเงื่อนไขที่ซับซ้อนหรือมีการกระทำหลายอย่าง ควรใช้ if-else เพื่อให้โค้ดมีความเข้าใจง่ายและชัดเจนมากขึ้น

## Reference

https://dart-tutorial.com/conditions-and-loops/ternary-operator-in-dart/ <br>
https://dart.dev/language/operators#conditional-expressions <br>
https://www.educative.io/answers/ternary-operator-in-dart <br>
https://www.tutorialspoint.com/ternary-operator-in-dart-programming <br>
https://www.programiz.com/c-programming/ternary-operator#google_vignette <br>
https://www.programiz.com/java-programming/ternary-operator <br>
https://www.educative.io/answers/what-is-the-ternary-operator-in-python

## Link Video
https://youtu.be/zKQtcvB3RyA

## Slide
[Ternary Operator in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12881637/Ternary.Operator.in.Dart.pptx)


