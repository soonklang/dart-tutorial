# Final and Const in Dart

หากคุณไม่ต้องการเปลี่ยนค่าในตัวแปรหรือคุณอยากได้ค่าคงที่คุณสามารถใช้ Final กับ Const ได้

### ตัวอย่างการประกาศ Final และ Const ใน Dart
```dart
	void main() {
  	  final PI_1 = 3.14;
  	  const PI_2 = 3.14;
	  PI_1 = 2; //error
	  PI_2 = 2; //error
	}
```
#### สังเกตว่า
ตัวแปรที่มีกำหนดค่าได้ครั้งเดียว และต้องมีการกำหนดค่าเริ่มต้นให้เสมอเมื่อประกาศ และไม่สามารถแก้ไขค่าได้

### แล้ว 2 อย่างนี้มันต่างกันอย่างไร
##### ในเมื่อใช้ได้เหมือนกัน

#### Const
```dart
	void main() {
	  const PI; //error
	  const PI_1 = 3.14;
	}
```
เราไม่สามารถสร้างตัวแปล const ป่าวๆได้ จะ Error ทันที เมื่อเราสร้างนั้นต้องระบุค่าทันที
ดังนั้นเราควรใช้ const ก็ต่อเมื่อเรารู้ค่าที่แน่นอน ณ เวลา compile time

##### Compile time
หมายถึงช่วงเวลาขณะที่โปรแกรมถูกคอมไพล์ หรือแปลงโค้ดที่เขียนเป็นภาษามนุษย์เป็นภาษาที่เครื่องคอมพิวเตอร์เข้าใจได้ เมื่อโปรแกรมถูกคอมไพล์แล้ว จะสร้างไฟล์ที่เครื่องคอมพิวเตอร์สามารถทำงานได้โดยตรง ช่วงเวลานี้เกิดขึ้นก่อนที่โปรแกรมจะถูกเรียกใช้งานและเริ่มการทำงานจริง ช่วงเวลาที่โปรแกรมถูกคอมไพล์นั้นจะเป็นเวลาที่ระบบคอมพิวเตอร์ตรวจสอบความถูกต้องของโค้ด แปลงเป็นรหัสเครื่อง และทำการเตรียมความพร้อมให้กับการทำงานของโปรแกรมในอนาคต

#### Final
```dart
	void main() {
	  final PI_2;
	  PI_2 = 3.14;
	}
```

สังเกตว่าเราสามารถประกาศตัวแปรไว้เปล่าก่อนได้ แล้วค่อยระบุค่าที่หลัง
ดัวนั้น ถ้าเรายังไม่รู้ค่า เราสามารถใช้ Final แทนได้ ดังนั้นใช้ final ณ เวลา run time

##### Run time
หมายถึงช่วงเวลาที่โปรแกรมถูกรันและทำงานจริงบนคอมพิวเตอร์หรืออุปกรณ์ที่ใช้ในการทำงาน ในช่วงนี้ โปรแกรมจะประมวลผลข้อมูล ดำเนินการตามโค้ด และสร้างผลลัพธ์ตามการทำงานที่กำหนดไว้ในโปรแกรม

### Const และ Final ของภาษาอื่น

#### C language
ในภาษา c นั้นมีแค่ const ไม่มี final
```c
#include <stdio.h>
void main(){
  const int PI = 3.14;
}
```

#### Java language
ในภาษา Java, คีย์เวิร์ด final ถูกใช้เพื่อประกาศค่าคงที่ (constant) แทนตัวแปรที่ค่าของมันไม่สามารถเปลี่ยนแปลงได้หลังจากกำหนดค่าแล้ว เป็นวิธีที่ Java ใช้ในการสร้างค่าคงที่
```java
class Demo{
  public static void main(String args[]){
    final int MY_CONSTANT = 10;
  }
}
```

#### Python language

ในภาษา python นั้นไม่มี const และ final
จึงมักพิมพ์ตัวแปรเป็นพิมพ์ใหญ่หมด เพื่อบอกว่าเป็น ค่าคงที่นั้นเอง
```python
PI = 3.14;
NAME = "Lucky"
IP = "192.168.1.1"
```

## สรุป
ใช้ const เมื่อต้องการสร้างค่าคงที่ที่เรารู้ค่าแน่นอน ณ เวลา compile time และใช้ final เมื่อต้องการสร้างค่าคงที่ที่เราจะรู้ค่าเมื่อ run time

## Presentation
https://youtu.be/I_898-H7j8M
## Slide
[Slide](https://drive.google.com/file/d/1Inl69lhhaHoY6VLmtwxIFx1xg56TVwCL/view?usp=drive_link)

## Reference
[Dart Tutorial](https://dart-tutorial.com/useful-information/final-vs-const-in-dart/)
[siriphonnot.medium.com](https://siriphonnot.medium.com/const-static-%E0%B9%81%E0%B8%A5%E0%B8%B0-final-%E0%B9%83%E0%B8%99-dart-%E0%B8%95%E0%B9%88%E0%B8%B2%E0%B8%87%E0%B8%81%E0%B8%B1%E0%B8%99%E0%B8%AD%E0%B8%A2%E0%B9%88%E0%B8%B2%E0%B8%87%E0%B9%84%E0%B8%A3-f5eceed6b982)
[codingninjas](https://www.codingninjas.com/studio/library/dart-const-and-final-keyword)
[stackoverflow](https://stackoverflow.com/questions/50431055/what-is-the-difference-between-the-const-and-final-keywords-in-dart)



