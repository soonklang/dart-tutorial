# Object in dart
**การเขียนโปรแกรมเชิงวัตถุ** Object(วัตถุ) คือ หน่วยของcode และข้อมูลในตัวเอง โดยจะถูกสร้างขึ้นจากเทมเพลสที่เรียกว่า Class(คลาส)  **object** ประกอบด้วย **properties(ตัวแปร)** และ**methods(ฟังก์ชัน)** วัตถุ คือ instanceของclass  
**ตัวอย่าง** objectจักรยาน อาจมีattributes(คุณลักษณะ)ต่างๆ เช่น **color(สี)** , **size(ขนาด)** , **current speed(ความเร็วปัจจุบัน)** อาจมีmethod เช่น changeGear , PadalFaster และ Brake

# Instantiation
การเขียนโปรแกรมเชิงวัตถุ **การสร้าง instantiation** คือ กระบวนการสร้างinstanceของclass หรือจะบอกได้ว่าการสร้าง instantiation เป็นกระบวนการสร้างobjectของclass เช่น หากคุณมีclassชื่อ **Bicycle** จะสามารถสร้างobjectของclassชื่อ **Bicycle** ได้

# Declaring Object In Dart
เมื่อทำการสร้าง class แล้วจะต้องประกาศobject คุณสามารถประกาศ object โดยใช้ syntax ต่อไปนี้:

# Syntax
```dart
ClassName objectName = ClassName();
```

# Example 1: Declaring An Objet In Dart
ตัวอย่างด้านล่างนี้ มีจะมี class **Bicycle** มี properties 3 ประการ: **color** , **size** และ**currentSpeed** ใน class จะมี 2 method คือ **changeGear** ซึ่งเป็นการเปลี่ยนเกียร์ของจักรยาน และ **display** จะพิมพ์ค่า properties ทั้งสามออกมา นอกจากนี้ยังมี object ของ class**Bicycle** ที่calledเรียก**bicycle**
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
ในตัวอย่างนี้มี class **Animal**ทีมี properties 3 ประการ: **name** , **numberOfLegs**และ**lifeSpan** class ยังมี method **display**ที่พิมพ์ค่าของ properties ทั้งสามออกมา และยังมี object ของ class**Animal** ที่เรียกว่า**animal**
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
ในตัวอย่างนี้มี class **Car**ทีมี properties 3 ประการ: **name** , **color**และ**numberOfSeats** class ยังมี method **start**ที่พิมพ์ข้อความ "Car Started" และยังมี object ของ class**Car** ที่เรียกว่า**car**
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
- keyword **new** สามารถใช้เพื่อสร้าง object ใหม่ได้ แต่ไม่จำเป็น

# Difference Between Dart , C , Java and Python
### Dart
```dart
// Defining class  
class Student {  
   String? stdName;  
   int? stdAge;  
   int? stdRoll_nu;  
     
   // defining class function  
    showStdInfo() {  
        print("Student Name is : ${stdName}");  
        print("Student Age is : ${stdAge}");  
        print("Student Roll Number is : ${stdRoll_nu}");  
  
               }  
}  
void main () {  
  
  // Creating object called std  
  var std = new Student();  
  std.stdName = "Peter";  
  std.stdAge =24;  
  std.stdRoll_nu = 90001;  
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

### C
ในภาษา C เราใช้ **struct** เพื่อแทน class ในภาษา Dart โดยการสร้างหนึ่งโครงสร้างที่มีชื่อว่า "Student" ซึ่งประกอบด้วย field ต่างๆ ที่เหมือนกับตัวแปรใน class Dart ในส่วนของการเข้าถึง**ฟังก์ชัน(method)** ใน C นั้นเราเปลี่ยนมันเป็นฟังก์ชันเรียกใช้งานด้วยการส่งค่าโครงสร้างเป็น **Argument** เช่น **showStdInfo(std)** และเราใช้ฟังก์ชัน strcpy จากไลบรารี <string.h> เพื่อคัดลอกชื่อนักเรียนเข้าสู่field stdName ในโครงสร้าง.
```c
#include <stdio.h>

// Defining structure
struct Student {
    char stdName[50];
    int stdAge;
    int stdRoll_nu;
};

// Defining function
void showStdInfo(struct Student std) {
    printf("Student Name is: %s\n", std.stdName);
    printf("Student Age is: %d\n", std.stdAge);
    printf("Student Roll Number is: %d\n", std.stdRoll_nu);
}

int main() {
    // Creating structure variable
    struct Student std;
    strcpy(std.stdName, "Peter");
    std.stdAge = 24;
    std.stdRoll_nu = 90001;

    // Accessing function
    showStdInfo(std);

    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Student Name is: Peter
Student Age is: 24
Student Roll Number is: 90001</code></pre>
</details>

### Java
ใน Java เราเก็บคลาส Student ที่มีแอตทริบิวต์ stdName, stdAge และ stdRoll_nu และเมธอด showStdInfo() ไว้ ส่วนใน main เราจะสร้างอ็อบเจ็กต์ของคลาส Student กำหนดค่าแอตทริบิวต์ของอ็อบเจ็กต์ด้วยการใช้สมาชิกจากตัวอ็อบเจ็กต์ และเรียกใช้เมธอด showStdInfo() เพื่อแสดงข้อมูลนักเรียน   
Java และ Dart เป็นภาษาเชิงวัตถุ ดังนั้นแนวคิดและโครงสร้างจึงมีความคล้ายกัน แต่ยังคงมีความแตกต่างในเทคนิคและวิธีการเขียนเชิงลึกที่แตกต่างกันไป
```java
// Defining class
class Student {
    String stdName;
    int stdAge;
    int stdRoll_nu;

    // Defining class method
    void showStdInfo() {
        System.out.println("Student Name is: " + stdName);
        System.out.println("Student Age is: " + stdAge);
        System.out.println("Student Roll Number is: " + stdRoll_nu);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating object called std
        Student std = new Student();
        std.stdName = "Peter";
        std.stdAge = 24;
        std.stdRoll_nu = 90001;
        
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

### Python
ในภาษา Python เราสร้าง class Student และเมธอด **__init__** เพื่อกำหนดค่าเริ่มต้นสำหรับ attribute ในคลาส เราไม่ต้องกำหนดชนิดข้อมูลของแอตทริบิวต์เนื่องจาก Python เป็นภาษาที่ไม่ต้องการประกาศชนิดข้อมูลโดยชัดเจน ส่วนเมธอด **showStdInfo()** ถูกเรียกใช้เหมือนกับเมธอดใน Dart และการเข้าถึง attribute ใน Python จะใช้ **self** ในการอ้างอิงถึงแอตทริบิวต์ในคลาส
```python
class Student:
    def __init__(self):
        self.stdName = ""
        self.stdAge = 0
        self.stdRoll_nu = 0
    
    def showStdInfo(self):
        print("Student Name is:", self.stdName)
        print("Student Age is:", self.stdAge)
        print("Student Roll Number is:", self.stdRoll_nu)

# Creating object called std
std = Student()
std.stdName = "Peter"
std.stdAge = 24
std.stdRoll_nu = 90001

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
