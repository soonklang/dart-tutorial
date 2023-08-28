# TERNARY OPERATOR IN DART

## Ternary Operator In Dart
ในหัวข้อนี้จะอธิบายเกี่ยวกับ Ternary Operator ในภาษา Dart โดย Ternary Operator คือ วิธีในการจัดการเงื่อนไขและคืนค่าในบรรทัดเดียว เพื่อให้โค้ดอ่านได้ง่ายขึ้น และส่วนใหญ่จะใช้แทนที่คำสั่ง if-else หรือเรียกว่า if-else แบบลดรูป ซึ่งจะมีรูปแบบเหมือนกับคำสั่ง if-else แต่มีการทำงานที่สั้นและกระชับกว่า โดยใช้เครื่องหมาย ? และ : ในการตรวจสอบเงื่อนไข เพื่อเลือกคืนค่าใดค่าหนึ่ง ซึ่งขึ้นอยู่กับผลลัพธ์ของเงื่อนไขที่กำหนด

**ข้อควรจำ**
สำคัญ : จุดประสงค์หลักของ Ternary Operation คือ ลดจำนวนบรรทัดในการเขียนโค้ด และใช้ในกรณีที่เงื่อนไขไม่ซับซ้อน หากเงื่อนไขมีความซับซ้อนหรือมีการกระทำหลายอย่างที่ต้องประมวลผล ควรใช้ if-else แทนเพื่อให้โค้ดอ่านง่ายและเข้าใจมากขึ้น

## ประโยชน์ของ Ternary Operator
- ทำให้โค้ดกระชับและสามารถอ่านได้ง่าย
- ช่วยลดความยุ่งยากของโค้ด
- ช่วยเพิ่มความรวดเร็วในการเขียนโค้ด

## Syntax ของ Ternary Operator ในภาษา Dart
  
- **กรณีที่ต้องการเลือกคืนค่าตามเงื่อนไขที่กำหนด**
```dart
condition ? expr1 : expr2
```
> **คำอธิบาย** <br>
>- **condition :** เงื่อนไขที่จะถูกประเมินเพื่อตรวจสอบว่าเป็นจริงหรือเท็จ โดยปกติจะเป็นนิพจน์ที่สามารถให้ผลลัพธ์เป็น boolean (true หรือ false) <br>
>- **expr1 :** คือนิพจน์ที่จะถูกคืนค่าถ้าเงื่อนไข (condition) เป็นจริง (ค่าหลังเครื่องหมาย ? ) <br>
>- **expr2 :** คือนิพจน์ที่จะถูกคืนค่าถ้าเงื่อนไข (condition) เป็นเท็จ (ค่าหลังเครื่องหมาย : ) <br>

### ตัวอย่าง
```dart
void main(){
   var ans = 10;
   ans == 10 ? print("Answer is 10") : print("Oh no!");
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Answer is 10</code></pre>
</details> 

<br>

- **กรณีที่ต้องการจัดการค่า null**
```dart
expr1 ?? expr2
```
> **คำอธิบาย** <br>
>- **expr1 :** นิพจน์ที่จะถูกประเมิน หากมีค่าไม่เป็น null จะคืนค่าของ expr1
>- **expr2 :** นิพจน์ที่จะถูกคืนค่า หาก expr1 เป็น null

### ตัวอย่าง
```dart
void main(){
   var ans;
   ans ?? print("ans is null");
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>ans is null</code></pre>
</details>

<br>

## เทียบ Syntax ในภาษาอื่นๆ
- Java
```java
condition ? expr1 : expr2;
 ```
- C
```c
condition ? expr1 : expr2;
 ```
- Phython
```python
expr1 if condition else expr2
 ```
> **Note :** ในภาษา Python ไม่มี Ternary Operator ในรูปแบบเดียวกันกับภาษาอื่น แต่มี Conditional Expression ที่ใช้เพื่อสร้างเงื่อนไขและคืนค่าในรูปแบบที่คล้ายกับ Ternary Operator 
<br>
รูปแบบการใช้งานและ Syntax อาจเหมือนหรือคล้ายคลึงกัน แต่จะมีการใช้งานเพิ่มเติมหรือการเขียนที่แตกต่างกันในแต่ละภาษา

<br>

<br>

## Ternary Operator Vs If Else
เปรียบเทียบการใช้ if-else แบบทั่วไป กับการใช้ Ternary Operator หรือ If-else แบบลดรูปในการจัดการเงื่อนไข

### ตัวอย่าง : ใช้ If else
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
> หาตัวเลขที่มากที่สุดระหว่างสองตัวเลขโดยใช้เงื่อนไข if-else
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

### ตัวอย่าง : ใช้ Ternary Operation
- Dart
```dart
void main() {
  int num1 = 10;
  int num2 = 15;
  int max = (num1 > num2) ? num1 : num2;
  print("The greatest number is $max");
}
```
> หาตัวเลขที่มากที่สุดระหว่างสองตัวเลขโดยใช้เงื่อนไข Ternary Operation
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>The greatest number is 15</code></pre>
</details>

> **Note :** สังเกตได้ว่า Ternary operator ทำให้โค้ด if-else สั้นลงและอ่านง่ายมากขึ้น
<br>

## ตัวอย่างเดียวกันในภาษาอื่นๆ

- Java
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

- C
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

- Phython
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
Ternary Operator สามารถใช้เป็นวิธีแทนที่คำสั่ง if-else ในกรณีที่เงื่อนไขไม่ซับซ้อน ช่วยลดจำนวนบรรทัดในการเขียนโค้ดและเพิ่มประสิทธิภาพในการจัดการเงื่อนไขและคืนค่าในรูปแบบที่สั้นและกระชับ <br>

**สรุปเปรียบเทียบในภาษาต่าง ๆ**
- Dart มี Ternary Operator และ Null Coalescing Operator เพื่อจัดการเงื่อนไขและค่า null ในรูปแบบที่สะดวกและกระชับ
- Java และ C มี Ternary Operator สำหรับเงื่อนไขและคืนค่า
- Python ไม่มี Ternary Operator แต่มี Conditional Expression ที่คล้ายกับ Ternary Operator ในภาษาอื่น

อย่างไรก็ตาม Ternary Operation ถึงจะเปรียบเสมือนแบบจำลองของ If-Else แต่ก็ไม่สามารถแทนที่คำสั่ง If-Else ได้อย่างสมบูรณ์เสมอไป สำหรับเงื่อนไขที่ซับซ้อนหรือมีการกระทำหลายอย่างควรใช้ if-else เพื่อให้โค้ดมีความเข้าใจง่ายและชัดเจนมากขึ้น

## Reference

https://dart-tutorial.com/conditions-and-loops/ternary-operator-in-dart/ <br>
https://dart.dev/language/operators#conditional-expressions <br>
https://www.educative.io/answers/ternary-operator-in-dart <br>
https://www.tutorialspoint.com/ternary-operator-in-dart-programming


