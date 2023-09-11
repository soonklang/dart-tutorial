# *Getter and Setter in Dart*
Getter และ Setter เป็นวิธีการเข้าถึงหรือเปลี่ยนแปลงคุณสมบัติ (Properties) ในวัตถุ(Object)นั้นๆ
ในการเขียนภาษา Dart เราจะใช้คำว่า get กับ set เป็น Keywords ในการกำหนด Getter กับ Setter
โดยที่ Getter ทำหน้าที่รับค่าของคุณสมบัติของวัตถุและทำหน้าที่เป็นตัวเข้าถึง ส่วน Setter มีหน้าที่แก้ไขค่าของคุณสมบัติในวัตถุและทำหน้าที่เป็นตัวปรับเปลี่ยนค่าของคุณสมบัตินั้น


  # *ข้อดีของการใช้ Getter&Setter*
  - สามารถตรวจสอบการข้อมูลก่อนจะทำการอ่านหรือเขียนข้อมูล
  - จำกัดการอ่านและเขียนข้อมูลได้ทำให้ข้อมูลปลอดภัยมากยิ่งขึ้น
  - สามารถสั่งให้ทำ action บางอย่างก่อนที่จะอ่านหรือเขียนข้อมูล เช่น การบันทึกข้อมูลเข้าสู่ระบบ
  

  ## *Content*
  - [Syntax](#syntax)
  - [Example 1 : Basic Getter & Setter](#example-1-basic-getter-and-setter)
  - [Example 2 : Read-Only Property](#example-2-read-only-property)

## *Syntax*
เราสามารถเขียน Syntax ของ Getter ได้ดังนี้
```dart
return_type get property_name{
  //Getter body
}
```
เราสามารถเขียนการเรียกใช้ Getter ให้กระชับยิ่งขึ้นโดยใช้เครื่องหมาย arrow syntax

```dart
return_type get property_name => value;
```
ส่วน Syntax ของ Setter สามารถเขียนได้ดังนี้
```dart
set property_name (value) {
  // Setter body
}
```
เช่นเดียวกันกับ Getter เราสามารถทำให้โค้ดเราสั้นขึ้นโดยใช้ arrow syntax
```dart
set property_name(value_type value) => this.private_property = value;
```

# *Example 1* Basic Getter and Setter
```dart
class Circle {
  double radius;

  Circle(this.radius);

  double get circumference => 2 * 3.1415 * radius;

  set diameter(double value) {
    radius = value / 2;
  }
}

void main() {
  var myCircle = Circle(5.0);
  print("Radius: ${myCircle.radius}");
  print("Circumference: ${myCircle.circumference}");

  myCircle.diameter = 10.0;
  print("New Radius: ${myCircle.radius}");
}
```

## *Example 2* Read Only Property
```dart
class Temperature {
  double _celsius;

  Temperature(this._celsius);

  double get celsius => _celsius;
  double get fahrenheit => _celsius * 9 / 5 + 32;
}

void main() {
  var temp = Temperature(25.0);
  print("Celsius: ${temp.celsius}");
  print("Fahrenheit: ${temp.fahrenheit}");
}
```
