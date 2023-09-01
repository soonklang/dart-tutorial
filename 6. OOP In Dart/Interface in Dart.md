
# Interface in Dart
Interface คือ การกำหนดโครงสร้างของ methood ขึ้นมาอาจไม่มีการกำหนดรายละเอียด การทำงานใดๆ โดยทุก method จะไม่อนุญาตให้เรียกใช้ทำงาน แต่จะถูกสืบทอดและกำหนดรายละเอียด ของ Interface นั้น คลาสที่ implement ก็จะมี methood ที่เรียกใช้งานได้ 
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
# ตัวอย่างการใช้ Interface ในภาษา Java 
```java
import java.io.*;
 
interface Songs {
   
    // public, static and final
    final int like = 32000;
 
    // public and abstract
    void Name();
}
 
// A class that implements the interface.
class Mv implements Songs {
   
    // Implementing the capabilities of
    // interface.
    public void Name(){
      System.out.println("เพลงชาติไทย");
    }
 
    // Driver Code
    public static void main(String[] args)
    {
        Mv v = new Mv();
        v.Name();
        System.out.println(like);
    }
}

```
Output
```
เพลงชาติไทย
32000
```

# ตัวอย่างการใช้ Implementing Multiple Interfaces Dart
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
# สิ่งที่ต้องระวัง
แม้ว่าการใช้งานหลายอินเทอร์เฟซจะมีประสิทธิภาพ แต่มาพร้อมกับความท้าทาย:<br>

ความซับซ้อน : ยิ่งคลาสใช้อินเทอร์เฟซมากเท่าใด คลาสก็จะยิ่งซับซ้อนมากขึ้นเท่านั้น จำเป็นอย่างยิ่งที่จะต้องรักษาสมดุลเพื่อหลีกเลี่ยงการเขียนCodeที่ซับซ้อนเกินไป<br>
วิธีการทับซ้อนกัน : หากสองอินเทอร์เฟซมีวิธีการที่มีชื่อเดียวกัน แต่มีฟังก์ชันการทำงานที่แตกต่างกัน อาจนำไปสู่ความสับสนได้<br>
# สรุปการใช้ Interface in Dart
1.ใช้เพื่อสืบทอดmethod ของคลาสแม่แบบ

2.คลาสสามารถขยายได้เพียงคลาสเดียว แต่สามารถนำไปใช้ได้มากเท่าทีเราต้องการ

3.Dart ไม่มีวิธีการโดยตรงในการประกาศอินเทอร์เฟซ ดังนั้นการประกาศคลาสจึงถือเป็นการประกาศบนอินเทอร์เฟซ

4.คลาสย่อยจะต้องแทนที่ฟิลด์ของอินเทอร์เฟซ

5.เราสามารถใช้อินเทอร์เฟซหนึ่งหรือหลายอินเทอร์เฟซพร้อมกันได้
# Reference
https://dart-tutorial.com/object-oriented-programming/interface-in-dart/<br>
https://www.geeksforgeeks.org/interface-in-dart/<br>
https://www.educative.io/answers/what-is-an-interface-in-dart/<br>
https://www.darttutorial.org/dart-tutorial/dart-interface/<br>
https://www.javatpoint.com/dart-interfaces<br>
