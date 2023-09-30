# Asycn and Await In Dart
Async และ Await เป็น feature ใน Dart ที่ช่วยให้เราสามารถเขียนโค้ดแบบ asynchronous ที่มีลักษณะและการทำงานเหมือนโค้ดแบบ synchronous ทำให้อ่านง่ายขึ้น

เมื่อ function ทำเครื่องหมาย async หมายความว่ามันจะทำงานบางอย่างและทำการส่งวัตถุของ Future มาให้พร้อมกับผลลัพธ์ของงานนั้น

ในทางกลับกัน await จะชะลอการทำงานของ function async จนกว่า Future ที่รอคอยจะทำงานเสร็จสิ้น ซึ่งสามารถทำให้เราสร้างโค้ดที่ดูเหมือนแบบ synchronous แต่จริง ๆ เป็นโค้ดแบบ asynchronous ได้

เราสามารถใช้คีย์เวิร์ด async ก่อนส่วนของ function เพื่อทำให้เป็น function แบบ asynchronous และเราสามารถใช้
คีย์เวิร์ด await เพื่อให้ได้ผลลัพธ์ที่สมบูรณ์ของการแสดงผลแบบ asynchronous

## แนวคิดที่สำคัญ
* ในการกำหนด async ฟังก์ชั่น ให้เราเพิ่ม "async" ไว้ก่อนส่วนของ body ของ ฟังก์ชั่น
* ให้การเรียกใช้งาน async ฟังก์ชั่น เราต้องกำหนด "await" ไว้ด้านหน้าของ async ฟังก์ชั่นที่เรียกใช้งานเสมอ

### ตัวอย่าง: Synchronous function
```
void main() {
 print("Start");
 getData();
 print("End");
}

void getData() {
 String data = middleFunction();
 print(data);
}

Future<String> middleFunction(){
 return Future.delayed(Duration(seconds:5), ()=> "Hello");
}
```
<details>
 <summary><strong>Output</strong></summary>
 <pre><code>Start
End
Instance of '_Future<String>'
</code></pre>
</details>

### ตัวอย่าง: Asynchronous function
```
void main() {
 print("Start");
 getData();
 print("End");
}

void getData() async{
 String data = await middleFunction();
 print(data);
}

Future<String> middleFunction(){
 return Future.delayed(Duration(seconds:5), ()=> "Hello");
}
```
<details>
 <summary><strong>Output</strong></summary>
 <pre><code>Start
End
Hello
</code></pre>
</details>

ในตัวอย่างข้างต้น async จะจัดการสถานะของโปรแกรมที่สามารถดำเนินการส่วนใดส่วนหนึ่งของโปรแกรมได้ async จะมาพร้อมกับ await เสมอ เนื่องจาก await จะถือเป็นส่วนของโปรแกรมจนกว่าส่วนที่เหลือของโปรแกรมจะถูกดำเนินการ

 เพื่อให้เห็นลำดับ และทิศทางการทำงานชัดเจน ดูรูปแบบตัวอย่างด้านล่างนี้ประกอบ
 
### ตัวอย่าง: Asynchronous
```
void main () async {
  print("Run 1");
  print(await createOrderMessage());
  print("Run 2");
  print(run3());
  print("Run 4");
  print(await run5());
  print("Run 6");
}

String run3(){
  return "Run 3";
}

Future<String> run5() async {
  return Future.delayed(Duration(seconds: 4), () => 'Run 5'); 
}
Future<String> createOrderMessage() async {
  var order = await getUserOrder();   
  return 'Your order is: $order'; 
}
Future<String> getUserOrder() {
  return Future.delayed(Duration(seconds: 4), () => 'Large Latte'); 
}
```
<details>
 <summary><strong>Output</strong></summary>
 <pre><code> Your order is: Large Latte
    Run 2
    Run 3
    Run 4
    Run 5
    Run 6
</code></pre>
</details>
 จะเห็นว่า flow หรือลำดับการทำงาน จะมีลักษณะที่แตกต่างจากกรณีที่เป็น การใช้งานแบบ synchronous 
 
 <br>
 เราลองมาดูหากกำหนดการใช้งานในรูปแบบ synchronous  เป็นดังนี้
 
 ### ตัวอย่าง: Synchronous
 ```
void main () {
  print("Run 1");
  print(createOrderMessage());
  print("Run 2");
  print(run3());
  print("Run 4");
  print(run5());
  print("Run 6");
}

String run3(){
  return "Run 3";
}

Future<void> run5() {
  return Future.delayed(Duration(seconds: 4), () => print('Run 5')); 
}
String createOrderMessage()  {
  var order = getUserOrder();   
  return 'Your order is: $order'; 
}
Future<void> getUserOrder() {
  return Future.delayed(Duration(seconds: 4), () => print('Large Latte')); 
}
```
<details>
 <summary><strong>Output</strong></summary>
 <pre><code> Run 1
    Your order is: Instance of '_Future<void>'
    Run 2
    Run 3
    Run 4
    Instance of '_Future<void>'
    Run 6
    Large Latte
    Run 5
