
# Class and Objects in Dart


# Class คืออะไร ?
Class  จะเปรียบเสมือนกับ Blueprint หรือแบบแปลนสำหรับสร้าง Object แล้ว
Class ยังเป็นตัวกำหนด Properties และ Mehtods ของ Object
ถ้าอยากรู้เกี่ยวกับ Class มากขึ้นให้ไปที่หัวข้อ [Class in Dart](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Class%20in%20Dart.md)

# Object คืออะไร ?
Object คือตัวอย่างของ Class คุณสามารถสร้างได้หลาย Object ใน Class เดียวกัน
ถ้าอยากรู้เกี่ยวกับ Object มากขึ้นให้ไปที่หัวข้อ [Objects in Dart](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Object%20in%20dart.md)

# ตัวอย่าง Class และ Object ในภาษา Dart
ตัวอย่างข้างล่างนี้จะมี Class Animal มี properties 3 อย่าง คือ
name(ชื่อ) , numberOfLegs(จำนวนขา) และ lifeSpan(อายุไข) และ Class จะมี method ชื่อ display
ซึ่งจะพิมพ์ค่า properties ทั้ง 3 อย่างออกมา

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

# ตัวอย่าง 2: หาพื้นที่สี่เหลี่ยมผืนผ้าโดยใช้ Class และ Objects
ตัวอย่างข้างล่างนี้จะมี Class Rectangle(สี่เหลี่ยมผืนผ้า) มี properties 2 อย่าง คือ
length(ความยาว) และ breadth(ความกว้าง) และ Class จะมี method ชื่อ area(พื้นที่)
ซึ่งจะพิมพ์ค่าพื้นของสี่เหลี่ยมผืนผ้า
```dart
class Rectangle{
  //properties of rectangle
  double? length;
  double? breadth;
  
  //functions of rectangle
  double area(){
    return length! * breadth!;
  }
}

void main(){
  //object of rectangle created
  Rectangle rectangle = Rectangle();
  
  //setting properties for rectangle
  rectangle.length=10;
  rectangle.breadth=5;
  
  //functions of rectangle called
  print("Area of rectangle is ${rectangle.area()}.");
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Area of rectangle is 50.</code></pre>
</details>

# ตัวอย่าง 2: หาค่าดอกเบี้ย แบบง่ายๆ โดยใช้ Class และ Objects
ตัวอย่างข้างล่างนี้จะมี Class SimpleInterest(คำนวนดอกเบี้ยง่ายๆ) มี properties 3 อย่าง คือ
principal(เงินต้น) ,rate(อัตราดอกเบี้ย) และtime(ระยะเวลา) และ Class จะมี method
interest(ดอกเบี้ย) ซึ่งจะพิมพ์ค่าคำนวนดอกเบี้ย แบบวิธีง่ายๆ
```dartclass SimpleInterest{
  //properties of simple interest
  double? principal;
  double? rate;
  double? time;
  
  //functions of simple interest
  double interest(){
    return (principal! * rate! * time!)/100;
  }
}
void main(){
  //object of simple interest created
  SimpleInterest simpleInterest = SimpleInterest();
  
  //setting properties for simple interest
  simpleInterest.principal=1000;
  simpleInterest.rate=10;
  simpleInterest.time=2;
  
  //functions of simple interest called
  print("Simple Interest is ${simpleInterest.interest()}.");
  }
  ```
  
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Simple Interest is 200..</code></pre>
</details>

# Reference
https://dart-tutorial.com/object-oriented-programming/class-and-objects-in-dart/

