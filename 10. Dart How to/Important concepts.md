# Important concepts
ใน tutorial นี้เราจะมาดูเรื่องแนวคิดที่สำคัญของ Dart  โดยที่ภาษา Dart เป็นภาษาโปรแกรมที่มีแนวคิดแบบ Object-Oriented Programming (OOP) ที่ให้ความสำคัญกับการจัดการกับ Object และ Class และใช้ในสร้าง Applications หรือ Project อื่นๆ และจะต้องคำนึงถึงข้อเท็จจริงและแนวคิดดังนี้

## Objects & Class
ใน Dart นั้นตัวแปร ตัวเลข ฟังก์ชัน และค่า null จะเป็นวัตถุ และวัตถุก็เป็น Instance ของ Class วัตถุเหล่านี้สืบทอดมาจากคลาส Object แต่ยกเว้นค่า Null ถ้าหากใช้ Sound Null Safety

Sound Null Safety คือการป้องกันไม่ให้เกิดข้อผิดพลาดที่เป็นค่าว่าง ซึ่งเป็นสาเหตุที่ทำให้ข้อผิดพลาดระหว่างการรันโปรแกรม (runtime errors) 


## Null Safety
คือ คุณสมบัติหนึ่งใน Dart ที่จะช่วยเพื่อป้องกันข้อผิดพลาดที่เกิดจากค่า Null ซึ่งช่วยให้สามารถตรวจจับข้อผิดพลาดที่เกิดจากค่า Null ได้ และฟีเจอร์นี้เรียกว่า "Sound Null Safety"

ใน Dart เวอร์ชัน 2.12 ขึ้นไปที่เปิดใช้งาน null safety เมื่อประกาศตัวแปรจะต้องระบุว่าตัวแปรนั้นจะมีค่า null ซึ่งหมายความว่าตัวแปรไม่สามารถมีค่าว่างได้ 
### Example : สร้างตัวแปรโดยที่ไม่ได้กำหนดค่า
```dart
  void main() {
    String name;  
    print(name);  
  }
```
>จากตัวอย่างจะทำให้เกิดการ runtime error หากต้องการระบุว่าตัวแปรอาจมีค่าเป็น null จะต้องเพื่มเครื่องหมายคำถาม ? ไปที่ประเภทข้อมูล

- Output
  
``` dart
Error: Non-nullable variable 'name' must be assigned before it can be used.
```

 

### Example : สร้างตัวแปรโดยที่ไม่ได้กำหนดค่าโดยการใช้ ?
```dart
  void main() {
    String? name;  // ประกาศตัวแปร name โดยระบุว่าอาจจะมีค่าเป็น null
    print(name);  
  }
```
>จากตัวอย่างมีการเพื่มเครื่องหมาย ? หลังประเภทข้อมูล ทำให้ค่าของ name สามารถเป็น null ได้และจะไม่เกิดการ runtime error

- Output
  
``` dart
null
```

## Type Annotations & Type Inference
### Type Annotations
คือภาษาที่ต้องมีการประกาศ และบอกว่าตัวแปรนี้จะเป็นข้อมูลประเภทไหนซึ่งตัวเราเองจะต้องกำหนดว่าตัวแปร ฟังก์ชัน วัตถุ นั้นมี type เป็นอะไร 
#### Example : การสร้างตัวแปรและกำหนดชนิดข้อมูล 
```dart
void main() {
  String name = "John";
  int age = 30;
  print(name);
  print(age);
}
```
>จากตัวอย่างจะเป็นการกำหนดประเภทข้อมูลไว้แล้ว String กับ int

- Output
  
``` dart
John
30
```


