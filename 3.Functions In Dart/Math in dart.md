# **Math in dart**
ในหัวข้อนี้จะสอนการเรียกให้ฟังชั่นที่ใช้ดำเนินการทางคนิตศาตร์ในภาษา dart และเปรียบเทียบกับภาษาอื่นๆ ซึ่งก่อนเริ่มที่จะใช้ฟังชั่น math นั้นเราจะต้อง import libary dart:math
#
import functions

**Dart**
 ```dart
import 'dart:math';
```
### เปรียบการเรียกใช้ฟังก์ชั่น math กับภาษาอื่นๆ
**java**
```java
import static java.lang.Math.*;
```
ปล. การใช้ .* ของ java จะเป็นเรียกใช้ทุกฟังชั่น
**c**
```c
#include <math.h>
```
**c++**
```c++
#include <math.h>
```
**python**
```python
import math
```
เป็นต้น
ปล. การ import math ที่ยกตัวอย่างมาของแต่ละภาษาอาจจะเหมือนกันแต่ข้างในของ libary แตกต่างกันอย่างสิ้นเชิง
#
### libary math ใน dart นั้นจะประกอบไปด้วย 4  class ด้วยกัน คือ Random class, Point class, Rectangle class และ MutableRectangle class

# 1.Random class
จะเป็นการสร้างค่าสุ่มของ bool, int หรือ double values 
ซึ่งการใช้นั้นเราจะ ใช้คำสั่ง Random().สิ่งที่เราต้องการ เช่น
 ```dart
import 'dart:math';
void main (){
findInt = Random().nextInt(10)
//สุ่มตัวเลขระหว่าง 0-9
var doubleValue = Random().nextDouble()
//จะทำการ random ทศนิยม ระหว่าง 0 < 1 
// random 0 ถึง 10 เป็นทศนิยม
var boolValue = Random().nextBool();
//จะเป็นการ random true หรือ false 
}
```
ข้างใน nextInt(...) นั้นเราจะกำหนดค่าตัวเลขหรือตัวเเปรคงที่เข้าไปเพื่อกำหนดช่วงที่เราต้องการจะทำการสุ่มซึ่งถ้าเราใส่ 10 ลง ไปจะทำการสุ่มค่าระหว่าง 0 ถึง 10 นั้นเอง
ถ้าเกิดเราอยากจะ random ค่าระหว่าง 5-10 ละก็เราก็ใช้ method (max - min + 1) + min ซึ่ง max = 10 min =5 ตามสมการจะได้ (10-5+1)+5 จะได้
```dart
import 'dart:math';
void main (){
var findspcInt = Random().nextInt(6) + 5
//ซึ่งการ Random().nextInt(6) จะทำการสุ่มตัวเลข ระหว่าง 0-5 จากนั้นจะทำการ + 5 เข้าไปทุกช่วง จะได้เป็นการสุ่มตัวเลขระหว่าง 5-10 นั้นเอง
}
```
ส่วน nextDouble() เราจะใส่ *ช่วงที่เราต้องการเช่น 
```dart
var doubleValue = Random().nextDouble()*10
//จะ random 0 < 10 
```
## เปรียบเทียบการ random ค่ากับ python 
pyhon นั้นเราจะ import random เข้ามาก่อน จากนั้นใช้คำสั่ง random.randint(a,b) ซึ่ง a,b จะเป็นช่วงของค่าที่เราต้องการ
### python 
```python
import random
Arandom = random.randint(0,9)
#Arandom จะทำการเก็บตัวเลขสุ่มตัวเลขระหว่าง 0 ถึง 9
frandom = random.uniform(0,1)
#frandom จะทำการเก็บตัวเลขสุ่มตัวเลขทศนิยมระหว่าง 0 ถึง 1
```
ส่วนการ random ของ bool นั้นเราจะใช้วิธี 
```python
import random
a = random.randint(0, 1)
random_bool = bool(a)
#ซึ่งเปรียบเทียบการ ramdom ค่า 1 = true 0 = false 
```
## เปรียบเทียบการ random ค่ากับ c
c นั้นจะการเรียกใช้ #include <stdlib.h> ที่มีฟั่งชั่นก์ rand() เป็นการ random ค่า ซึ่งถ้าเขียน a = rand() เฉยๆ rand() จะ random 
ค่าจำนวณเต็มบวกออกมาระหว่าง 0 ถึง 32767 ซึ่งแต่ถ้าเราต้องการกำหนดช่วง เราจะเขียน % ไว้ข้างหลังตามด้วยช่วงที่เราต้องการเช่น
```c
#include <stdio.h>
#include <stdlib.h>
int main() {
  int a = rand() % 10;
  // a จะเก็บค่าระหว่าง 0-10 นั้นเอง
}
```
## เปรียบเทียบการ random ค่ากับ java
java นั้นจะมีอยู่หลายวิธีด้วยกันซึ่ง จะทำการยกตัวอย่างมาสองวิธ๊คือ 1 ทำการ import java.util.Random;
```java
import java.util.Random;
class Random{
public static void main( String args[] ){
Random rand = new Random(); //กำหนด Instance ของ Random class
int R = rand.nextInt(10); //เนื่องจากเราใส่ ( int ) ลงไปจึงกำหนดให้ random ค่า จาก 0 ถึงตัวที่เรากำหนดไว้
double D = rand.nextDouble();//จะ random double ระหว่าง 0 ถึง 1
}
}
```
random bool 
```java
import java.util.Random;
class Random{
public static void main( String args[] ){
Random rand = new Random(); //กำหนด Instance ของ Random class
boolean R = rand.Boolean();
// R จะ random ค่า true , false
}
}
```
วิธีที่ 2 ใช้ Math.random() ซึ่งเราจะต้องกำหนด ช่วง min max มาจากนั้นจะใช้
รูปแบบ  Math.floor(Math.random() *(max - min + 1) + min) 
```java
class Random{
public static void main( String args[] ){
int max = 100;
int min = 10;
a =  Math.floor(Math.random() *(max - min + 1) + min);
//a จะทำการเก็บค่าระหว่าง 10 ถึง 100

}
}
```
## สรุปข้อดีข้อเสียของการ random
การ random ค่าต่างๆของแต่ละภาษานั้นจะค่อนข้างแตกต่างกันโดยสิ้นเชิง
โดยจะเห็นได้ว่า การ random ตัวเลขนั้น ภาษา dart กับ python จะเขียนได้ง่ายและไม่ซับซ้อน ส่วน c กับ java อาจจะต้องเขียนเยอะกว่าหน่อยถ้าเทียบกัน
ส่วนการเขียน random boolean นั้น จะเห็นความเเตกต่างโดยชัดเจน ซึ่ง dart จะเขียนแค่ บรรทัดเดียวเเละเรียบง่าย ส่วน python กับ java อาจจะดูซับซ้อนขึ้นนิดหน่อย และ c ผมหาวิธีไม่เจอหรือ

# 2.Point class



