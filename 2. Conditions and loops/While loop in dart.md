# While loop in dart

While loop เป็นคำสั่งวนซ้ำที่ดำเนินการหลายครั้งตามค่า boolean โดยโครงสร้างภาษาของ While Loop จะเป็นดังนี้

**Syntax Dart**
```dart
while(conditional expression) {
  statements   
}
```
* **Conditional expression (เงื่อนไข)** คือ เป็นตัวเช็คเงื่อนไขจริงหรือเท็จเท่านั้น หากเป็นจริงคำสั่งภายในลูปจะถูกดำเนินการ หากเป็นเท็จลูปจะถูกหยุดทำงาน
> Conditional expression จะต้องอยู่ใน"()"
* **Statements (คำสั่ง)** คือ คำสั่งที่ต้องการจะทำหากเงื่อนไขของลูปเป็นจริง
> Statements จะต้องเขียนอยู่ในช่วงของบล็อกโค้ด "{}"

**Flowchart While loop in dart มีขั้นตอนการทำงานของ while loop ดังรูปต่อไปนี้**

![Flowchart](https://github.com/630710041/Flowchart/blob/main/flowchart_whileloop.png)

# ตัวอย่างโค้ด While loop ในภาษา Dart

* ตัวอย่าง การทำงานของ while loop <br>

```dart
void main() {
  var number = 10;
  var sum = 0;

  while (number >= 1) {
    sum = sum + number;
    number--;
  }
  print("The Sum is ${sum}");
}
```
**คำอธิบาย**
> &emsp;ลูปจะทำการเช็คเงื่อนไขหากเป็นจริงคำสั่งจะถูกดำเนินการ โดยในตัวอย่างจะเช็คว่าตัวแปร number มากกว่าหรือเท่ากับ 1 หรือไม่<br>
> ในครั้งแรกค่า number จะมีค่า 10 ซึ่งเงื่อนไขเป็นจริงคำสั่งจะดำเเนินการบวกค่า(sum + number) และค่า number จะลบ 1 และวนซ้ำไปเรื่อยๆ<br>
> จนรอบสุดท้ายค่า number จะมีค่าเท่ากับ 0 จึงทำให้เงื่อนไขเป็นเท็จ ผลรวม(sum)ที่ได้จะมีค่าเท่ากับ 55

**Output :**
```dart
The Sum is 55
```

# While loop ของภาษา Dart แตกต่างกับภาษา C Java และ Python อย่างไร

* ตัวอย่าง While loop ภาษา C

```C
int i = 0;

while (i < 5) {
  printf("%d\n", i);
  i++;
}
```

* ตัวอย่าง While loop ภาษา Java

```Java
int i = 0;

while (i < 5) {
  System.out.println(i);
  i++;
}
```

จะสังเกตุได้ว่า โครงสร้างของภาษา C และ Java มีโครงสร้างแบบเดียวกันกับภาษา Dart และเงื่อนไขจะต้องเป็นจริงเท่านั้นถึงจะดำเนินการคำสั่งและวนลูปซ้ำ<br>
แตกต่างจาก Python ที่มีโครงสร้างภาษาแตกต่างจาก C และ Java ที่กล่าวถึงข้างต้น

* ตัวอย่าง While loop ภาษา Python

```Python
i = 1
while i < 6:
  print(i)
  i += 1
```

**Syntax Python**

```Python
while conditional expression :
    statements
```

โครงสร้างแตกต่างเพียงแค่เล็กน้อย เงื่อนไข While loop ของ Python ไม่ต้องอยู่ใน"()"เหมือนของ C และ Java หลังจากสร้างเงื่อนไขลูปแล้วต้องคั่นหลังด้วย colon(:) While loop เป็นวิธีที่ใช้ง่ายไม่ซับซ้อนมากเพราะสามารถนำโครงสร้างของภาษา C และ Java มาช่วยทำความเข้าใจได้ง่ายขึ้น
