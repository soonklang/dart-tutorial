# Abstract Class in Dart
---

## INTRODUCTION

  ในบทนี้จะได้เรียนรู้เกี่ยวกับ  abstract class ใน ภาษา dart ก่อนที่จะลงลึกเนื้อหากันในบทนี้ 
  จะต้องมีพื้นฐานความเข้าใจเกี่ยวกับ  class, object, constructor, and inheritance. ก่อนในบทที่ผ่านมาเราจะได้เรียนรู้การประกาศ คลาส กัน 
  ซึ่ง คลาส เหล่านั่นเรียกว่า concrete classes และ concrete class ก็สร้างเป็น object ได้ แต่ใน abstract class นั่นสร้างเป็น object ไม่ได้นะจ้ะ  



## Abstract Class
  
  Abstract Class คือ คลาส ที่ไม่สามารถสร้าง object หรือ สร้างเป็นตัวแปรได้ มันถูกใช้เพื่อบอกว่า คลาส นี้  มี method การทำงานอะไรบ้าง 
  เพื่อที่จะให้ คลาส อื่นนั่นสืบทอดการทำงานต่อไปนั่นเอง keyword ในการใช้ก็คือ abstract
	
# Syntax
```dart
abstract class ClassName {
  //Body of abstract class

  method1();
  method2();
}
```


## Abstract Method
   
   abstract method คือ method ที่มีเครื่องหมาย  `semicolon(;)` ปิดท้าย และไม่มีการทำงานใน method เป็นแค่การประกาศไว้เพื่อบอกว่า class นี้มี method เท่านี้นะ 
   และให้ class อื่น ที่สืบทอดต่อไปปรับเปลี่ยนข้างในกันเอง
# Syntax
```dart
abstract class ClassName {
  //Body of abstract class
  method1();
  method2();
}
```
## ทำไมต้อง Abstract Class
	
 คลาส ลูก ที่สืบทอด  abstract class ทั้งหมดจะต้องประกาศ method ที่มีอยู๋ใน abstract class ทั้งหมด  และเพราะการใช้สิ่งนี้จะทำให้เกิด `Abstraction` ใน Dart programing language


## ตัวอย่างที่ 1: Abstract Class ใน Dart
	
  ในตัวอย่างโค้ดข้างล่างนั่น มี abstract class `Vehicle` และข้างในมี method `start()` และ `stop()` อยู่
  class ลูกจะต้องเอา method ไปใส่ไว้ในตัวของมันเองและมันก็เปลี่ยนการทำงานข้างในด้วย overide และปริ้นข้อความออกมา


```dart
abstract class Vehicle {
  // Abstract method
  void start();
  // Abstract method
  void stop();
}

class Car extends Vehicle {
  // Implementation of start()
  @override
  void start() {
    print('Car started');
  }

  // Implementation of stop()
  @override
  void stop() {
    print('Car stopped');
  }
}

class Bike extends Vehicle {
  // Implementation of start()
  @override
  void start() {
    print('Bike started');
  }

  // Implementation of stop()
  @override
  void stop() {
    print('Bike stopped');
  }
}

void main() {
  Car car = Car();
  car.start();
  car.stop();

  Bike bike = Bike();
  bike.start();
  bike.stop();
}
```

**ผลลัพธ์:**
```
Car started
Car stopped
Bike started
Bike stopped
```
  

>[!NOTE]
> **ข้อมูลเพิ่มเติม:** 
>	abstract class ถูกใช้เพื่อบอกว่ามี method อะไรบ้างและถูกสืบทอดด้วย class อื่น และสามารถประกาศ abstract method ใน abstract classได้

## ตัวอย่างที่ 2: Abstract Class ใน Dart
	
   ในตัวอย่างข้างล่างนี้ มี abstract class `Shape` ที่มี method อยู่คือ `area()` และคลาสลูก `Rectangle` และ `Triangle`
   คลาสลูกได้ทำการสืบทอด method `area()` มา และ overide มันเพื่อคำนวณหาพื้นทีของสี่เหลี่ยมและสามเหลี่ยม 

```dart
abstract class Shape {
  int dim1, dim2;
  // Constructor
  Shape(this.dim1, this.dim2);
  // Abstract method
  void area();
}

class Rectangle extends Shape {
  // Constructor
  Rectangle(int dim1, int dim2) : super(dim1, dim2);

  // Implementation of area()
  @override
  void area() {
    print('The area of the rectangle is ${dim1 * dim2}');
  }
}

class Triangle extends Shape {
  // Constructor
  Triangle(int dim1, int dim2) : super(dim1, dim2);

  // Implementation of area()
  @override
  void area() {
    print('The area of the triangle is ${0.5 * dim1 * dim2}');
  }
}

void main() {
  Rectangle rectangle = Rectangle(10, 20);
  rectangle.area();

  Triangle triangle = Triangle(10, 20);
  triangle.area();
}
```   

