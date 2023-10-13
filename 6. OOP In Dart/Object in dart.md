# Object in dart
**การเขียนโปรแกรมเชิงวัตถุ** คือ การเขียนโปรแกรมที่เสมือนจริง มีลักษณะเสมือนธรรมชาติ แนวคิดของการเขียนโปรแกรมเชิงวัตถุนั้นให้ความสำคัญกับ **ข้อมูล(data)** และ **พฤติกรรม(behavior)** ของวัตถุ และความสัมพันธ์กันระหว่างวัตถุ โดยจะถูกสร้างขึ้นจากเทมเพลสที่เรียกว่า Class(คลาส)  **Object** ประกอบด้วย **properties(ตัวแปร)** และ**methods(ฟังก์ชัน)** วัตถุ คือ instance ของ class  
**ตัวอย่าง** Objectจักรยาน อาจมีattributes(คุณลักษณะ)ต่างๆ เช่น **color(สี)** , **size(ขนาด)** , **current speed(ความเร็วปัจจุบัน)** อาจมีmethod เช่น changeGear , PadalFaster และ Brake  
> NOTE : หากต้องการสร้าง object เราต้องสร้าง class ก่อน


# Instantiation
การเขียนโปรแกรมเชิงวัตถุ **การสร้าง instantiation** คือ กระบวนการสร้างinstanceของclass หรือจะบอกได้ว่าการสร้าง instantiation เป็นกระบวนการสร้าง object ของ class เช่น หากคุณมี class ชื่อ **Bicycle** จะสามารถสร้าง Object ของclassชื่อ **Bicycle** ได้

# Declaring Object In Dart
เมื่อทำการสร้าง class แล้วจะต้องประกาศ Object คุณสามารถประกาศ Object โดยใช้ syntax ต่อไปนี้:

# Syntax
```dart
ClassName objectName = ClassName();
```


# Example 1: Declaring An Object In Dart
ตัวอย่างด้านล่างนี้ มีจะมี class **Bicycle** มี properties 3 ประการ: **color** , **size** และ **currentSpeed** ใน class จะมี 2 method คือ **changeGear** ซึ่งเป็นการเปลี่ยนเกียร์ของจักรยาน และ **display** จะพิมพ์ค่า properties ทั้งสามออกมา นอกจากนี้ยังมี Object ของ class **Bicycle** ที่เรียกว่า**bicycle**
```dart
    class Bicycle {
      String? color;
      int? size;
      int? currentSpeed;
    
      void changeGear(int newValue) {
        currentSpeed = newValue;
      }
    
      void display() {
        print("Color: $color");
        print("Size: $size");
        print("Current Speed: $currentSpeed");
      }
    }

    void main(){
        // Here bicycle is object of class Bicycle. 
        Bicycle bicycle = Bicycle();
        bicycle.color = "Red";
        bicycle.size = 26;
        bicycle.currentSpeed = 0;
        bicycle.changeGear(5);
        bicycle.display();
    }
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Color: Red
Size: 26
Current Speed: 5</code></pre>
</details>

# Example 2: Declaring Animal Class Object In dart
ในตัวอย่างนี้มี class **Animal**ทีมี properties 3 ประการ: **name** , **numberOfLegs** และ **lifeSpan** class ยังมี method **display**ที่พิมพ์ค่าของ properties ทั้งสามออกมา และยังมี Object ของ class**Animal** ที่เรียกว่า**animal**
```dart
    class Animal {
      String? name;
      int? numberOfLegs;
      int? lifeSpan;
    
      void display() {
        print("Animal name: $name.");
        print("Number of Legs: $numberOfLegs.");
        print("Life Span: $lifeSpan.");
      }
    }

    void main(){
        // Here animal is object of class Animal. 
        Animal animal = Animal();
        animal.name = "Lion";
        animal.numberOfLegs = 4;
        animal.lifeSpan = 10;
        animal.display();
    }
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Animal name: Lion.
Number of Legs: 4.
Life Span: 10.</code></pre>
</details>


# Example 3: Declaring Car Class Object In dart
ในตัวอย่างนี้มี class **Car**ทีมี properties 3 ประการ: **name** , **color**และ**numberOfSeats** class ยังมี method **start**ที่พิมพ์ข้อความ "Car Started" และยังมี object ของ class **Car** ที่เรียกว่า **car**
```dart
    class Car {
      String? name;
      String? color;
      int? numberOfSeats;
    
      void start() {
        print("$name Car Started.");
      }
    }

    void main(){
        // Here car is object of class Car. 
        Car car = Car();
        car.name = "BMW";
        car.color = "Red";
        car.numberOfSeats = 4;
        car.start();

        // Here car2 is another object of class Car.
        Car car2 = Car();
        car2.name = "Audi";
        car2.color = "Black";
        car2.numberOfSeats = 4;
        car2.start();
    }
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>BMW Car Started.
Audi Car Started.</code></pre>
</details>

# Keypoint
- method **main** คือจุดเริ่มต้นของโปรแกรม จึงจำเป็นต้องดูผลลัพธ์เสมอ  
- keyword **new** สามารถใช้เพื่อสร้าง Object ใหม่ได้ แต่ไม่จำเป็น

# Difference Between Dart , Java and Python
## Dart
```dart
// Defining class  
class Student {  
   String? name;  
   int? age;  
   int? rollNo;  
     