### Type Inference
คือเป็นการปล่อยให้ตัว Dart จัดการเรื่อง type ว่าตัวแปร ฟังก์ชัน วัตถุ ให้เองโดยอัตโนมัติ
โดยที่ compiler สามารถรู้ type ของข้อมูลได้โดยดูจาก literal หรือค่าคงที่ที่กำหนดให้กับตัวแปร
#### Example : การสร้างตัวแปรแต่ไม่ได้กำหนดชนิดข้อมูล
```dart
void main() {
  var name = " John"; 
  var age = 30;
  print(name);
  print(age);
}
```
>จากตัวอย่างจะมีการกำหนดประเภทข้อมูลเป็น var คือตัวแปรที่ไม่ระบุชนิดข้อมูลตอนประกาศตัวแปร และจะสามารรู้ประเภทข้อมูลได้ตอนที่เรากำหนดค่า

- Output
  
``` dart
John
30
```


## Dart supports
คุณลักษณะหรือความสามารถที่ Dart รองรับมีตัวอย่างที่สำคัญดังนี้
### Generic Type 
การระบุชนิดข้อมูลของตัวแปรที่จะใช้ใน Class หรือ Method นั้นๆ ให้มีลักษณะ dynamic ตามการเรียกใช้งาน และสามารถใช้งานกับชนิดข้อมูลหลายประเภทได้  โดยไม่ต้องเขียนโค้ดใหม่สำหรับแต่ละชนิดข้อมูล

#### Example : Generic Type
```Dart
class Box<T> {			
  T value;
  Box(this.value);
}

void main() {
  var integerBox = Box<int>(42);
  var stringBox = Box<String>("Hello, Dart!");

  print(integerBox.value); // 42
  print(stringBox.value); // "Hello, Dart!"
}
```
>จากตัวอย่างจะเป็นใช้ Generic Type โดยรับพารามิเตอร์ชื่อ T เป็นชนิดข้อมูลที่จะถูกใช้ในคลาส Box และ value; เป็นตัวแปรของคลาส Box ที่เก็บค่าของชนิดข้อมูลของ T
ในฟังก์ชั่น main() จะสร้างออบเจ็กต์ชื่อว่า integerBox กับ stringBox และจะรับชนิดข้อมูลโดยจะใส่ใน <..> และส่งพารามิเตอร์ไปให้กับ class Box 


- Output
  
``` dart
42
Hello, Dart!
```


### Top-level functions 
เป็นฟังก์ชันในระดับสูงสุดของโปรแกรมจะอยู่ด้านบนสุดของลำดับชั้นของคลาสหรือฟังก์ชัน และสามารถสร้างฟังก์ชันที่เชื่อมโยงกับ Class หรือ Object ได้ และสามารถเขียนฟังก์ชันระดับบนสุดอีกฟังก์ชันหนึ่งไว้ที่ด้านบนของฟังก์ชัน main() ได้

#### Example : เปรียบเทียบฟังก์ชันในระดับสูงสุด
```Dart
void sayHello() { // A top-level function
  print("Hello, world!");
}
void main() {
  sayHello(); // "Hello, world!"
}

```
>จากตัวอย่าง void sayHello() เป็น top-level function จะประกาศด้านบนสุดของโค้ด และในฟังก์ชัน main จะเรียกใช้ void sayHello() โดยไม่จำเป็นต้องสร้างอินสแตนซ์ของคลาส  


- Output

```dart
Hello, world!
```

### Top-level variables 
ในภาษา Dart คือตัวแปรที่ประกาศที่ด้านนอกของคลาสและฟังก์ชัน ซึ่งอยู่นอกเหนือจากเนื้อหาของคลาสหรือฟังก์ชัน โดยตัวแปรเหล่านี้สามารถเข้าถึงได้ทุกที่ในโปรแกรม แต่ไม่ได้เชื่อมโยงกับคลาสหรืออ็อบเจ็กต์ใดๆ 
#### Example : สร้างตัวแปรนอกฟังก์ชัน main()
```dart
var myVariable = 42; // Top-level variables 

void main() {
  print(myVariable);
}
```
>จากตัวอย่างเราจะสามารถเรียกตัวแปรนอก main() ได้โดยที่ไม่จำเป็นต้องเขียนฟังก์ชันหรือคลาส และไม่ต้องมีการสร้างอ็อบเจ็กต์หรือคลาสอื่น 

