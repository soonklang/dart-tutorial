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

# ตัวอย่างที่ 1: Declaring An Objet In Dart
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

# ตัวอย่างที่ 2: Declaring Animal Class Object In dart
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


# ตัวอย่างที่ 3: Declaring Car Class Object In dart
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


# Difference Between Dart and Java and Python


# Reference
