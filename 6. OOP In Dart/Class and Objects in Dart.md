
# Class and Objects in Dart


# Class คืออะไร ?
Class  จะเปรียบเสมือนกับ Blueprint หรือแบบแปลนสำหรับสร้าง Object แล้ว
Class ยังเป็นตัวกำหนด Properties และ Mehtods ของ Object
ถ้าอยากรู้เกี่ยวกับ Class มากขึ้นให้ไปที่หัวข้อ Class

# Object คืออะไร ?
Object คือตัวอย่างของ Class คุณสามารถสร้างได้หลาย Object ใน Class เดียวกัน
ถ้าอยากรู้เกี่ยวกับ Object มากขึ้นให้ไปที่หัวข้อ Object

# Example Of A Class & Object In Dart
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




