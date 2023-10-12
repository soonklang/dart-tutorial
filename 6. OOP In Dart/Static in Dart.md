<img width="4124" alt="image" src="https://github.com/soonklang/dart-tutorial/assets/141732410/86c658fe-95b4-4279-bb82-a0546fa2f45d"># Static In Dart 
การกำหนดตัวแปรหรือเมธอดที่ใช้ร่วมกันโดยตัวแทนอ้างอิงทั้งหมดของคลาส (Instances of class) เราสามารถใช้ Keyword แบบ static กำกับไว้ด้านหน้าฟิลด์ เพื่อใช้งานเฉพาะ ที่อาจจะไม่ได้สัมพันธ์กับ instance object และการเรียกใช้ static variable และ static method จะใช้งานหน่วยความจำเมื่อมีการทำงานครั้งแรกเท่านั้น จะคืนค่าหน่วยความจำเมื่อโปรแกรมปิดหรือหยุดการทำงาน
## Static Variable in Dart
static variable เป็น top-level variable ที่สามารถเรียกใช้งานผ่าน class ใดๆ ในโปรแกรมได้ เราจะเรียกว่า static variable หรือในกรณีเป็น object จะเรียกว่า instance variable ในกรณีที่ตัวแปรของเราเป็นค่าคงที่ไม่เปลี่ยนแปลง เราสามารถกำหนดตัวแปรนี้เป็น static variable เพื่อให้รองรับการเรียกใช้งานหน่วยความจำแค่ครั้งแรกครั้งเดียวได้และใช้ค่าจากหน่วยความจำเดิม ในการเรียกใช้งานในครั้งต่อไป โดยใช้ keyword คำว่า static กำกับไว้ด้านหน้าของตัวแปร
```dart
void main () {
  var circle1 = Circle(22);
  // ใช้งานหน่วยความจำทุกๆ instnce object ที่เรียกใช้งาน
  print(circle1.pi); 
  var circle2 = Circle(44);
  // ใช้งานหน่วยความจำทุกๆ instnce object ที่เรียกใช้งาน
  print(circle2.pi);  
}
 
class Circle{
  double radius; // instance variable
  double pi = 3.14; // instance variable
   
  Circle(this.radius); // constructor
   
  // instance method
  double getArea(){
    return pi * (radius * radius);
  }
}
```
ตัวแปร pi หรือ instance variable ที่ทุกๆ ครั้งที่มีการสร้าง object และเรียกใช้งาน ตัวแปร pi จะมีการดึงหน่วยความจำมาใช้และ ค่า pi เป็นค่าคงที่ไม่เปลี่ยนแปลง
```dart
void main () {
  var circle1 = Circle(22);
 // print(circle1.pi); // error ไม่สามารถเรียกใช้ผ่าน instance ได้
  print(Circle.pi); // สามารถเรียกใช้ผ่าน class name ได้
  // โดยจะใช้งานหน่วยความจำแค่ครั้งแรกครั้งเดียว
  var circle2 = Circle(44);
 // print(circle2.pi); // error ไม่สามารถเรียกใช้ผ่าน instance ได้ 
  print(Circle.pi); // สามารถเรียกใช้ผ่าน class name ได้
  // การเรียกใช้ครั้งที่สองจะใช้จากค่าเดิม จะไม่มีการใช้งานหน่วยความจำเพิ่ม
}
 
class Circle{
  double radius; // instance variable
  static double pi = 3.14; // static variable
   
  Circle(this.radius); // constructor
   
  // instance method
  double getArea(){
    // ตัวแปร pi เป็น static variable 
    // สามารถเรียกใช้งานใน ฟังก์ชั่นปกติได้
    return pi * (radius * radius);
  }
   
  // static method
  static double getPi(){
    // ตัวแปร pi เป็น static variable 
    // สามารถเรียกใช้งานใน ฟังก์ชั่น static ได้
    return pi;
  }

  // static method 
  static void testStatic(){
    getPi(); // เรียกใช้ static method ได้
    print(pi); // เรียกใช้งาน static variable ได้
  }
}
```
ตอนนี้เราเปลี่ยนตัวแปร pi เป็นตัวแปร static หรือ static variable โดยตัวแปร static variable จะไม่สามารถเรียกใช้งานผ่าน instance ได้ แต่เราสามารถเรียกใช้งานตัวแปร static ในระดับ class name 
## Static Method in Dart
Static method เป็นฟังก์ชั่นที่กำหนดโดยใช้ keyword คำว่า static กำกับไว้ด้านหน้าของฟังก์ชั่นเช่นเดียวกับ instance method แต่ฟังก์ชั่น static ไม่สามารถเรียกใช้งานผ่าน instance object ได้ แต่จะเรียกใช้งานผ่าน class name 
เราสร้าง static method ไว้สำหรับใช้งานเฉพาะ ที่อาจจะไม่ได้สัมพันธ์กับ instance object ทั้งนี้ก็เพื่อให้บางกรณี เราต้องการฟังก์ชั่นนั้นๆไว้ใช้งาน แต่ไม่ต้องการให้ผูกกับ instance object เพื่อลดการใช้งานหน่วยความจำให้กับการเรียกใช้งานฟังก์ชั่น เพราะฟังก์ชั่น static จะไม่ใช้งานหน่วยความจำจนกว่าจะมีการเรียกใช้งาน และจะใช้งานแค่ครั้งเดียวเท่านั้น  
```dart
void main () {
  var car1 = Car('red',2000);
  // การเรียกใช้ instance method สามารถเรียกใช้งานผ่าน
  // instance object ได้ car1 คือ instance object
  print(car1.getColor());
  var car2 = Car('blue',1500);
  print(car2.getColor());  
   
  // การเรียกใช้ static method ต้องเรียกใช้งาน
  // ผ่าน class name ไม่สามารถเรียกใช้งานผ่าน instance object
  print(Car.comparePrice(car1, car2));
}
 
class Car{
  String color;
  int price;
   
  Car(this.color,this.price);
   
  // instnce method
  String getColor(){
    return color;
  }
  // static method
  static int comparePrice(car1, car2){
    return car1.price - car2.price;
  }
}
```
## ความแตกต่างระหว่าง Static in Dart และ Static in Java 
### ความแตกต่างระหว่าง Static Variable in Dart และ Static Variable in Java 
Static Variable ทั้งใน Dart และ Java มีความคล้ายคลึงกัน เป็นการประหยัดหน่วยความจำโดยการเรียกใช้งานหน่วยความจำเพียงครั้งแรกครั้งเดียวและใช้ค่าจากหน่วยความจำเดิมเช่นเดียวกัน แต่ก็มีบางส่วนที่แตกต่างกัน
1. การเข้าถึง :
* Dart : สามารถเข้าถึง static variables ได้โดยตรงผ่านชื่อคลาสเท่านั้น ไม่สามารถเข้าถึงผ่านอ็อบเจกต์ของคลาสได้
```dart
class MyClass {
  static int staticVariable = 10;
}

void main() {
  print(MyClass.staticVariable);
}

```
* Java : สามารถเข้าถึง static variables ได้ทั้งผ่านชื่อคลาสและผ่านอ็อบเจกต์ของคลาส ตัวอย่างการเข้าถึง
```Java
class MyClass {
    static int staticVariable = 10;
}

public class Main {
    public static void main(String[] args) {
        System.out.println(MyClass.staticVariable);
        System.out.println(new MyClass().staticVariable);
    }
}

```
2. การใช้ในคลาสลูก (Subclass) :
* Dart : คลาสลูกไม่สามารถสืบทอดค่าของ static variables จากคลาสแม่ได้
```dart
class Parent {
  static int staticVariable = 10;
}

class Child extends Parent {}

void main() {
  print(Child.staticVariable);  // Error
}

``` 
* Java : คลาสลูกสามารถใช้ static variables จากคลาสแม่ได้โดยตรง แต่ค่าของ static variables ในคลาสลูกจะแชร์กับคลาสแม่เช่นกัน
```Java
class Parent {
    static int staticVariable = 10;
}

class Child extends Parent {}

public class Main {
    public static void main(String[] args) {
        System.out.println(Child.staticVariable);  // 10
        Child.staticVariable = 20;
        System.out.println(Parent.staticVariable); // 20
    }
}

```
### ความแตกต่างระหว่าง Static Method in Dart และ Static Method in Java 
1. การเข้าถึง :
* Dart :สร้าง static method โดยประกาศฟังก์ชันและใช้คีย์เวิร์ด 'static' นำหน้า สามารถเรียกใช้ static method ได้โดยเรียกผ่านชื่อคลาสเท่านั้น ไม่สามารถเรียกผ่านอ็อบเจกต์ของคลาสได้
```dart
class MyClass {
  static void myStaticMethod() {
    print("This is a static method in Dart");
  }
}

void main() {
  MyClass.myStaticMethod();
}

```
* Java : สร้าง static method โดยประกาศเมทอดและใช้คีย์เวิร์ด 'static' นำหน้า สามารถเรียกใช้ static method ได้ผ่านชื่อคลาสหรือผ่านอ็อบเจกต์ของคลาสได้
```Java
class MyClass {
    static void myStaticMethod() {
        System.out.println("This is a static method in Java");
    }
}

public class Main {
    public static void main(String[] args) {
        MyClass.myStaticMethod();
    }
}

```
2. การสืบทอดและการเข้าถึงเมทอด :
* Dart : คลาสลูกไม่สามารถสร้างเมทอด static ที่มีชื่อเหมือนกับเมทอด static ในคลาสแม่
```dart
class Parent {
  static void myStaticMethod() {
    print("Parent's static method in Dart");
  }
}

class Child extends Parent {
  static void myStaticMethod() {
    print("Child's static method in Dart");
  }
}

void main() {
  Parent.myStaticMethod();  // Output: Parent's static method in Dart
  Child.myStaticMethod();   // Output: Child's static method in Dart
}

```
* Java : คลาสลูกสามารถสร้างเมทอด static ที่มีชื่อเหมือนกับเมทอด static ในคลาสแม่และเขียนโค้ดใหม่ได้ แต่เมทอด static ของคลาสลูกจะเรียกใช้เมทอด static ของคลาสลูก ไม่ใช่เมทอด static ของคลาสแม่
```Java
class Parent {
    static void myStaticMethod() {
        System.out.println("Parent's static method in Java");
    }
}

class Child extends Parent {
    static void myStaticMethod() {
        System.out.println("Child's static method in Java");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent.myStaticMethod();  // Output: Parent's static method in Java
        Child.myStaticMethod();   // Output: Child's static method in Java
    }
}

```
3. การเข้าถึงตัวแปรและเมทอดอื่นในคลาส :
* Dart : เมทอด static สามารถเข้าถึง static variables และ static methods อื่นในคลาสนั้นๆ ได้โดยใช้ชื่อคลาสนำหน้า
```dart
class MyClass {
  static int staticVariable = 10;

  static void myStaticMethod() {
    print("Static variable: $staticVariable");
    anotherStaticMethod();
  }

  static void anotherStaticMethod() {
    print("Another static method");
  }
}

```
* Java : เมทอด static สามารถเข้าถึง static variables และ static methods อื่นในคลาสนั้นๆ ได้โดยใช้ชื่อคลาสนำหน้าหรือผ่านอ็อบเจกต์ของคลาส
```Java
class MyClass {
    static int staticVariable = 10;

    static void myStaticMethod() {
        System.out.println("Static variable: " + staticVariable);
        anotherStaticMethod();
    }

    static void anotherStaticMethod() {
        System.out.println("Another static method");
    }
}

```
## ความแตกต่างระหว่าง Static in Dart และ Static in C
### ความแตกต่างระหว่าง Static Variable in Dart และ Static Variable in C
การใช้ static variables ใน Dart และ C มีความแตกต่างในเรื่องของการประกาศและการเข้าถึง และการเปลี่ยนแปลงของค่าใน static variables จะมีผลต่อการแชร์ข้อมูล
ระหว่างอ็อบเจกต์และฟังก์ชันหรือไฟล์
1. การประกาศและการเข้าถึง :
* Dart : ประกาศ static variable ในคลาสโดยใช้คีย์เวิร์ด 'static' นำหน้าตัวแปร สามารถเข้าถึง static variable ได้โดยเรียกใช้ชื่อคลาสนำหน้า
```dart
class MyClass {
  static int staticVariable = 10;
}

void main() {
  print(MyClass.staticVariable);
}

```
* C : ประกาศ static variable ในฟังก์ชันโดยใช้คีย์เวิร์ด 'static' นำหน้าตัวแปร สามารถเข้าถึง static variable ได้ในระดับฟังก์ชันที่ถูกประกาศ
```C
#include <stdio.h>

void myFunction() {
    static int staticVariable = 10;
    printf("Static variable: %d\n", staticVariable);
}

int main() {
    myFunction();
    return 0;
}

```
2. การใช้ใน Context ต่างๆ :
* Dart : static variable ใช้เพื่อแชร์ค่าระหว่างอ็อบเจกต์และคลาสต่างๆ ในขอบเขตของเฉพาะคลาสนั้น ๆ ค่าของ static variable จะเป็นตัวเดียวกันสำหรับทุกอ็อบเจกต์ของคลาสนั้น ๆ และการเปลี่ยนแปลงค่าจะมีผลต่อทุกที่ที่มีการเข้าถึงตัวแปรนั้น
* C : static variable ในฟังก์ชันจะถูกจัดเก็บในหน่วยความจำที่จัดสรรให้กับแอพพลิเคชัน ค่าของ static variable จะถูกเก็บไว้และจะยังคงอยู่เมื่อออกจากขอบเขตของฟังก์ชัน สำหรับ static variable ที่ถูกประกาศในระดับไฟล์ ค่าของตัวแปรจะถูกแชร์ระหว่างไฟล์ที่เรียกใช้
3. การใช้ใน Context ของ Multithreading :
* Dart : การใช้ static variable ในฟังก์ชันหรือคลาสไม่ใช้วิธีการป้องกันการ multithreading ระหว่าง thread ดังนั้นต้องระมัดระวังเมื่อใช้ในสภาวะที่มีการใช้งานพร้อมกันของ thread
* C : การใช้ static variable ในฟังก์ชันหรือไฟล์ในสภาวะที่มีการใช้งานพร้อมกันของthread อาจทำให้เกิดปัญหาการแชร์ข้อมูล (data sharing) จึงใช้กลไกต่าง ๆ เช่น Mutex หรือ Semaphore เพื่อป้องกันปัญหานี้
### ความแตกต่างระหว่าง Static Method in Dart และ Static Functions in C
static method ใน Dart และ static function ในภาษา C มีความแตกต่างในเรื่องของการประกาศและการเข้าถึง และการเข้าถึงตัวแปรและเมทอดอื่นในคลาสหรือไฟล์เดียวกัน
1. การประกาศและการเข้าถึง :
* Dart : ประกาศ static method โดยใช้คีย์เวิร์ด 'static' นำหน้้าเมทอดในคลาส และสามารถเรียกใช้ static method ได้โดยเรียกผ่านชื่อคลาสเท่านั้น ไม่สามารถเรียกผ่านอ็อบเจกต์ของคลาสได้
```dart
class MyClass {
  static void myStaticMethod() {
    print("This is a static method in Dart");
  }
}

void main() {
  MyClass.myStaticMethod();
}

```
* C : ประกาศ static function โดยใช้คีย์เวิร์ด 'static' นำหน้าฟังก์ชัน สามารถเรียกใช้ static function ได้ภายในไฟล์ที่ฟังก์ชันถูกประกาศเท่านั้น การเข้าถึงฟังก์ชันนี้จะถูกจำกัดไว้ในขอบเขตของไฟล์
```C
#include <stdio.h>

static void myStaticFunction() {
    printf("This is a static function in C\n");
}

int main() {
    myStaticFunction();
    return 0;
}

```
2. การเข้าถึงตัวแปรและเมทอดอื่นในคลาส :
* Dart : static method สามารถเข้าถึง static variables และ static methods อื่นในคลาสนั้นๆ ได้โดยใช้ชื่อคลาสนำหน้า
```dart
class MyClass {
  static int staticVariable = 10;

  static void myStaticMethod() {
    print("Static variable: $staticVariable");
    anotherStaticMethod();
  }

  static void anotherStaticMethod() {
    print("Another static method");
  }
}

```
* C : static function สามารถเข้าถึง static variables และ static functions อื่นในไฟล์นั้นๆ ได้โดยตรง
```C
#include <stdio.h>

static int staticVariable = 10;

static void myStaticFunction() {
    printf("Static variable: %d\n", staticVariable);
    anotherStaticFunction();
}

static void anotherStaticFunction() {
    printf("Another static function\n");
}

int main() {
    myStaticFunction();
    return 0;
}

```
## ความแตกต่างระหว่าง Static in Dart และ Static in Python
### ความแตกต่างระหว่าง Static Variable in Dart และ Static Variable in Python
static variable ใน Dart และ class variable ใน Python มีความแตกต่างในเรื่องของการประกาศและการเข้าถึง การใช้งานใน instance ของคลาส และผลกระทบต่อการเปลี่ยนแปลงค่าที่เกิดขึ้นในที่นี้ไม่เหมือนกัน ในทั้งสองภาษานี้ค่าของ static variable หรือ class variable จะแชร์ค่าเดียวกันในทุก instance ของคลาส
1. การประกาศและการเข้าถึง :
* Dart :ประกาศ static variable ในคลาสโดยใช้คีย์เวิร์ด static นำหน้าตัวแปร และสามารถเข้าถึง static variable ได้โดยเรียกใช้ชื่อคลาสนำหน้า
```dart
class MyClass {
  static int staticVariable = 10;
}

void main() {
  print(MyClass.staticVariable);
}

```
* Python :  ไม่มีการประกาศ static variable ในคลาส แต่สามารถสร้างตัวแปรในคลาสที่ถูกเรียกว่า "class variable" ได้ โดยการประกาศตัวแปรนี้ในคลาสและใช้ ClassName. นำหน้าเพื่อเข้าถึง
```Python
class MyClass:
    class_variable = 10

print(MyClass.class_variable)

```
2. การใช้ใน Instance ของคลาส :
* Dart : static variable เป็นของคลาสเองและไม่ขึ้นอยู่กับการสร้าง instance ของคลาส ดังนั้น static variable จะใช้ในรูปแบบ ClassName.staticVariable และไม่ได้เกี่ยวข้องกับ instance ของคลาส
```dart
class MyClass {
  static int staticVariable = 10;
}

void main() {
  print(MyClass.staticVariable);  // Output: 10
  var instance = MyClass();
  print(instance.staticVariable);  // Error: 'staticVariable' is not an instance member of 'MyClass'
}

```
* Python : class variable เป็นของคลาสเช่นกันแต่เมื่อเรียกใช้งานจาก instance ของคลาส ค่าของ class variable จะถูกสืบทอดและแก้ไขได้ผ่าน instance ด้วย
```Python
class MyClass:
    class_variable = 10

instance = MyClass()
print(instance.class_variable)  # Output: 10
instance.class_variable = 20
print(instance.class_variable)  # Output: 20

```
3. การเปลี่ยนแปลงค่า :
* Dart : สามารถเปลี่ยนแปลงค่าของ static variable ได้โดยตรง และการเปลี่ยนแปลงจะมีผลต่อทุก instance ของคลาส
```dart
class MyClass {
  static int staticVariable = 10;
}

void main() {
  print(MyClass.staticVariable);  // Output: 10
  MyClass.staticVariable = 20;
  print(MyClass.staticVariable);  // Output: 20
}

```
* Python : เมื่อค่าของ class variable ถูกเปลี่ยนแปลงผ่าน instance ค่าของ class variable ในคลาสจะถูกค้างไว้ แต่ instance จะมีค่า class variable ใหม่แยกไป
```Python
class MyClass:
    class_variable = 10

instance1 = MyClass()
instance2 = MyClass()

print(instance1.class_variable)  # Output: 10
instance1.class_variable = 20
print(instance1.class_variable)  # Output: 20
print(instance2.class_variable)  # Output: 10 (unchanged)

```
### ความแตกต่างระหว่าง Static Method in Dart และ Static Method in Python
1. การประกาศและการเข้าถึง :
* Dart : Static method ใน Dart ประกาศในคลาสโดยใช้คีย์เวิร์ด static นำหน้าฟังก์ชันในคลาส และสามารถเรียกใช้งานได้โดยเรียกผ่านชื่อคลาสเท่านั้น
```dart
class MyClass {
  static void myStaticMethod() {
    print("This is a static method in Dart");
  }
}

void main() {
  MyClass.myStaticMethod();
}

```
* Python : Static method ใน Python ประกาศโดยใช้ @staticmethod นำหน้าฟังก์ชัน และสามารถเรียกใช้งานได้ผ่านชื่อคลาสหรือผ่านอ็อบเจกต์ของคลาส
```Python
class MyClass:
    @staticmethod
    def my_static_method():
        print("This is a static method in Python")

MyClass.my_static_method()

```

