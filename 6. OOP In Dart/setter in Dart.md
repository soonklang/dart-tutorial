# Setter in Dart
  - ใช้ตั้งค่าข้อมูลในตัวแปรที่ได้รับจากพารามิเตอร์
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
# ตัวอย่างโปรแกรมภาษา Dart
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
# ตัวอย่างโปรแกรมภาษา C
 ```c
#include <stdio.h>
int x;
void main() {
    set_x(5);
    printf("%d", get_x());
}

void set_x(int n) {
    x = n;
}

int get_x() {
    return x;
}

```
# ตัวอย่างโปรแกรมภาษา Java
 ```java
class Person {
  private String name; 
  // Getter
  public String getName() {
    return name;
  }
  // Setter
  public void setName(String newName) {
    this.name = newName;
  }
}

class Main {
    public static void main(String[] args) {
        Person p = new Person();
        p.setName("Hello");
        System.out.println(p.getName());
    }
}

```
# ตัวอย่างโปรแกรมภาษา Python
 ```python
class Geek:
    def __init__(self, age = 0):
         self._age = age
      
    # getter method
    def get_age(self):
        return self._age
      
    # setter method
    def set_age(self, x):
        self._age = x
  
raj = Geek()
  
# setting the age using setter
raj.set_age(21)
  
# retrieving age using getter
print(raj.get_age())
  
print(raj._age)

```

## **สไลด์**
[คลิกที่นี่!!](https://drive.google.com/file/d/1dfFgtl8jblZoBKNAJj6HLkppwFGeeuR9/view?usp=sharing)
<br>

## **คลิปการสอน**
[คลิกที่นี่!!](https://www.youtube.com/watch?v=MP-wzHpVKoI&ab_channel=AtthayaThongkhum)
<br>

## **Reference**
[เนื้อหาส่วนที่ 1](https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/)
<br>
[เนื้อหาส่วนที่ 2](https://www.tutorialspoint.com/getter-and-setter-in-dart-programming)
<br>
[setter in C](https://stackoverflow.com/questions/27316233/getters-and-setters-in-pure-c)
<br>
[setter in Java](https://www.w3schools.com/java/java_encapsulation.asp)
<br>
[setter in Python](https://www.geeksforgeeks.org/getter-and-setter-in-python/)
<br>