- Output
  
```dart
42
```






## Access Modifiers 
คือการกำหนดระดับในการเข้าถึงของ คลาส แอตทริบิวต์ เมธอด โดยมีประโยชน์ในเรื่องของสิทธิในการเข้าใช้งาน และการซ้อนข้อมูล


ใน Dart จะต่างจาก Java หรือ C++ ตรงที่ไม่มีคีย์เวิร์ด public protected และ private หากตัวระบุขึ้นต้นด้วยขีดล่าง (_) จะถูกกำหนดเป็น private 
#### Example : 1 กำหนดระดับการเข้าถึงของ attribute 
```dart
class Point {
  int _x = 0; //กำหนดให้ x เป็น private
  int _y = 0; //กำหนดให้ ั y เป็น private

  Point({int x = 0, int y = 0}) { //c
    this._x = x;
    this._y = y; 
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();
}
```

- Output
  
```dart
Point(x=10,y=20)
```
---
### __เปรียบเทียบการเขียนในภาษาอื่นๆ__

1. Java

```java
class Point {
    private int x = 0; // กำหนดให้ x เป็น private
    private int y = 0; // กำหนดให้ y เป็น private

    Point(int x, int y) { // Constructor
        this.x = x;
        this.y = y;
    }

    void show() {
        System.out.println("Point(x=" + x + ", y=" + y + ")");
    }
}

public class Main {
    public static void main(String[] args) {
        Point p1 = new Point(10, 20);
        p1.show();
    }
}
```

- Output
  
```java
Point(x=10,y=20)
```

---
2. C++

```c++
#include <iostream>

class Point {
private:
    int x = 0; // กำหนดให้ x เป็น private
    int y = 0; // กำหนดให้ y เป็น private

public:
    Point(int x, int y) { // Constructor
        this->x = x;
        this->y = y;
    }

    void show() {
        std::cout << "Point(x=" << x << ", y=" << y << ")" << std::endl;
    }
};

int main() {
    Point p1(10, 20);
    p1.show();

    return 0;
}
```
- Output

```c++
Point(x=10,y=20)
```

---
3. Python

```python
class Point:
    def __init__(self, x, y):  # Constructor
        self._x = x
        self._y = y

    def show(self):
        print(f"Point(x={self._x}, y={self._y})")

def main():
    p1 = Point(10, 20)
    p1.show()

if __name__ == "__main__":
    main()
```

- Output

```python
Point(x=10,y=20)
```


> โดยตัวอย่างทั้งสามตัวนี้ แสดงให้เห็นว่าภาษา Java กับ C++ จะมีความคล้ายคลึงกันมาก
> และจะมีคีย์เวิร์ด private แต่ในทางกลับกันภาษา Dart กับ Python นั้นจะไม่มีคีย์เวิร์ดแต่จะแทนด้วยเครื่องหมาย (_)



ใน Dart จะมีความเป็น Private ที่ระดับเดียวกับ Library มากกว่าระดับ Class หมายความว่า Class และฟังก์ชันอื่นๆ ทั้งหมดภายใน Library นั้นสามารถเข้าถึงสมาชิกเหล่านั้นได้ 

การเพิ่ม (_) ให้กับตัวแปรจะทำให้ library เป็นแบบ private ไม่ใช่คลาสแบบ private

เพื่อป้องกันไม่ให้ฟังก์ชันอื่นเข้าถึงฟิลด์ที่เป็น private ของ class Point จะต้องสร้าง library ใหม่และวางคลาสไว้ในนั้น


#### Example : 2 พยายามเข้าถึง ฟิลด์ _x และ ฟิลด์ _y ที่เป็น private ในฟังก์ชัน main()