</code></pre>
</details>

คำสั่งทั้งหมดจะทำงานต่อเนื่องกันตามลำดับทันที แต่ค่าจากคำสั่ง createOrderMessage() และ run5() ที่เป็นการทำงานในรูปแบบ asynchronous ที่มีเรื่องของเวลาที่ต้องรอเข้ามาเกี่ยวข้อง ทำให้แสดงค่า ที่เป็นค่ายังไม่เสร็จสมบูรณ์ก่อน หรือก็คือ Uncompleted และเมื่อครบ 4 วินาที ต่อมา ก็จะแสดงผลลัพธ์สุดท้ายของ คำสั่ง createOrderMessage() และ run5() 

## การจัดการข้อผิดพลาด
เราสามารถจัดการข้อผิดพลาดในฟังก์ชัน async ได้โดยใช้ try-catch โดยสามารถเขียนโค้ด try-catch ได้ด้วยวิธีการเดียวกันกับที่เขียนโค้ด synchronous

### ตัวอย่าง
```
main() {
  print("Start");
  getData();
  print("End");
}


void getData() async{
    try{
        String data = await middleFunction();
        print(data);
    }catch(err){
        print("Some error $err");
    }
 
}

Future<String> middleFunction(){
  return Future.delayed(Duration(seconds:5), ()=> "Hello");
}
```

<details>
 <summary><strong>Output</strong></summary>
 <pre><code>Start
End
Hello
</code></pre>
</details>

ในตัวอย่างข้างต้น try-catch จะจัดการกับข้อยกเว้นที่อาจเกิดขึ้นหลังจากโปรแกรมถูกเรียกใช้งาน
```
ℹ️ Note: เราไม่สามารถดำเนินการแบบ asynchronous จากฟังก์ชัน ซิงโครนัสได้
```
## ทำความเข้าใจเพิ่มเติม
- เราใช้ "async" keyword เพื่อระบุว่าฟังก์ชั่นนั้นๆ เป็น asynchronous
- asynchronous ฟังก์ชั่น เป็นฟังก์ชั่นที่มีการใช้งาน "async" keyword กำกับไว้
- เราใช้ "await" keyword เพื่อรับค่าผลลัพธ์สุดท้ายจากการเรียกใช้งาน asynchronous ฟังก์ชั่น โดยจะสามารถกำหนดได้เฉพาะภายใน asynchronous ฟังก์ชั่น เท่านั้น

## คำศัพท์สำคัญ
- **async** : หมายความว่า function นี้เป็น asynchronous และจะไม่เกิดขึ้นทันที เราอาจต้องรอสักครู่เพื่อให้ได้รับ result
- **async function** : function ที่มี keyword async เรียกว่า async function
- **await** : หมายความว่า ให้รอ รอจนกว่า fucntion นี้จะทำงานเสร็จและจะ return value กลับไป (จะใช้ได้กับ Function ที่เป็น Future เท่านั้น)

## Slide
- [AsyncAndAwait.pptx](https://github.com/Lathavit/PL/blob/main/AsyncAndAwait.pptx?raw=true)

## Video
- [Async and Await In Dart](https://youtu.be/ZwQyOYOw8zE)

## **Reference**
[Async and Await In Dart :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://dart-tutorial.com/asynchronous-programming/async-and-await-in-dart/)
<br>
[Dart lang: Ep.4 (async, await, then and Future) | by Grassroot Engineer | Medium](https://grassrootengineer.medium.com/dart-lang-ep-4-async-await-then-and-future-16e34a31fab9)
<br>
[การใช้งาน Asynchronous Programming ในภาษา Dart เบื้องต้น เนื คอร์สเรียน เรียนฟรี ออนไลน์ บทความ (ninenik.com)](https://www.ninenik.com/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99_Asynchronous_Programming_%E0%B9%83%E0%B8%99%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2_Dart_%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99-949.html)
