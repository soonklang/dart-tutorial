
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
  void animal() {
    print("มีช้าง มีแมว");
  }
}
 
// class Panda implementing class Zoo
class Panda implements Zoo {

  void animal() {
    print("สวนสัตว์มี แพนด้า 2 ตัว");
  }
}
 
void main() {
  // creating instance of Class Panda
  var panda = Panda();
 panda.animal();
}
```
Output
```
สวนสัตว์มี แพนด้า 2 ตัว
```
# เปรียบเทียบกับภาษา Java 
```java
interface Zoo {
   public void Animal(); 
      }

// class Panda implementing class Zoo
public class Panda implements Zoo {

  public void Animal() {
        System.out.println("สวนสัตว์มี แพนด้า 2 ตัว ");
    }

    public static void main(String[] args) {
        // สร้างอินสแตนซ์ของคลาส Khao_kheow_zoo
        Panda panda = new Panda();
        panda.Animal();
    }
}
```
Output
```
สวนสัตว์มี แพนด้า 2 ตัว
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
   Bank c = Bank();
   print("coinSilver : ${c.coinSilver()}");
   print("coinGold : ${c.coinGold()}");
}

 abstract class Silver {
   int coinSilver();
}

 abstract class Gold  {
   int coinGold();
}

class Bank implements Silver, Gold {
   int coinSilver() {
      return 1000;
   }
   int coinGold() {
      return 50;
   }
}


```
Output
```
coinSilver: 1000 
coinGold:50 
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

3การใช้งานหลาย Interface:<br>

   -คลาสสามารถ Implement หลาย Interface พร้อมกัน โดยใช้ , เพื่อคั่นระหว่างชื่อ Interface.<br>

4การเปลี่ยนแปลง Interface:<br>

   -หากมีการเปลี่ยนแปลงใน Interface โดยการเพิ่มหรือลบเมทอด คุณต้องปรับปรุงทุกคลาสที่ Implement Interface นั้น.<br>


# Reference
https://dart-tutorial.com/object-oriented-programming/interface-in-dart/<br>
https://www.geeksforgeeks.org/interface-in-dart/<br>
https://www.educative.io/answers/what-is-an-interface-in-dart/<br>
https://www.darttutorial.org/dart-tutorial/dart-interface/<br>
https://www.javatpoint.com/dart-interfaces<br>

# Slide & Video
https://docs.google.com/presentation/d/1oADlS_xcE9EhjZayu_g-1ViwulF1Dc2WgGdxgK8i7ck/edit?usp=sharing<br>
https://youtu.be/bX7q5cZDatQ?feature=shared<br>
