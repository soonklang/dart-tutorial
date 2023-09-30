# Extension in Dart
## Introduction to Dart extension methods
ฟีเจอร์ Extension Methods เป็นฟีเจอร์ที่เข้ามาเพื่อช่วยให้เราสามารถเพิ่มความสามารถของ Class โดยที่ไม่ต้องใช้ Inheritance นั่นหมายความว่าความสามารถใด ๆ ก็ตามที่เราเพิ่มเข้าไปนั้น จะสามารถเรียกใช้งานผ่าน Class เดิมได้เลย

## Dart extension method syntax
method ของการใช้งาน Extension dart จะเป็นดังนี้

```dart
extension <extension name> on <type> {
  (<member definition>)*
}
   ```

> การใช้ Extension ควรประกาศอยู่ส่วนบนสุดของไฟล์ หรือก็คือไม่ควรประกาศใช้ภายใน Function หรือ Class

Extension name นั้นสามารถละไว้ได้ แต่ที่ Dart แนะนำให้เราตั้งชื่อด้วยนั้น เนื่องจากเราไม่รู้ว่านักพัฒนาคนอื่น ๆ ในทีมจะมีการตั้งชื่อ Method ใน Extension ซ้ำกับเราหรือไม่ ซึ่งอาจทำให้เกิดความสับสน

ภายในส่วนขยาย เราสามารถนิยาม method ได้ โดยใน method เหล่านี้ คำสั่ง this จะอ้างอิงถึงอินสแตนซ์ปัจจุบันของชนิด (type) นั้น

นอกเหนือจาก method เรายังสามารถเพิ่มสมาชิกอื่น ๆ เช่น `getter`, `setter`, และ `operator` ได้

## Static types and dynamic
- Static Types และ Extension Methods:

  Extension methods ใน Dart ถูกแก้ไขตาม static type ของตัวแปรผู้รับ (receiver) ไม่ใช่ตามประเภทที่เป็นจริงในเวลาทำงาน (runtime type) นั่นหมายความว่าคอมไพเลอร์กำหนดว่าจะเรียก extension method ใดตามประเภทที่ประกาศไว้ในตัวแปร ไม่ใช่ตามค่าที่จะถือเป็นค่าจริงในเวลาทำงาน

- Dynamic และ Extension Methods:

  เราไม่สามารถเรียกใช้ extension method บนตัวแปรที่มีประเภท dynamic ได้ ดังนี้
  ```dart
  dynamic d = '2';
  print(d.parseInt()); // เมื่อ run จะเกิด error ดังนี้: NoSuchMethodError 
    ```

- Extension Methods และ Type Inference:

  Extension methods สามารถทำงานร่วมกับการ Type Inference ของ Dart ได้เสมอ โค้ดต่อไปนี้ถูกต้องเนื่องจากตัวแปร v ถูก Type Inference เป็น String
  ```dart
  var v = '2';
  print(v.parseInt()); // Output: 2
    ```


## Example 1
สมมติว่าเรามี Class ที่เราใช้งานจาก `Third-party Library` ใช้ในการสร้าง ลูกอม (Candy) ขึ้นมา สำหรับโรงงานของเรา ดังนี้

```dart
class Candy {
  final List<String> _flavors = [];
  final int _sweetness;

  Candy(this._sweetness);

  String get detail =>
      'This candy has degree of sweetness at $_sweetness and has the following flavor(s): $_flavors';

  void addFlavor(String flavor) {
    _flavors.add(flavor);
  }
}
   ```

แต่แล้วโรงงานของเราตัดสินใจว่าลูกอมจะต้องมีลูกเล่นใหม่ ๆ เพื่อให้แข่งขันกับคู่แข่งได้ โดยการที่รสชาติของลูกอมนั้นสามารถหายไปได้ แต่เนื่องจากโรงงานของเราใช้งานเครื่องจักรผลิตลูกอมที่สั่งมาจากต่างประเทศ (ใช้งาน Third-party Library) เราจึงไม่สามารถแก้ไขลูกอม (Class) นั้นได้โดยตรง

แต่หากเขียนขึ้นในภาษา Dart เราสามารถ Extension ออกมาได้ โดยที่ไม่ต้องทำให้ลูกอมนั้นเป็นประเภทพิเศษ​ (Extends ให้กลายเป็น Subclass) เราจึงเขียนโค้ดเพิ่มขึ้นมาดังนี้

```dart
extension on Candy {
  void removeFlavor(String flavor) {
    _flavors.remove(flavor);
  }
}
   ```

