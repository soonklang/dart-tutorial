# FOR LOOP ในภาษา DART

เป็นประเภทของลูป (loop) ที่นิยมและใช้บ่อยที่สุด ซี่งช่วยให้โค้ดนั้นสามารถทำงานตามคำสั่งซ้ำได้หลายครั้ง โดยมีโครงสร้างภาษา(Syntax) ดังนี้

 ```dart
for(initialization; condition; increment/decrement){
            statements;
}
```

```dart
for (เงื่อนไขเริ่มต้น; เงื่อนไขสำหรับการทำงานซ้ำ; การเปลี่ยนแปลงหลังจากการทำงานซ้ำ) {
    // บล็อกของโค้ดที่จะทำงานในแต่ละรอบของลูป
}
```

> แนวคิดหลักของ for loop คือสามารถทำงานซ้ำกับบล็อกของคำสั่งต่าง ๆ โดยที่กำหนดเงื่อนไขเริ่มต้น เงื่อนไขการทำงานซ้ำ และการเปลี่ยนแปลงหลังจากการทำงานซ้ำได้ 

* **Initialization (เงื่อนไขเริ่มต้น)** : ส่วนนี้เป็นส่วนที่กำหนดค่าเริ่มต้นของตัวแปรที่จะใช้ในการควบคุมลูป ส่วนนี้จะถูกทำครั้งเดียวก่อนที่ลูปจะเริ่มทำงาน เช่น การกำหนดค่าเริ่มต้นให้กับตัวแปรนับ

* **Condition (เงื่อนไขสำหรับการทำงานซ้ำ)** : เป็นเงื่อนไขที่ต้องเป็นจริงเพื่อให้ลูปทำงานซ้ำในแต่ละรอบ หากเงื่อนไขนี้เป็นเท็จ ลูป for จะสิ้นสุดการทำงาน

* **Increment/Decrement (การเปลี่ยนแปลงหลังจากการทำงานซ้ำ)** : ส่วนนี้ใช้ในการเปลี่ยนค่าของตัวแปรที่ใช้ในการควบคุมลูปหลังจากที่บล็อกของโค้ดในแต่ละรอบทำงานเสร็จสิ้น เช่น การเพิ่มค่าหรือลดค่าของตัวแปรนับ

* **Statements (คำสั่ง)** : ส่วนนี้เป็นบล็อกของคำสั่งที่เราต้องการที่จะทำซ้ำในแต่ละรอบของลูป จะถูกทำซ้ำจนกว่าเงื่อนไขการทำงานซ้ำจะเป็นเท็จ

แผนผังการทำงานต่อไปนี้แสดงวิธีการทำงานของคำสั่งลูป for:


## For loop ใน Dart มีความแตกต่างจากในภาษา C หรือ Java อย่างไร ?

## ตัวอย่างที่ 1 **การพิมพ์ตัวเลข 1 ถึง 10 โดยใช้ลูป for**
* ตัวอย่างนี้จะพิมพ์ตัวเลขตั้งแต่ 1 ถึง 10 โดยใช้ลูป for ซึ่งส่วนที่กำหนดคือ int i = 1; เป็นส่วนของการเริ่มต้น (initialization), i<=10 เป็นเงื่อนไข (condition) และ i++ เป็นการเพิ่มค่า/ลดค่า (increment/decrement) ของตัวแปร i

**ตัวอย่างภาษา DART**
```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    print(i);
  }
}
```
ใน Dart เราใช้ for ในการเรียกใช้ลูป
* เริ่มต้นที่ int i = 1; ซึ่งเป็นการประกาศและกำหนดค่าตัวแปรเริ่มต้นเป็น i มีค่า 1
* เงื่อนไข i <= 10; จะทำให้ลูปทำงานตราบใดที่ i มีค่าน้อยกว่าหรือเท่ากับ 10
* i++ คือการเพิ่มค่า i ทีละหนึ่งหลังจากแต่ละรอบ

**ตัวอย่างภาษา JAVA**
```java
public class Main {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```
**ตัวอย่างภาษา C**
```C
#include <stdio.h>
int main() {
    for (int i = 1; i <= 10; i++) {
        printf("%d\n", i);
    }
    return 0;
}
```
> ถึงแม้จากตัวอย่างจะมีโครงสร้างที่คล้ายคลึงกันในทั้ง 3 ภาษา แต่วิธีการประกาศตัวแปร, การทำงานของเงื่อนไข และการเพิ่มค่า/ลดค่าต่างๆ นั้นจะมีความแตกต่างกันเล็กน้อยตามแต่ละภาษา

## ตัวอย่างที่ 2 **การพิมพ์ตัวเลข 10 ถึง 1 โดยใช้ลูป for**