**ผลลัพธ์:**
```
The area of the rectangle is 200
The area of the triangle is 100.0
```

## การกำหนด  Constructor ใน Abstract Class
	
  ใน abstract class นั่นสร้าง object ไม่ได้ก็จริง แต่อย่างไรก็ตาม เราสามารถกำหนด constructor ใน abstract class ได้
	constructor ใน abstract class จะถูกเรียกเมื่อ object ของคลาสอื่นถูกสร้างขึ้น
	
## ตัวอย่างที่ 3 Constructor ใน  Abstract Class
	
  ในตัวอย่างข้างล่างนี้  จะมี abstract class `Bank` ที่มี constructor รับค่ามาสองพารามิเตอร์คือ `name` และ `rate`.
	มี abstract method `interest()` คลาสลูก `SBI` และ `ICICI` ที่ทำการ overide abstract method จาก คลาส `Bank`


```dart   
abstract class Bank {
  String name;
  double rate;

  // Constructor
  Bank(this.name, this.rate);

  // Abstract method
  void interest();

  //Non-Abstract method: It have an implementation
  void display() {
    print('Bank Name: $name');
  }
}

class SBI extends Bank {
  // Constructor
  SBI(String name, double rate) : super(name, rate);

  // Implementation of interest()
  @override
  void interest() {
    print('The rate of interest of SBI is $rate');
  }
}

class ICICI extends Bank {
  // Constructor
  ICICI(String name, double rate) : super(name, rate);

  // Implementation of interest()
  @override
  void interest() {
    print('The rate of interest of ICICI is $rate');
  }
}

void main() {
  SBI sbi = SBI('SBI', 8.4);
  ICICI icici = ICICI('ICICI', 7.3);

  sbi.interest();
  icici.interest();
  icici.display();
}
```   




**ผลลัพธ์:**
```
The rate of interest of SBI is 8.4
The rate of interest of ICICI is 7.3
Bank Name: ICICI
```

#  Abstract Class ใน Java
---

## ตัวอย่าง 1 abstract class ใน Java
```java
abstract class Shape{  
abstract void draw();  
}  
//In real scenario, implementation is provided by others i.e. unknown by end user  
class Rectangle extends Shape{  
void draw(){System.out.println("drawing rectangle");}  
}  
class Circle1 extends Shape{  
void draw(){System.out.println("drawing circle");}  
}  
//In real scenario, method is called by programmer or user  
class TestAbstraction1{  
public static void main(String args[]){  
Shape s=new Circle1();//In a real scenario, object is provided through method, e.g., getShape() method  
s.draw();  
}  
}  
```
**ผลลัพธ์:**
```
drawing circle
```

## ตัวอย่าง 2 abstract class ใน Java
```java
abstract class Bank{    
abstract int getRateOfInterest();    
}    
class SBI extends Bank{    
int getRateOfInterest(){return 7;}    
}    
class PNB extends Bank{    
int getRateOfInterest(){return 8;}    
}    
    
class TestBank{    
public static void main(String args[]){    
Bank b;  
b=new SBI();  
System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");    
b=new PNB();  
System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");    
}}    
```
**ผลลัพธ์:**
```
Rate of Interest is: 7 %
Rate of Interest is: 8 %
```

# Video
[Abstract in dart Youtube](https://www.youtube.com/watch?v=j8mrUyRI2IE&classId=e5e2b274-bbc3-4a1a-933d-44e26250f3fa&assignmentId=8b90540e-3a0f-49f4-bce2-c7b86d9501ec&submissionId=74dba728-a705-b527-04cd-42431099fb28)

# Slide
 - [Abstract in Dart Slide](https://drive.google.com/file/d/1lfvuEmXPDg_zFe_iMWN-vyUl45tZDapP/view?usp=sharing)
 - [Abstract in Dart Slide (version2)](https://drive.google.com/file/d/1M29HLUyIcxhJPcaD-dh1zCN7Hh26O_6s/view?usp=sharing)
 - [Abstract in Dart Slide (version3) ](https://drive.google.com/file/d/1fXBafX2_ky_kYNf3oU2oGYJBX6llaBYD/view?usp=sharing)



## จุดสำคัญที่ต้องจำในเรื่องนี้
  - **Abstract class สร้าง object ไม่ได้**
  - **Abstract class มีได้ทั้ง  method ปกติ และ abstract method**
  - **สร้างขึ้นเพื่อบอกการทำงานในคลาส(abstract class)แล้วให้คลาสอื่นมาสืบทอด**
  - **abstract method เป็นคลาสที่ไม่มีการทำงานและมีเพียงลายเซ็นหรือก็คือ semicolon(;)ปิดท้าย**

# Reference(s)
  - https://www.javatpoint.com/abstract-class-in-java
  - https://dart-tutorial.com/object-oriented-programming/abstract-class-in-dart/

  