เท่านี้เราก็สามารถเรียกใช้งาน `candyInstance.removeFlavor("Mint");` ได้แล้ว อย่างไรก็ตาม **ข้อควรระวังหนึ่งก็คือ** เราไม่สามารถเพิ่ม Instance Variables ให้กับ Extension Methods ได้ตามที่ชื่อนั้นบอกใบ้เราไว้เลย
> หากเราต้องการเพิ่ม Instance Variables แล้วละก็ เราอาจพิจารณาใช้การ Extends ไปเป็น Subclass แทน ซึ่งเป็นวิธีที่มีความเหมาะสมมากกว่า

## ใช่งานกับ class พื้นฐานได้

เราสามารถใช้ extension กับพวก int, String, Object, List<> Map<> ได้ เช่น
```dart
void main() {
  print(2.pow2);

  var myList = [1, 2, 3];
  print(sum(myList));
  print(myList.sum);
}
```
> สามารถใช้ extension กับ class พื้นฐานได้
```dart
extension on int {
  int get pow2 => this * this;
}
```
> ปกติถ้าเราจะ sum เราอาจจะสร้างฟังก์ชันขึ้นมาก็ได้ ดังนี้
```dart
int sum(List<int> list) {
  return list.fold(0, (a, b) => a + b);
}
```
> แต่เราสามารถทำแบบนี้ก็ได้ด้วย
```dart
extension on List<int> {
  int get sum => fold(0, (a, b) => a + b);
}
   ```
Output

```dart
4
6
6
   ```

## API conflict

API conflict ในที้นี้สำหรับ Extension คือ เมื่อมีการนิยาม extension method ที่ชื่อซ้ำกันในไลบรารีหรือโมดูลที่ถูกนำเข้ามากำหนดใช้งานพร้อมกัน โดย Dart ไม่รู้ว่าจะใช้ extension method ตัวไหนเมื่อเกิดความขัดแย้ง ตัวอย่างดังนี้
> อย่างแรกกำหนด string_lib1.dart นิยาม extension StringExtension ที่มี method capitalize() สำหรับคลาส String เพื่อทำให้ตัวอักษรแรกเป็นตัวพิมพ์ใหญ่และตัวอักษรที่เหลือเป็นตัวพิมพ์เล็ก

```dart
extension StringExtension on String {
  String capitalize() =>
      "${this[0].toUpperCase()}${this.substring(1).toLowerCase()}";
}
   ```
> อย่างที่สองกำหนด string_lib2.dart นิยาม extensions StringCase และ StringPadding ที่มี method capitalize() และ zeros() ตามลำดับ
```dart
extension StringCase on String {
  String capitalize() =>
      "${this[0].toUpperCase()}${this.substring(1).toLowerCase()}";
}

extension StringPadding on String {
  String zeros(int width) => this.padLeft(width, '0');
}
   ```
> นำเข้าใช้งาน string_lib1.dart และ string_lib2.dart และใช้งาน extension methods จากทั้งสองไลบรารี
```dart
import 'string_lib1.dart';
import 'string_lib2.dart';

void main() {
  print('hello'.capitalize());
  print('123'.zeros(6));
}
   ```
> จะปรากฎ error ออกมาดังนี้
```dart
A member named 'capitalize' is defined in extension 'StringExtension' and extension 'StringCase', and none are more specific.
   ```
นั่นคือการที่ dart ไม่รู้ว่าควรจะใช้ Extension อันไหนเพราะไม่มีอันใดอันหนึ่งสำคัญไปมากกว่าหรือน้อยกว่ากัน

## การแก้ปัญหามี 2 วิธี

- ใช้ show หรือ hide เพื่อจำกัด API ที่เผยแพร่
- ใช้ extensions โดยใช้ชื่อเต็ม

**1. show หรือ hide**

  เมื่อนำเข้า extension ที่มีข้อขัดแย้ง ใช้ `hide` เพื่อซ่อน extension ที่ไม่ต้องการใช้งาน
  
```dart
import 'string_lib1.dart';
import 'string_lib2.dart' hide StringCase;
   ```

  เช่นเดียวกับกับ `show` นั่นคือใช้ `show` เพื่อแสดงเฉพาะ extension ที่เราต้องการออกมา
  
```dart
import 'string_lib1.dart';
import 'string_lib2.dart' show StringPadding;
   ```
**2. Extension โดยใช้ชื่อเต็ม**

  คือการนำเข้าทั้งสองไลบรารีและใช้งาน extensions โดยใช้ชื่อเต็มของ extensions เพื่อชี้แจงชื่อ extension ที่ต้องการใช้

  ```dart
import 'string_lib1.dart';
import 'string_lib2.dart';

void main() {
  print(StringExtension('hello').capitalize());
  print('123'.zeros(6));
}
   ```

## แนวคิดของ Extension ของ Dart เมื่อเทียบกับภาษาอื่น

