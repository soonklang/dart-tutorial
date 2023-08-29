

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

## เทียบกับ Stream ของภาษาอื่นที่
หลักจากที่ได้ทำความรู้จักกับ Stream ใน Dart แล้วเรามาดูบทบาทของ Stream ในภาษาอื่นกันบ้าง

### Stream ใน C  
- ในภาษา C ไม่มี Stream เตรียมไว้ให้แต่
 แต่จะมี libraries จำพวก I/O (Input Output)  ที่มี function `fopen`
,`fread`,`fwrite` ที่สามารถอ่านหรือเขียนข้อมูล จากไฟล์ได้
function พวกนี้สามารถทำหน้าที่คล้ายๆกับ Stream ได้แต่จะเป็น Stream ในเชิงของไฟล์ ไม่ใช่ Asynchronous programming แบบใน Dart
แต่เราก็สามารถประยุกต์ใช้ในรูปแบบ Async ได้เหมือนกัน

### Stream ใน Java
- ในภาษา Java มี Stream และสามารถใช้ทำเป็น Asynchronous programming ได้
แต่จริงๆแล้ว Stream ใน Java จะมุ่งเน้นไปที่การจัดการกับข้อมูลด้วยการใช้ function ซะมากกว่า เช่น
>การ filter (คัดกรองข้อมูลที่ต้องการจาก Stream)
```java 
List names = Arrays.asList("Reflection","Collection","Stream");  
List result = names.stream().filter(s->s.startsWith("S")).collect(Collectors.toList()); 
```
> หรือ sort (เรียงข้อมูลใน Stream)
```java
List names = Arrays.asList("Reflection","Collection","Stream");  
List result = names.stream().sorted().collect(Collectors.toList());
```


### Stream ใน Python
- Python มีแนวคิดของ Stream ในรูปแบบของ File เหมือน C
และก็ยังรองรับการเขียนแบบ Asynchronous คล้ายๆกับ Dart โดยมี library ที่ชื่อ `asyncio` 
โดยจะมี keywords ก็คือ `async` และ `await` เหมือนกัน


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
## วิธีการใช้ Stream ใน Dart
หลังจากที่เราสามารถสร้าง function ที่สามารถคืนค่าเป็น Stream ได้แล้ว
<br>
ต่อไปจะเข้าสู่ขั้นตอนการใช้งาน หรือ ดึงค่า จาก Stream นั่นเอง
<br>

  เราสามารถใช้คำสั่ง **`await for`**  เพื่อดึงค่าจาก Stream ได้