```dart
class Point {
  int _x = 0; //กำหนดให้ x เป็น private
  int _y = 0; //กำหนดให้ y เป็น private

  Point({int x = 0, int y = 0}) { //c
    this._x = x;
    this._y = y; 
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();

  p1._x = 100; // เป็นการแก้ไขตัวแปร x ที่เป็น private
  p1._y = 200; // เป็นการแก้ไขตัวแปร y ที่เป็น private
  p1.show();
}
```
>จากตัวอย่างเป็นการที่พยายามเข้าถึงตัวแปรที่เป็นแบบ private จึงทำให้เปลี่ยนแปลงค่าภายในตัวแปร x กับ y
- Output

```dart
Point(x=10,y=20)
Point(x=100,y=200)
```


#### Example : วิธีการป้องกันการเข้าถึงของฟิลด์ที่เป็น private

> 1.  ให้สร้างไฟล์ใหม่ที่เรียกว่า point.dart และเพิ่ม class Point ให้กับไฟล์

```dart
class Point {
  int _x = 0;
  int _y = 0;

  Point({int x = 0, int y = 0}) {
    this._x = x;
    this._y = y;
  }
  show() {
    print('Point(x=$_x,y=$_y)');
  }
}
```

> 2.  import point.dart library ลงใน main.dart เพื่อให้สามารถอ้างอิงถึง class Point

```dart
import 'point.dart';

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();
}
```

>  3.  หากพยายามแก้ไขหรือเข้าถึงตัวแปร _x และ_y จาก main.dart จะเกิด error

```dart
import 'point.dart';

void main() {
  var p1 = Point(x: 10, y: 20);
  p1.show();

  // errors
  p1._x = 100;
  p1._y = 200;
}
```



## Error Handling
กระบวนการในการจัดการกับข้อผิดพลาดหรือข้อบกพร่องที่อาจเกิดขึ้นในโปรแกรมในระหว่างการเรียกใช้โค้ด

เครื่องมือใน Dart สามารถรายงานปัญหาได้สองประเภทคือ คำเตือน (Warnings) และข้อผิดพลาด (errors)

### 1. Warnings
เป็นการบอกว่าโค้ดอาจไม่ทำงาน แต่ไม่ได้ขัดขวางการทำงานของโปรแกรม
### 2. Errors
ข้อผิดพลาดอาจเป็นได้ทั้ง ข้อผิดพลาดในการคอมไพล์เวลา (Compile-time error) หรือข้อผิดพลาดรันไทม์ (Runtime error)
-  #### Compile-time error
   ข้อผิดพลาดที่เกิดจากการเขียนคำสั่งผิด ไม่ตรงกับโครงสร้างของภาษา 
-  #### Runtime error
   ข้อผิดพลาดที่จะพบได้ในตอนที่เครื่องกำลังทำงานตามโปรแกรมนั้นๆ


---

## Link Slide
https://drive.google.com/drive/folders/1FZ-TKBhbYUiTphMKC0PyheA8DwHemKjA?usp=sharing

## Link Video
https://youtu.be/7uuieuLawsE

## Reference
https://www.tutorialandexample.com/dart-important-concepts

https://benzneststudios.com/blog/dart/hello-sound-null-safety-in-dart/

https://dart.dev/language/variables#null-safety

https://dart.dev/language/type-system

https://dart.dev/language/type-system#type-inference

https://www.youtube.com/watch?v=TF-TBsgIErY&list=PLjxrf2q8roU0Net_g1NT5_vOO3s_FR02J&t=124s

https://www.geeksforgeeks.org/dart-generics/

https://sanjibsinha.com/top-level-functions-in-dart/

https://news.dartlang.org/2012/09/simplify-your-constructors-and-top.html

https://www.darttutorial.org/dart-tutorial/dart-private-fields/

https://www.geeksforgeeks.org/access-modifiers-java/

https://www.geeksforgeeks.org/access-modifiers-in-c/

https://www.geeksforgeeks.org/access-modifiers-in-python-public-private-and-protected/

https://dart.dev/language/error-handling