   // defining class function  
    showStdInfo() {  
        print("Student Name is : ${name}");  
        print("Student Age is : ${age}");  
        print("Student Roll Number is : ${rollNo}");  
  
               }  
}  
void main () {  
  
  // Creating object called std  
  Student std = Student();  
  std.name = "Peter";  
  std.age =24;  
  std.rollNo = 90001;  
// Accessing class Function  
 std.showStdInfo();  
}  
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Student Name is: Peter
Student Age is: 24
Student Roll Number is: 90001</code></pre>
</details>


## Java
Object ใน Java เป็นพื้นฐานของการเขียนโปรแกรมเชิงวัตถุ Object จะสอดคล้องกับสิ่งต่าง ๆ ที่พบในโลกแห่งความเป็นจริง ตัวอย่างเช่น โปรแกรมกราฟิกอาจมีวัตถุเช่น **วงกลม** **สี่เหลี่ยม** และ **เมนู** ระบบช้อปปิ้งออนไลน์อาจมีวัตถุเช่น **ตะกร้าสินค้า** **ลูกค้า** และ **ผลิตภัณฑ์**  
## วิธีสร้าง Object
มีสี่วิธีในการสร้าง Object ใน Java
 - ใช้ keyword **new** เป็นวิธีทั่วไปในการสร้าง Object ใน Java
>// creating object of class Test  
>Test t = new Test();

 - ใช้ method **Class.forName(String className)** มีคลาสที่กำหนดไว้ล่วงหน้าในแพ็คเกจ java.lang ที่มีชื่อ Class forName(String className) เป็นmethod return คลาส object ที่เกี่ยวข้องกับคลาสที่มี name ที่กำหนด เราต้องระบุชื่อที่มีคุณสมบัติครบถ้วนสำหรับclass เมื่อเรียกเมธอด newInstance() บนคลาสObjectนี้ จะreturn new instance ของคลาสด้วยชื่อสตริงที่กำหนด  
>// creating object of public class Test  
>// consider class Test present in com.p1 package  
>Test obj = (Test)Class.forName("com.p1.Test").newInstance();

 - ใช้ method **clone()** โดย method นี้จะอยู่ในคลาส Object จะทำการสร้างและส่งกลับสำเนาของ Object
>// creating object of class Test  
>Test t1 = new Test();  
>// creating clone of above object  
>Test t2 = (Test)t1.clone();

 - การ Deserialization เป็นเทคนิคในการอ่าน Object ที่บันทึกไว้ในไฟล์
>FileInputStream file = new FileInputStream(filename);  
>ObjectInputStream in = new ObjectInputStream(file);  
>Object obj = in.readObject();

### Example
ใน Java เราเก็บคลาส Student ที่มี attribute **name**, **age** และ **rollNo** และเมธอด **showStdInfo()** ไว้ ส่วนใน main เราจะสร้างอ็อบเจ็กต์ของคลาส Student กำหนดค่าแอตทริบิวต์ของอ็อบเจ็กต์ด้วยการใช้สมาชิกจากตัวอ็อบเจ็กต์ และเรียกใช้เมธอด **showStdInfo()** เพื่อแสดงข้อมูลนักเรียน   
Java และ Dart เป็นภาษาเชิงวัตถุ ดังนั้นแนวคิดและโครงสร้างจึงมีความคล้ายกัน แต่ยังคงมีความแตกต่างในเทคนิคและวิธีการเขียนเชิงลึกที่แตกต่างกันไป
```java
// Defining class
class Student {
    String name;
    int age;
    int rollNo;

    // Defining class method
    void showStdInfo() {
        System.out.println("Student Name is: " + name);
        System.out.println("Student Age is: " + age);
        System.out.println("Student Roll Number is: " + rollNo);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating object called std
        Student std = new Student();
        std.name = "Peter";
        std.age = 24;
        std.rollNo = 90001;
        
        // Accessing class method
        std.showStdInfo();
    }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Student Name is: Peter
Student Age is: 24
Student Roll Number is: 90001</code></pre>
</details>

## Python

### Example
ในภาษา Python เราสร้าง class **Student** และเมธอด __init__ เพื่อกำหนดค่าเริ่มต้นสำหรับ attribute ในคลาส เราไม่ต้องกำหนดชนิดข้อมูลของ attribute เนื่องจาก Python เป็นภาษาที่ไม่ต้องการประกาศชนิดข้อมูลโดยชัดเจน ส่วนเมธอด **showStdInfo()** ถูกเรียกใช้เหมือนกับเมธอดใน Dart และการเข้าถึง attribute ใน Python จะใช้ **self** ในการอ้างอิงถึงแอตทริบิวต์ในคลาส
```python
class Student:
    def __init__(self):
        self.name = ""
        self.age = 0
        self.rollNo = 0
    
    def showStdInfo(self):
        print("Student Name is:", self.name)
        print("Student Age is:", self.age)
        print("Student Roll Number is:", self.rollNo)

# Creating object called std
std = Student()
std.name = "Peter"
std.age = 24
std.rollNo = 90001

# Accessing class method
std.showStdInfo()
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Student Name is: Peter
Student Age is: 24
Student Roll Number is: 90001</code></pre>
</details>

# Reference
https://dart-tutorial.com/object-oriented-programming/object-in-dart/  
https://www.javatpoint.com/dart-classes-and-object  
https://www.geeksforgeeks.org/classes-objects-java/

# Link Video
[Video](https://youtu.be/4Ced4Cb2BHE)

# Slide
[link slide](https://github.com/Sxrxwxlxx/File-Dart/blob/main/Slide_Object_In_Dart.pdf)  
[link download slide](https://github.com/Sxrxwxlxx/File-Dart/blob/main/Slide_Object_In_Dart.pdf?raw=true)
