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
## ข้อดีข้อเสียของแต่ละภาษา
การ random ค่าต่างๆของแต่ละภาษานั้นจะค่อนข้างแตกต่างกันโดยสิ้นเชิง
โดยจะเห็นได้ว่า การ random ตัวเลขนั้น ภาษา dart กับ python จะเขียนได้ง่ายและไม่ซับซ้อน ส่วน c กับ java อาจจะต้องเขียนเยอะกว่าหน่อยถ้าเทียบกัน
ส่วนการเขียน random boolean นั้น จะเห็นความเเตกต่างโดยชัดเจน ซึ่ง dart จะเขียนแค่ บรรทัดเดียวเเละเรียบง่าย ส่วน python กับ java อาจจะดูซับซ้อนขึ้นนิดหน่อย และ c ผมหาวิธีไม่เจอหรือ

# 2.Point class
Point class เป็นคราสที่เอาไว้ใช้กับพิกัดสองมิติ
ซึ่งใน point class นั้นก็จะมี features ต่างๆดังนี้
- Point(x, y) ซึ่งเป็นการกำหนดตัวเลขของจุดหรือพิกัดโดย x,y จะเป็นตัวเเทนของตัวเลขที่เรากำหนดเราไว้
- Point.x และ point.y ซึ่งเป็นการเข้าถึงพิกัดตัวเลขที่เรากำหนดไว้
- Point.magnitude เป็นการหาค่าระยะทางระหว่างจุดที่เรากำหนดกับพิกัด (0,0)
- Point1.distanceTo(Point2) เป็นการหาระยะทางระหว่างจุดสองจุด
- Point1.squaredDistanceTo(์Point2) เป็นการยกกำลังสองของระยะทางระหว่างจุดสองจุด
- Point * num เป็นการเพิ่มค่าของพิกัดโดยการคูณ
- Point1 + Point2 และ Point1 - Point2 จะเป็นการบวก และ ลบกันของจุดสองจุด
- Point1 == point2 เป็นการเท่ากันของจุดสองจุดและส่งค่ากลับมาเป็น boolean
```dart
import 'dart:math'; 
void main() {

var p1 = Point(1, 2);//กำหนดจุดที่ตำแหน่ง(0,0)
var p2 = Point(10, 14);//กำหนดจุดที่ตำแหน่ง(10, 14)
var p3 = Point(14.2, 13.3);//กำหนดจุดที่ตำแหน่ง(14.2, 13.3)

print("x value of p1: ${p1.x}"); //เป็นการปริ้นค่า x ของ p1
print("y value of p1: ${p1.y}"); //เป็นการปริ้นค่า y ของ p1

print("Magnitude of p2: ${p2.magnitude}");//หาค่าระยะทางระหว่างจุดที่ p2 กับ (0,0)

print("Distance between p1 and p2: ${p1.distanceTo(p2)}");//หาระยะทางระหว่างจุดของ p1 กับ p2

print("Squared distance between p1 and p2: ${p1.squaredDistanceTo(p2)}");//หาระยะทางกำลังสองของจุด p1 กับ p2

Point newP2 = p2*3; //เพิ่มค่าของพิกัด p2 เป็นสามเท่า
print("x value of newP2 scaled by 3: ${newP2.x}");
print("y value of newP2 scaled by 3: ${newP2.y}");

Point sum = p2 + newP2;//เป็นการหาค่าผลรวมของจุดสองจุด
print("x value of the sum of p2 and newP2: ${sum.x}");
print("y value of the sum of p2 and newP2: ${sum.y}");

Point diff = newP2 - p3;
print("x value of the difference between newP2 and p3: ${diff.x}");
print("y value of the difference between newP2 and p3: ${diff.y}");

Point p4 = p1;
print("p1 and newP2 are equal: ${p1==newP2}");
print("p1 and p4 are equal: ${p1==p4}");
}
```
output
```
x value of p1: 1
y value of p1: 2
Magnitude of p2: 17.204650534085253
Distance between p1 and p2: 15.0
Squared distance between p1 and p2: 225
x value of newP2 scaled by 3: 30
y value of newP2 scaled by 3: 42
x value of the sum of p2 and newP2: 40
y value of the sum of p2 and newP2: 56
```
## เปรียบเทียบ Point class กับ java
ใน java ถ้าเราจะต้องการทำงานเกี่ยวกับจุดสองมิติเราสามารถ import java.awt.geom.Point2D มาใช้ได้

