
# Stream (กระแสข้อมูล)
ยินดีต้อนรับทุกท่านเข้าสู่เนื้อหา **Stream** ของหัว Asynchronous Programming 
<br>
หลายๆท่านอาจจะยังไม่คุ้นชินกับคำว่า **Stream** สักเท่าไหร่
<br>
จึงจะขอยกตัวอย่างที่จะได้เห็นภาพง่าย ๆ ก่อนจะเข้าเนื้อหาหลักของเรา

## รู้จักกับ **Stream** 
Stream หรือถ้าแปลเป็นภาษาไทยจะได้ความว่า "กระแส" หรือ "สายน้ำ" <br>
เมื่อพูดถึงสายน้ำแล้ว ให้ทุกท่านนึกถึงภาพที่ได้ไปเที่ยวทะเลหาดทรายขาว <br>
ที่ทะเลนั้นจะสามารถมี **เหตุการณ์ (Events)** ต่างๆเกิดขึ้น เช่น
>เด็กที่กำลังตกปลา ผู้ดีที่กำลังอุจจาระ หรืออาจจะเป็น ปลาที่กำลังพลอดรักกันอย่างดุเดือด

เหตุการณ์ที่เกิดขึ้นอาจจะส่งค่ากลับมา เช่น 
>เด็กตกปลาได้ 2 ตัว ผู้ดีอุจจาระไป 4 ก้อน ปลาออกลูกมา 50 ตัว

เราจะมองว่า **ค่า** ที่ส่งกลับมาจาก **เหตุการณ์ (Events)** จะอยู่ใน **กระแสข้อมูล (Stream)** 
<br>
ซึ่งหมายความว่า Stream จะแตกต่างจาก Future ก่อนหน้านี้ที่ตอบกลับมาแค่ 1 ค่าเท่านั้นนั่นเอง
<br>
ดูตารางข้างล่าง
|รูปแบบ\การคืนค่า  |ค่าเดียว  |  ศูนย์หรือมากกว่า|
|--|--|--|
| Sync |int  |Iterator[^1] |
|Async|Future|Stream|

<br>
[^1] สิ่งที่สามารถวนซ้ำได้เช่น Array , List  , String
<br>
หมายความว่า Stream ก็คือ Iterator ที่อยู่ในรูปของ Asynchronous นั่นเอง

### ผู้ฟัง (Listeners)

การที่ Stream จะใช้งานได้อย่างเต็มที่ต้องพึ่ง ผู้ฟัง (Listeners)
<br>
ลองคิดดูว่ามีรายการรายงานข่าวที่ไม่มีคนฟังดูสิ !!! ฟังดูน่าหดหู่มากเลยนะ
<br>
Stream สามารถมีผู้ฟัง (Listeners) ได้ตั้งแต่ 1 คนขึ้นไป ซึ่งผู้ฟังทุกคนจะได้รับข้อมูลชุดเดียวกันทั้งหมด
<br>
หมายความว่าการมี ผู้ฟัง (Listeners) ก็คือการที่สามารถนำค่าที่ได้จาก Stream มาใช้งานต่อได้นั่นเอง !!
<br>


## วิธีสร้าง Stream ใน Dart
หลังจากที่รู้แนวคิดของ Stream คร่าวๆแล้วเราจะลอง สร้าง Stream ใน Dart ซึ่ง Stream เป็น class หนึ่งที่อยู่ใน Dart อยู่แล้ว 
<br>

ต่อไปนี้จะเป็น function ที่จะคืนค่าเป็น `Stream<String>` หลังจาก 3 วินาทีหลังจากเรียกใช้งาน

```dart
// function ที่คืนค่า Stream
Stream<String> getUserName() async* {
  await Future.delayed(Duration(seconds: 1)); //ถ่วงเวลา 1 วินาที
  yield 'Mark';                               //ส่งคืนค่า 'Mark' 
  await Future.delayed(Duration(seconds: 1)); //ถ่วงเวลา 1 วินาที
  yield 'John';                               //ส่งคืนค่า 'John' 
  await Future.delayed(Duration(seconds: 1)); //ถ่วงเวลา 1 วินาที
  yield 'Smith';                              //ส่งคืนค่า 'Smith' 
}
```
> yield คล้ายๆกับ return คือการคืนค่าข้อมูลกลับ
> <br>
> แต่ yield สามารถข้อมูลกลับได้หลายครั้งนั่นเอง

หรือเรายังสามารถสร้าง Stream ด้วยการใช้ method `Stream.fromIterable()`
<br>
ต่อไปนี้จะเป็น function ที่จะคืนค่าเป็น `Stream<String>` โดยทันทีหลังจากเรียกใช้งาน
<br>

```dart
// function ที่คืนค่า Stream
Stream<String> getUserName() {
  return Stream.fromIterable(['Mark', 'John', 'Smith']);  
}
```


[Streams In Dart :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://www.dart-tutorial.com/asynchronous-programming/stream-in-dart/)
<br>
[Dart - Streams - GeeksforGeeks](https://www.geeksforgeeks.org/dart-streams/)
<br>
[Asynchronous programming: Streams | Dart (dart.dev)](https://dart.dev/tutorials/language/streams)
