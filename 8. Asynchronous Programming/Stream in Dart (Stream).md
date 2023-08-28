<h1>Stream</h1>
Stream ใน Dart คือกลไกหนึ่งที่ใช้ในการจัดการและการทำงานกับข้อมูลที่เปลี่ยนแปลงได้ตลอดเวลาอย่างมีประสิทธิภาพ มันเปรียบเสมือนเป็นท่อที่ข้อมูลสามารถไหลผ่านไปมาได้เรื่อยๆ และคุณสามารถติดตามสถานะและจัดการกับข้อมูลเหล่านั้นได้เมื่อมีการเปลี่ยนแปลงเกิดขึ้น

ใน Dart, Stream คืออะไรก็ตามที่สามารถส่งข้อมูลได้ในรูปแบบไม่จำเป็นต้องรอให้ข้อมูลทั้งหมดเตรียมพร้อมก่อน มันเหมาะสำหรับกรณีที่คุณต้องการจัดการกับข้อมูลอย่างแบบเรียลไทม์ เช่น การอัปเดตสถานะของแอปพลิเคชันเมื่อข้อมูลมีการเปลี่ยนแปลง การดึงข้อมูลจากแหล่งต่างๆ อย่างเช่น APIs, การทำงานกับไฟล์ข้อมูล หรือการเอาข้อมูลจากอุปกรณ์ต่างๆ เป็นต้น

การสร้าง Stream ใน Dart นั้นสามารถทำได้โดยใช้คลาส Stream หรือ StreamController ซึ่งเป็นคลาสที่ใช้ในการสร้าง Stream และสั่งให้ข้อมูลไหลผ่าน Stream ตามที่คุณต้องการ คุณสามารถเพิ่มข้อมูลลงใน Stream ด้วยเมธอด .add() และสามารถจัดการกับการปิด Stream ด้วยเมธอด .close() เมื่อไม่ต้องการใช้งาน Stream ต่อไป
```dart
import 'dart:async';

class Number {
  Number() {
    Timer.periodic(
      Duration(seconds: 1),
      (timer) {
        _controller.sink.add(_count);
        _count++;
      },
    );
  }

  //  create a StreamController
  final _controller = StreamController<int>();
  var _count = 1;

  // property that returns the stream object
  Stream<int> get stream => _controller.stream;
}


void main() {
  var stream = Number().stream.asBroadcastStream();

  stream.listen(
    (event) => print('listener 1: $event'),
  );

  // cause exception
  stream.listen(
    (event) => print('listener 2: $event'),
  );
}


   ```