2. การเข้าถึงตัวแปรและเมทอดอื่นในคลาส :
* Dart : Static method ใน Dart สามารถเข้าถึง static variables และ static methods อื่นในคลาสเดียวกันโดยใช้ชื่อคลาสนำหน้า
```dart
class MyClass {
  static int staticVariable = 10;

  static void myStaticMethod() {
    print("Static variable: $staticVariable");
    anotherStaticMethod();
  }

  static void anotherStaticMethod() {
    print("Another static method");
  }
}

```
* Python : Static method ใน Python ไม่สามารถเข้าถึงตัวแปรหรือเมทอดในคลาสได้โดยตรง เนื่องจากมันไม่มีการแนบคลาสเข้าถึง static method และไม่สามารถใช้ 'self' หรือ 'cls' ในการเข้าถึงตัวแปรหรือเมทอดในคลาสได้
```Python
class MyClass:
    class_variable = 10

    @staticmethod
    def my_static_method():
        print("This is a static method in Python")
        # Cannot access class_variable or other methods here

```
3. การเข้าถึง instance method หรือตัวแปรของ instance :
* Dart :  Static method ใน Dart ไม่สามารถเข้าถึง instance method หรือตัวแปรของ instance ได้โดยตรง เนื่องจากไม่ได้รับ Object เป็น Argument
```dart
class MyClass {
  void instanceMethod() {
    print("Instance method in Dart");
  }

  static void myStaticMethod() {
    // Cannot call instanceMethod() here
  }
}

```
* Python : Static method ใน Python ไม่สามารถเข้าถึง instance method หรือตัวแปรของ instance ได้เช่นกัน เนื่องจากไม่มีการแนบ Object เข้าถึง static method
```python
class MyClass:
    def instance_method(self):
        print("Instance method in Python")

    @staticmethod
    def my_static_method():
        # Cannot call instance_method(self) here

```
## reference
https://www.darttutorial.org/dart-tutorial/dart-static/