ในการใช้งาน Extensions ในภาษา Dart จะมีความแตกต่างจากภาษา Java, C, และ Python เนื่องจาก Dart เป็นภาษาที่ออกแบบมาเพื่อรองรับแนวคิดของ Extensions อย่างเต็มที่ ดังนั้นการใช้งาน Extensions ใน Dart จะมีความสะดวกและหลากหลายมากกว่า

**Java และ C**
  - ในส่วนของ Java และ C นั้นไม่มีแนวคิดที่เป็น Extension แบบเดียวกันกับ Dart
  - การเพิ่ม method หรือฟังก์ชันให้กับ class ที่มีอยู่ในภาษาเหล่านี้มักจะใช้วิธีการอื่น ๆ เช่นการสร้างคลาสย่อย (subclass) หรือการสืบทอด (inheritance) แล้วเพิ่มเมท็อดในคลาสย่อยแทน
    
  > ตัวอย่าง Java ที่ใช้ inherit เพื่อเพิ่มเมท็อดหรือฟังก์ชันให้กับคลาสที่มีอยู่

```java
// นิยามคลาสที่สืบทอดเพื่อเพิ่มเมท็อดให้กับคลาส String ในไฟล์ StringUtils.java
public class StringUtils {
  public static String capitalize(String str) {
    return str.substring(0, 1).toUpperCase() + str.substring(1).toLowerCase();
  }
}

// นำคลาสมาใช้งานในไฟล์ Main.java
public class Main {
  public static void main(String[] args) {
    String myString = "hello";
    System.out.println(StringUtils.capitalize(myString));  // แสดงผล "Hello"
  }
}
```

  > ตัวอย่าง C ที่ใช้การประกาศฟังก์ชันเสริมเป็นฟังก์ชันแยกที่สามารถเรียกใช้เมื่อต้องการ เนื่องจาก C ไม่มี inherit เหมือนกับ Java

```C
// นิยามฟังก์ชัน capitalize สำหรับสตริงในไฟล์ string_utils.h
#ifndef STRING_UTILS_H
#define STRING_UTILS_H

void capitalize(char *str);

#endif

// นิยามฟังก์ชัน capitalize ในไฟล์ string_utils.c
#include <string_utils.h>
#include <ctype.h>
#include <string.h>

void capitalize(char *str) {
    str[0] = toupper(str[0]);
    for (int i = 1; i < strlen(str); i++) {
        str[i] = tolower(str[i]);
    }
}

// นำฟังก์ชันมาใช้งานในไฟล์ main.c
#include <string_utils.h>

int main() {
    char myString[] = "hello";
    capitalize(myString);
    printf("%s\n", myString);  // แสดงผล "Hello"
    return 0;
}
``` 

    
**Python**
  - ใน Python มีคอนเซปต์ของ Extensions ที่คล้ายกับ Dart ที่ช่วยให้คุณเพิ่มเมท็อดหรือฟังก์ชันให้กับคลาสที่มีอยู่แล้วได้ โดยใช้ Decorator และการใช้ `@staticmethod` หรือ `@classmethod`
    
  > ตัวอย่าง python
  
```python
# นิยาม extension สำหรับ String ในไฟล์ string_extensions.py
class StringExtension:
    def __init__(self, string):
        self.string = string

    def capitalize(self):
        return self.string[0].upper() + self.string[1:].lower()

# นำ extension มาใช้งานในไฟล์ main.py
from string_extensions import StringExtension

my_string = "hello"
extension = StringExtension(my_string)
print(extension.capitalize())  # แสดงผล "Hello"
```
สรุปได้ว่าการใช้งาน Extensions แต่ละภาษาจะมีความแตกต่างกันอย่างมาก โดย Dart และ Python มีคอนเซปต์ของ Extensions ที่ช่วยให้งานด้านนี้ง่ายขึ้น ในขณะที่ Java และ C จะใช้วิธีการสืบทอดหรือประกาศฟังก์ชันแยกเพิ่มเติมเพื่อให้ความสามารถเหล่านี้กับคลาสที่มีอยู่แล้ว

## อ้างอิง
[Dart Extension Methods](https://www.darttutorial.org/dart-tutorial/dart-extension-methods/)<br>
[Dart Extension | Inception Hideout](https://blog.intception.me/dev/flutter/dart-extension.html#%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99)<br>
[Dart: Extension Methods](https://www.petepittawat.dev/posts/dart-extension-methods)<br>
[Extension Methods | Dart](https://dart.dev/language/extension-methods)

## Presentation

- [Extension in Dart.mp4](https://youtu.be/FEfZlpPtuPo?si=cDvAbPuD1Vavfx10)<br>

## Slide

- [Extension in Dart.pdf](https://drive.google.com/file/d/1OIJG0ARjdH6jcnzdbtJdqY80-d-YSalT/view?usp=sharing)

  
  
 
