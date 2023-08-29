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

นอกเหนือจาก method เรายังสามารถเพิ่มสมาชิกอื่น ๆ เช่น getter, setter, และ operator ได้

## Example 1
สมมติว่าเรามี Class ที่เราใช้งานจาก Third-party Library ใช้ในการสร้าง ลูกอม (Candy) ขึ้นมา สำหรับโรงงานของเรา ดังนี้

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

เท่านี้เราก็สามารถเรียกใช้งาน candyInstance.removeFlavor("Mint"); ได้แล้ว อย่างไรก็ตาม **ข้อควรระวังหนึ่งก็คือ** เราไม่สามารถเพิ่ม Instance Variables ให้กับ Extension Methods ได้ตามที่ชื่อนั้นบอกใบ้เราไว้เลย
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
import 'string_lib2.dart' hide StringCase;

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
- ใช้ extensions โดยชื่อเต็ม

  **1. ใช้ show หรือ hide เพื่อจำกัด API ที่เผยแพร่**
  
 