https://dart-tutorial.com/object-oriented-programming/static-in-dart/

https://www.ninenik.com/การใช้งาน_Static_variable_และ_Static_method_ในภาษา_Dart_เบื้องต้น-946.html

https://www.educative.io/answers/what-are-static-methods-in-dart#

https://www.simplilearn.com/tutorials/java-tutorial/static-keyword-in-java

https://www.lordgift.in.th/2012/06/static-variable-static-method.html

https://expert-programming-tutor.com/tutorial/java/10_02_oop2.php

https://www.amplysoft.com/knowledge/Class/Static%20Variable%20ตัวแปรแบบ%20Static.html

https://dekgenius.com/elearning/javaprogramming/สแตติก-static-และอินสแตนท์-instance/#:~:text=สแตติก%2520(Static)%20คือ,ประมวลผลในคอนโซล%20(Console)

https://www.javatpoint.com/static-in-c#:~:text=Static%20is%20a%20keyword%20used,variable%20is%20throughout%20the%20program

https://www.codingninjas.com/studio/library/static-keyword-in-c

https://www.geeksforgeeks.org/static-variables-in-c/

https://datatrained.com/post/static-keyword-in-c/

https://www.c-programming-simple-steps.com/static-keyword-in-c.html

https://www.javatpoint.com/static-in-python#:~:text=Python%20Static%20Variable,the%20instances%20of%20a%20class

https://www.studytonight.com/python/python-static-keyword

https://sparkbyexamples.com/python/static-or-class-variables-in-python/

https://www.digitalocean.com/community/tutorials/python-static-method

https://pynative.com/python-static-method/

## link slide
https://drive.google.com/file/d/1b0J7GtaVqo_XLeQQXRR_FAUAngCrCmru/view?usp=share_link
## link slide version 2
https://drive.google.com/file/d/1r0z7EMcg_0lQ_L9ZH0ChSvCLpvJ4LUYX/view?usp=sharing

## link video 
https://youtu.be/lK9A1bseCM4?feature=shared



