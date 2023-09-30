
# Interface in Dart
Interface คือ การกำหนดโครงสร้างของ methood ขึ้นมาอาจไม่มีการกำหนดรายละเอียด การทำงานใดๆ  แต่อาจจะถูกสืบทอดและกำหนดรายละเอียด ของ Interface นั้น คลาสที่ implement ก็จะมี methood ที่เรียกใช้งานได้ 
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
จะเห็นว่า ไม่ต้องใช้ interface keyword หน้าชื่อคลาสแม่แบบที่ต้องการให้implement  
 ในภาษา Dart จะมองว่าทุกๆ class เป็น interface สามารถนำไปใช้งานได้เลย 
# Syntax ของ java 
```java
interface Animal {

  public void sleep(); 
}
class Print implements Animal{
  public void sleep(){
System.out.println("หลับ");
   }
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
   Calculator c = Calculator();
   print("The gross total : ${c.ret_tot()}");
   print("Discount : ${c.ret_dis()}");
}

 abstract class Calculate_Total {
   int ret_tot();
}

 abstract class Calculate_Discount {
   int ret_dis();
}

class Calculator implements Calculate_Total, Calculate_Discount {
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
1.การนิยามเมทอด: เมทอดในอินเทอร์เฟซจะถูกนิยามเป็น abstract และต้องถูกนิยามใหม่ในคลาสที่ Implement อินเทอร์เฟซนั้น ถ้าคุณละเมทอดหรือทำผิดพลาดในการระบุเมทอดจากอินเทอร์เฟซ จะทำให้เกิดข้อผิดพลาด.<br>

2.การสร้างอินสแตนซ์: อินสแตนซ์ของคลาสที่ Implement อินเทอร์เฟซจะต้องนำเอาทุกเมทอดในอินเทอร์เฟซมานิยามใหม่ ไม่ว่าจะมีการใช้งานเมทอดนั้นหรือไม่.<br>

3.การอัปเดต: หากคุณเพิ่มเมทอดใหม่ในอินเทอร์เฟซที่มีคลาส Implement แล้ว คุณจะต้องอัปเดตทุกคลาสที่ Implement อินเทอร์เฟซนั้น เพื่อนิยามเมทอดใหม่ด้วย.<br>

4.สองคลาสอาจมีเมทอดชื่อเดียว: ถ้าคุณมีคลาสที่ Implement หลายอินเทอร์เฟซ และอินเทอร์เฟซเหล่านี้มีเมทอดที่มีชื่อเดียวกัน คุณจะต้องสร้างการนิยามของเมทอดที่ชื่อซ้ำนี้ในคลาสที่ Implement และระบุการทำงานที่ถูกต้องในแต่ละเมทอด.<br>





# สรุปการใช้ Interface in Dart
1การประกาศ Interface:<br>
-ใช้ abstract class เพื่อประกาศ Interface.<br>
-นิยามเมทอดใน Interface แบบ abstract โดยไม่ระบุรายละเอียดการทำงาน.<br>
2การ Implement Interface:<br>
-ใช้คีย์เวิร์ด implements เมื่อประกาศคลาสที่จะ Implement Interface.<br>
-นิยาม (override) เมทอดที่ปรากฏใน Interface ในคลาสที่ Implement โดยใช้ @override และระบุรายละเอียดการทำงานของเมทอด.<br>
3การสร้างอินสแตนซ์:<br>
-สามารถสร้างอินสแตนซ์ของคลาสที่ Implement Interface และเรียกใช้งานเมทอดของ Interface ได้.<br>
4การใช้งานหลาย Interface:<br>
-คลาสสามารถ Implement หลาย Interface พร้อมกัน โดยใช้ , เพื่อคั่นระหว่างชื่อ Interface.<br>
5การเปลี่ยนแปลง Interface:<br>
หากมีการเปลี่ยนแปลงใน Interface โดยการเพิ่มหรือลบเมทอด คุณต้องปรับปรุงทุกคลาสที่ Implement Interface นั้น.<br>

การใช้งาน Interface ช่วยให้คุณสามารถสร้างโค้ดที่มีโครงสร้างและสัญญาที่มั่นใจได้ และสนับสนุนความยืดหยุ่นในการสร้างคลาสที่ต้องการนำไปใช้ในที่ต่าง ๆ โดยใช้รูปแบบที่ถูกกำหนดล่วงหน้าใน Interface.<br>
# Reference
https://dart-tutorial.com/object-oriented-programming/interface-in-dart/<br>
https://www.geeksforgeeks.org/interface-in-dart/<br>
https://www.educative.io/answers/what-is-an-interface-in-dart/<br>
https://www.darttutorial.org/dart-tutorial/dart-interface/<br>
https://www.javatpoint.com/dart-interfaces<br>
