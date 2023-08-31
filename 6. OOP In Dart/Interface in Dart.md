
# Interface in Dart
Interface คือ การกำหนดโครงสร้างของ methood ขึ้นมาไม่มีการกำหนดรายละเอียด การทำงานใดๆ โดยทุก method จะไม่อนุญาตให้เรียกใช้ทำงาน แต่จะถูกสืบทอดและกำหนดรายละเอียด ของ Interface นั้น คลาสที่ implement ก็จะมี methood ที่เรียกใช้งานได้
-----------------------------------------------------------------------------
# Syntax ของ Dart
```dart
class Interface_class_name{
   ...
}

class Class_name implements Interface_class_name {
   ...
}
```
จะเห็นว่า ไม่ต้องเติมคำว่า interface หน้าชื่อคลาสแม่แบบที่ต้องการให้implement  
 ในภาษา Dart จะมองว่าทุกๆ class เป็น interface สามารถนำไปใช้งานได้ โดยไม่ต้องใช้ interface keyword
# Syntax ของ java 
```java
interface Animal {
  public void animalSound(); 
  public void sleep(); 
}
```
# ตัวอย่างการใช้ Interface ในภาษา Dart
```dart
class Zoo {
  void Animal() {
    print("มีช้าง มีแมว");
  }
}
 
// class Khao_kheow_zoo implementing class Zoo
class Khao_kheow_zoo implements Zoo {

  void Animal() {
    print("สวนสัตว์เขาเขียวมี สิงโต ม้าลาย อย่างล่ะตัว");
  }
}
 
void main() {
  // creating instance of Class khao_kheow_zoo
  var khao_kheow_zoo = Khao_kheow_zoo();
  khao_kheow_zoo.Animal();
}
```
Output
```
สวนสัตว์เขาเขียวมี สิงโต ม้าลาย อย่างล่ะตัว
```
# การใช้ Implementing Multiple Interfaces
```dart
void main() { 
   Calculator c = new Calculator(); 
   print("The gross total : ${c.ret_tot()}"); 
   print("Discount :${c.ret_dis()}"); 
}  
class Calculate_Total { 
   int ret_tot() {} 
}  
class Calculate_Discount { 
   int ret_dis() {} 
}                                     //ใช้ " , " ในการใช้ implements หลาย class
class Calculator  implements Calculate_Total,Calculate_Discount { 
   int ret_tot() { 
      return 1000; 
   } 
   int ret_dis() { 
      return 50; 
   } 
}
```
Output
```
The gross total: 1000 
Discount:50 
```
# สรุปการใช้ Interface in Dart
1.ใช้เพื่อสืบทอดmethod ของคลาสแม่แบบ
2.คลาสสามารถขยายได้เพียงคลาสเดียว แต่สามารถนำไปใช้ได้มากเท่าที่คุณต้องการ
3.Dart ไม่มีวิธีการโดยตรงในการประกาศอินเทอร์เฟซ ดังนั้นการประกาศคลาสจึงถือเป็นการประกาศบนอินเทอร์เฟซ