```java
import java.awt.geom.Point2D;

public class Main {
    public static void main(String[] args) {
        
        Point2D p1 = new Point2D.Double(3, 4);
        Point2D p2 = new Point2D.Double(1, -2);

       
        System.out.println("P1: (" + p1.getX() + ", " + p1.getY() + ")");//เปรียบเสมือนการหาค่าของ (x,y)
        System.out.println("P2: (" + p2.getX() + ", " + p2.getY() + ")");

   
        Point2D p3 = new Point2D.Double(p1.getX()+p2.getX(), p1.getY()+p2.getY());
        System.out.println("P3: (" + p3.getX() + ", " + p3.getY() + ")"); //ส่วนการหาการบวกลบจะใช้วิธีนี้
        
        double distance = p1.distance(p2); //หาระยะทางของสองจุด

        System.out.println("Distance between points: " + distance);
    }
}

```
output
```
P1: (3.0, 4.0)
P2: (1.0, -2.0)
P3: (4.0, 2.0)
Distance between points: 6.324555320336759
```
## เปรียบเทียบ Point class กับ c
ใน ภาษา c นั้น จะไม่มีคราสให้ import เหมือนกับภาษา dart เราแต่เราสามารถทำได้โดยการสร้างขึ้นมาเองได้
```c
#include <stdio.h>
#include <math.h>

struct Point {
    double x;
    double y;
//สร้าาง struct เอาไว้เก็บค่าจุด x,y
};

double distance(struct Point p1, struct Point p2) {
    double dx = p2.x - p1.x;
    double dy = p2.y - p1.y;
    return sqrt(dx*dx + dy*dy);
//สร้างคราส distance เอาไว้หาระยะทางระหว่างจุด
}

int main() {
    struct Point point1 = {3, 4};
    struct Point point2 = {1, -2};

    printf("Point 1: (%lf, %lf)\n", point1.x, point1.y);
    printf("Point 2: (%lf, %lf)\n", point2.x, point2.y);

    double dist = distance(point1, point2);
    printf("Distance between points: %lf\n", dist);

    return 0;
}

```
output
```
Point 1: (3.000000, 4.000000)
Point 2: (1.000000, -2.000000)
Distance between points: 6.324555
```
## เปรียบเทียบ Point class กับ python
ใน python นั้น วิธีการจะใกล้เคียงกับ dart เนื่องจากมี librarie ที่สามารถเข้ามาช่วยได้
แต่อาจจะต้องสร้างเขียนวิธีการหา distance เหมือนกับ c เข้ามาเหมือนกัน 
```python
import math
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
#สร้างคราสขึ้นมาเพื่อเก็บค่า x,y

p1 = Point(3, 4) 
p2 = Point(1, -2)

print("P1: "p1.x, p1.y)
print("P2: "p2.x, p2.y)

distance = math.sqrt((p2.x - p1.x)**2 + (p2.y - p1.y)**2)
#อ้างอิงวิธีการหาระยะทางระหว่างจุดจากสมการทางคณิตศาตร์
print("Distance between points:", distance)
```
output
```
P1:  3 , 4
P2:  1 , -2
Distance between points: 6.324555320336759

```
## ข้อดีข้อเสียของแต่ละภาษา
pyhon และ java จะมีวิธีเขียนที่ค่อนข้างสะดวกกว่าเพราะมีการใช้ libary มาช่วย ต่างจาก c ที่ไม่มีและต้องเขียน class ขึ้นมาเองจึงทำให้เสียเปรียบ
# 3.Rectangle class
Rectangle class คลาสนี้ใช้สำหรับแสดงเป็นตัวเเทนรูปสี่เหลี่ยมสองมิติและมีคุณสมบัติคงที่ ซึ่งประกอบไปด้วย left,top right และ bottom เพื่อเป็นตัวแทนของสี่เหลียมในสองมิติ
ซึ่งในการเขียนโค้ดนั้น เราจะสร้าง constructor ขึ้นมาเเต่เราจะกำหนด เป็น left,top ,width,height ซึ่ง width จะคือค่าของ right = width + left และ bottom =top + height
```dart
 import 'dart:math';
void main() {
var rect = Rectangle(10, 20, 30, 40);//สร้าง constructor โดยค่าข้างในจะเป็น (left, top, width, height)
  print("Left: ${rect.left}");
  print("Top: ${rect.top}");
  print("Right: ${rect.right}");
  print("Bottom: ${rect.bottom}");
  print("Width: ${rect.width}");
  print("Height: ${rect.height}");

}
```
output
```
Left: 10
Top: 20
Right: 40 //เกิดจาก width + left
Bottom: 60 //เกิดจาก top + height
Width: 30
Height: 40

```
เราสามารถเราเรื่อง point มาประยุกต์ได้โดยใช้คำสั่ง containsPoint(...) เพื่อหาจุดว่าอยู่ในขอบเขตของสี่เหลียมหรือป่าว
```dart
 import 'dart:math';
void main() {
var rect = Rectangle(10, 20, 30, 40);
  var point = Point(20, 30);
  if (rect.containsPoint(point)) {
    print("The point is inside the rectangle.");
  } else {
    print("The point is outside the rectangle.");
  }
}
```
output
```
The point is inside the rectangle.
```
เมื่อเรามีสี่เหลียมสองรูแล้วอยากจะหาช่วงที่ซ้อนทับกัน
เราจะใช้วิธี .intersection() เพื่อหาว่าสี่เหลียมทั้งสองรูปกันเกิดการซ้อนกันหรือไหม
```dart
import 'dart:math';
void main() {
  // Create a rectangle using constructor
  var rect1 = Rectangle(10, 20, 30, 40);
  var rect2 = Rectangle(25, 35, 40, 30);
var intersection = rect1.intersection(rect2);
print("Intersection ${intersection}");
}
```
output
```
Intersection Rectangle (25, 35) 15 x 25
//  หมายความว่าจุดที่มันซ้อนทับกันจะเริ่มตั้งแต่จุดที่ (25,35)  และขยายไปทางขวา 15 หน่วย และขยายลงมา 25 หน่วย        
```
## เปรียบเทียบ Point class กับ java
ในจาวาในทำงานกับพื้นที่สี่เหลี่ยมจะคล้ายกับ dart เนื่องจากมีฟังชั่นช่วย
ซึ่งเราจะ import java.awt.Rectangle;
```java
import java.awt.Rectangle;

public class Main {
    public static void main(String[] args) {
        
        Rectangle rect1 = new Rectangle(10, 20, 30, 40); //สร้าง constructors
        Rectangle rect2 = new Rectangle(25, 35, 40, 30);

        System.out.println("rect1: " + rect1);
        System.out.println("rect2: " + rect2);
        
        Rectangle intersection1 = rect1.intersection(rect2);//หาค่า intersection
        Rectangle intersection2 = rect2.intersection(rect1);
   
        System.out.println("Intersection1 Rectangle: " + intersection1);
        
    }
}

```
output
```
rect1: java.awt.Rectangle[x=10,y=20,width=30,height=40]
rect2: java.awt.Rectangle[x=25,y=35,width=40,height=30]
Intersection1 Rectangle: java.awt.Rectangle[x=25,y=35,width=15,height=25] //ค่าจะเหมือนกับ dart และวิธีก็คล้ายกัน
```
## เปรียบเทียบ Point class กับ python
การทำด้วย python จะไม่มีคราสเจาะจงเหมือน dart กับ java เราจึนต้องเขียนขึ้นมาเอง
```python
class Rectangle:# สร้างคราส Rectangle
    def __init__(self, left, top, width, height): #เก็บค่า 
        self.left = left
        self.top = top
        self.width = width
        self.height = height

    def intersection(self, other_rect):#เขียนวิธีเช็คว่าพื้นที่สี่เหลียมมันทับซ้อนกันหรือป่าว
        x_overlap = max(0, min(self.left + self.width, other_rect.left + other_rect.width) - max(self.left, other_rect.left))
        y_overlap = max(0, min(self.top + self.height, other_rect.top + other_rect.height) - max(self.top, other_rect.top))
        
        if x_overlap > 0 and y_overlap > 0:
            return Rectangle(max(self.left, other_rect.left), max(self.top, other_rect.top), x_overlap, y_overlap)
        else:
            return Rectangle(0, 0, 0, 0)

rect1 = Rectangle(10, 20, 30, 40)
rect2 = Rectangle(25, 35, 40, 30)

intersection_rect = rect1.intersection(rect2)
print("Intersection Rectangle: left =", intersection_rect.left, "top =", intersection_rect.top,
      "width =", intersection_rect.width, "height =", intersection_rect.height)
```
output
```
Intersection Rectangle: left = 25 top = 35 width = 15 height = 25
```
## ข้อดีข้อเสียของแต่ละภาษา
จะเห็นได้ว่า java กับ dart ค่อนค้างที่จะใกล้เคียงกันเป็นอย่างมากแต่ python นั้นเรายังจะต้องเขียน class ด้วยตัวเอง

# 4.MutableRectangle class
ซึ่งคราสนี้จะมีคุณสมบัติเหมือนกับ  Rectangle class แต่สามารถเปลี่ยนแปลงค่าได้
```dart
import 'dart:math';
void main() {
var rect = MutableRectangle(20, 50, 300, 600);
print(rect);
//ทำการเปลี่ยนค่า
rect.left = 70;
rect.top = 40;
rect.width = 200;
rect.height = 100;
print(rect);
}
```
output
```
Rectangle (20, 50) 300 x 600
Rectangle (70, 40) 200 x 100 //ค่าจะเปลี่ยนไป
```
# อ้างอิง
https://www.educative.io/answers/how-to-use-the-dartmath-library
https://api.dart.dev/stable/3.1.0/dart-math/dart-math-library.html

# Clip
https://www.youtube.com/watch?v=4ZBEun5JGNw
# silde
[Math in dart.pptx](https://github.com/vanittripichaphan/630710335/raw/b79537470158d9cc1a2f3506f16bcafb90ef1c0a/Math%20in%20Dart.pptx?)
