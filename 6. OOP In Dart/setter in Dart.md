# Setter in Dart
  - ใช้ตั้งค่าข้อมูลในตัวแปรที่ได้รับจากเมธอด getter
  - คือการที่เรารับค่าค่าหนึ่งเข้ามาเพื่อนำมาตั้งค่าตัวแปรนั้น ๆ ใน method
  - ทุกคลาสมี default setter method
# Syntax
```dart
set field_name() {
  ...
}
```
**set** เป็น keyword ที่ใช้บอกคอมไพลเลอร์ว่านี่คือ method setter <br>
**field_name()** คือ ชื่อของ method โดยในวงเล็บจะเป็นพารามิเตอร์ที่รับค่าเข้ามา เพื่อเปลี่ยนค่าใน method <br>
**หมายเหตุ** ด้านหน้าของ keyword set สามารถใส่ตัวกำหนดการคืนค่าได้ เช่น void, int, float
# ตัวอย่าง การใส่ตัวกำหนดการคืนค่า
 ```dart
void set employeeName(String name) {
  this.empName = name;
}
```
# ตัวอย่างโปรแกรม
 ```dart
// Creating Class named Gfg
class Gfg {
// Creating a Field/Property
String geekName;

// Creating the getter method
// to get input from Field/Property
String get getName {
	return geekName;
}

// Creating the setter method
// to set the input in Field/Property
set setName(String name) {
	geekName = name;
}
}

void main() {
// Creating Instance of class
Gfg geek = Gfg();

// Calling the set_name method(setter method we created)
// To set the value in Property "geekName"
geek.setName = "GeeksForGeeks";

// Calling the get_name method(getter method we created)
// To get the value from Property "geekName"
print("Welcome to ${geek.getName}");
}

```

## **Reference**
[geeksforgeeks](https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/)
<br>
[tutorialspoint](https://www.tutorialspoint.com/getter-and-setter-in-dart-programming)
<br>