```dart
// function ที่คืนค่า Stream
Stream<String> getUserName() async* {
  await Future.delayed(Duration(seconds: 1));
  yield 'Mark';
  await Future.delayed(Duration(seconds: 1));
  yield 'John';
  await Future.delayed(Duration(seconds: 1));
  yield 'Smith';
}

// main function
void main() async {
  // สามารถใช้ await for เพื่อดึงค่าจาก Stream 
  await for (String name in getUserName()) {
    print(name);
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Mark
John
Smith</code></pre>
เมื่อแบ่งเป็นลำดับเวลาการทำงานจะได้ Output ดังนี้
  <pre><code>Time            │     │    │
0|             1sec.  │    │
1| Mark  ───────┘    2sec. │
2| John  ─────────────┘  3sec.
3| Smith ──────────────────┘
</code></pre>
</details>

## Future ปะทะ Stream
| Future | Stream |
|:--------| :-------------|
|Future represents the value or error that is supposed to be available in the Future.| Stream is a way by which we receive a sequence of events. |
| A Future can provide only a single result over time.| Stream can provide zero or more values.|
|You can use FutureBuilder to view and interact with data. |You can use StreamBuilder to view and interact with data. |
|It can’t listen to a variable change. |But Stream can listen to a variable change. |
|Syntax: Future <data_type> class_name | Syntax: Stream <data_type> class_name|

## ประเภทของ Stream

Stream มีทั้งหมด 2 ประเภทนั่นก็คือ
- Single Subscription streams
- Broadcast streams

# Single Subscription Stream

ตามปกติแล้ว Stream จะถูกตั้งค่าให้เป็นแบบ Single Subscription
Stream จะเก็บค่าเอาไว้จนกว่าจะมีสมาชิก(Subscriber)มา Subscription ซึ่ง Stream นั้น
จะมีผู้ฟังได้แค่คนเดียว
คุณจะได้รับ exception ถ้าพยายามจะมี Subscriber มากกว่า 1 ใน Stream เดียวกัน 
Subscriber จะได้รับค่าที่ครบถ้วนสมบูรณ์ และมีลำดับที่ถูกต้องจาก Stream 
ในส่วนของ Stream controller จะมีเพียง Stream เดียวและ 1 Subscriber
>ยกตัวอย่างเช่น คุณกำลังทำข้อสอบ มิดเทอม แล้วหันไปลอกข้อสอบเพื่อน
>คุณก็จะได้รับ exception จากอาจารย์คุมสอบมาเป็นกากบาทตัวโตๆ
>หมายความว่าเพื่อนที่คุณไปลอกกำลังใช้ Stream อยู่นั่นเอง 
# Broadcast Stream
นี่คือ Stream ที่ถูกตั้งค่าสำหรับการมีสมาชิกได้มากกว่า 1
Stream จะเก็บค่าเอาไว้จนกว่าจะมีสมาชิกมา Subscription ซึ่ง Stream นั้น
จะมีผู้ฟังเท่าไหร่ก็ได้
คุณสามารถใช้ Broadcast stream ถ้าอยากให้มีผู้ฟังที่เยอะกว่า 1
ในส่วนของ Stream controller จะมีได้หลาย Stream แล้วหลาย Subscriber
>ยกตัวอย่างเช่น คุณใช้ Netflix หรือ Youtube ซึ่งคุณสามารถเลือกดูคลิปแมวเต้นก็ได้ แต่คุณก็ไม่ได้ดูอยู่คนเดียวอาจจะมีคนที่ประเทศจีนกำลังดูอยู่เหมือนกันคุณ คุณยังสามารถไปดูคลิปอื่นได้ถ้าคุณเลิกรับข้อมูลจากคลิปแมวเต้นได้เหมือนกัน

### Syntax (Broadcast Stream)

```dart
StreamController<data_type> controller = StreamController<data_type>.broadcast();
```

## Stream controller
นอกจากที่คุณจะสร้างโดยใช้คลาส Stream แล้วเรายังสามารถสร้างในรูปแบบอื่นได้
ตัวอย่างนี้เราจะสร้าง Stream โดยใช้ `StreamController `
```dart
StreamController<data_type> controller = StreamController<data_type>;
```
เราสามารถเข้าถึงตัว controller ได้ด้วยการใช้ `stream` ดังนี้
```dart
Stream stream = controller.stream;
```
### วิธีการสมัครรับข้อมูล (Subscribe) จาก Stream
หลังจากที่เราสามารถเข้าถึง stream ได้เราสามารถใช้ method `listen()`
ในการรับข้อมูลจาก Stream ได้ดังนี้
```dart
stream.listen((value) {
	print("Value from controller: $value");
});
```
>listen() จะเหมือน then() ของ Future แต่รับได้เรื่อยๆเพราเป็น Stream นั่นเอง

### วิธีการเพิ่มของลงใน Stream
เราจะสามารถเพิ่มค่าด้วยการใช้ method `add()` ผ่าน controller นั่นเอง
จะสามารถเขียนได้ดังนี้
```dart 
controller.add(3);
```
เมื่อเราลองใช้คำสั่งข้างบนก็จะได้ผลลัพธ์ดังนี้
` Value from controller: 3`
### วิธีการจัดการ Stream
เราก็ใช้ method `listen()` เพื่อจัดการส่งให้ `streamSubsciption` ควบคุมการรับข้อมูลได้ 
```dart
StreamSubscription<int> streamSubscription = stream.listen((value){
  print("Value from controller: $value");
});
```
### วิธีการยกเลิก Stream
หลังจากที่มี `streamSubsciption` เราก็สามารถใช้ method
`cancel()` เพื่อยกเลิกการรับข้อมูลได้
```dart
streamSubscription.cancel();
```
## ประเภทของ Class ต่างๆใน Stream
มี 4 คลาสหลักของ Dart ที่อยู่ใน async libraries ที่ใช้ในการจัดการกับ Streams

**Stream** :  เป็นตัวแทนของกระแสของข้อมูล แบบ Asynchronous
เช่น
```dart
final controller = StreamController<String>();
final subscription = controller.stream.listen((String data) {
  print(data);
});
controller.sink.add("Data!");
```
**EventSink** :  คือการเพิ่มของใน Stream ไม่ว่าจะเป็นเหตุการณ์ ค่า หรือ Error 
**StreamController** :  ตัวที่จัดการกับ Stream ไม่ว่าจะสร้าง Stream เพิ่ม (sink) ใน Stream แล้วยัง method ที่ใช้กำกับ Stream 
**StreamSubscription** : เป็นตัวแทนที่บ่งบอกว่าเป็นสมาชิกของ Stream สามารถ pause เพื่อหยุดรับข้อมูล , resume รับข้อมูลต่อ หรือ cancel ยกเลิกการเป็นสมาชิกของ Stream

## Method ที่ใช้ใน Stream
มี method 4 ตัวที่ใช้กับ Stream ได้

`listen()` ใช้ในการรับค่าหรือเหตุการณ์ที่ถูกส่งมาจาก Stream

**Syntax**: listen
```dart
final subscription = myStream.listen()
```

  Stream สามารถเกิด error ขึ้นได้เช่นกันการเพิ่ม method `onError` เข้าไปจะช่วยให้สามารถดักจับความผิดพลาดได้
**Syntax**: onError
```dart
onError: (err){

}
```
method `cancelOnError` จะถูกใช้งานเป็นปกติถ้าไม่ได้ตั้งค่า ถ้าตั้งค่า method  นี้ให้เป็น false การสมัครสมาชิกก็จะดำเนินต่อไปแม้จะเกิด Error เกิดขึ้น
**Syntax**: cancelOnError
```dart 
cancelOnError :  false
```
method `onDone` จะทำงานเมื่อ Stream เสร็จสิ้นการส่งข้อมูลทั้งหมด เช่น ตอนที่ไฟล์ถูกอ่านจนครบถ้วนแล้ว
- **Syntax**: onDone
```dart
onDone: (){
  
}
```
### ยกตัวอย่างการใช้ Method ใน Stream
```dart
streamObject.listen((event) {
  //method นี้จะทำงานก็ต่อเมื่อ Stream ส่งค่าหรือเหตุการณ์กลับมา
  print('Received: $event');
}, onError: (error) {
  //method นี้จะทำงานก็ต่อเมื่อมี Error เกิดขึ้นใน Stream
  print('Error: $error');
}, onDone: () {
  //method นี้จะทำงานก็ต่อเมื่อ Stream เสร็จสิ้นการส่งข้อมูลทั้งหมดแล้ว
  print('Stream is done');
});
```



## Keywords ที่ใช้ใน Stream
- async* : ใช้ใน Stream เหมือน async ที่ใช้ใน Future
- yield : ใช้ในการส่งค่าออกมาจาก Generator ไม่ว่าจะเป็นแบบ sync หรือ async  
- yield* : ใช้ในการวนทำ function ของ Iterable หรือ Streamซ้ำ

[Streams In Dart :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://www.dart-tutorial.com/asynchronous-programming/stream-in-dart/)
<br>
[Streams (The GNU C Library)](https://www.gnu.org/software/libc/manual/html_node/Streams.html)
<br>
[Dart - Streams - GeeksforGeeks](https://www.geeksforgeeks.org/dart-streams/)
<br>
[Asynchronous programming: Streams | Dart (dart.dev)](https://dart.dev/tutorials/language/streams)
<br>
[StreamController class - dart:async library - Dart API](https://api.dart.dev/stable/3.1.0/dart-async/StreamController-class.html)
<br>
[java.util.stream (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html)
<br>
[Streams — Python 3.11.5 documentation](https://docs.python.org/3/library/asyncio-stream.html)
<br>
[DartLangSpecDraft.pdf](https://spec.dart.dev/DartLangSpecDraft.pdf)
