# Stream in Dart (Ex.Async)😧
## ภาษา Dart
### Example Of async
```dart
Future<int> doSomeLongTask() async {
  await Future.delayed(const Duration(seconds: 2));
  return 21;
}main() async {
  int result = await doSomeLongTask();
  print(result); // prints '21' after waiting 2 second
}
   ```

<details>
<summary><strong>Output</strong></summary>
<pre><code>21
</code></pre>
</details>

### Example Of async*

```dart
Stream<int> countForOneMinute() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
} main() async {
  await for (int i in countForOneMinute()) {
    print(i); // prints 1 to 5, one integer per second
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre><code>1
2
3
4
5
</code></pre>
</details>

### Example Of yield*
```dart
Stream<int> str(int n) async* {
 if (n > 0) {  
   await Future.delayed(Duration(seconds: 2));
   yield n;
   yield* str(n - 2);
 }
}

void main() {
 str(10).forEach(print);
}
```
>จากตัวอย่าง มีการใช้ yield* เพื่อพิมพ์ค่าของฟังก์ชัน recursive นั่นก็คือ str() เรียกใช้ตัวเองซ้ำๆ
<details>
<summary><strong>Output</strong></summary>
<pre><code>10
8
6
4
2
</code></pre>
</details>


## Some More Example OF Stream

### Example 1

```dart
import 'dart:async';

void main() {
  var controller = StreamController();
  controller.stream.listen((event) {
    print(event);
  });
  controller.add('Hello');
  controller.add(42);
  controller.addError('Error!');
  controller.close();
}
```
>จากตัวอย่าง String integer และ error จะถูกเพิ่มลงใน StreamController() โดยใช้ listen() ในการรับค่าและพิมพ์ค่า
<details>
<summary><strong>Output</strong></summary>
<pre><code>Hello
42
Uncaught Error: Error!
</code></pre>
</details>


### Example 2

```dart
Stream<int> numberOfStream(int number) async* {
  for (int i = 0; i <= number; i++) {
    yield i;
  }
}

void main(List<String> arguments) {
  // Calling the Stream 
  var stream = numberOfStream(6);
  // Listening to Stream yielding each number
  stream.listen((s) => print(s));
}
```
>จากตัวอย่าง จะเห็นได้ว่า async* สามารถพิมพ์ค่าได้หลายๆค่า นั่นก็คือ 0-6

<details>
<summary><strong>Output</strong></summary>
<pre><code>0
1
2
3
4
5
6
</code></pre>
</details>



### Example 3

```dart
Stream<int> str(int n) async* {
 for (var i = 1; i <= n; i++) {
   await Future.delayed(Duration(seconds: 1));
   yield i;
 }
}

void main() {
 str(10).forEach(print);
}
```
>จากตัวอย่าง จะเห็นได้ว่ามีการพิมพ์ค่า 1-10 โดยแต่ละค่าจะพิมพ์ค่าหลังจากผ่านไป 1 วินาที

<details>
<summary><strong>Output</strong></summary>
<pre><code>1
2
3
4
5
6
7
8
9
10
</code></pre>
</details>

## async vs async*
|async                             |async*                                             |
|----------------------------------|---------------------------------------------------|
|ใช้กับ  Future                      |ใช้กับ  Stream                                       |
|async พิมพ์ค่าที่เป็น Future values ได้ค่าเดียว|async* พิมพ์ค่าที่เป็น Future values หลายๆครั้งได้   |
|ส่งผลลัพธ์กลับมาในรูปแบบของ Future    |ส่งผลลัพธ์กลับมาในรูปแบบของ Stream                     |

## yield vs yield*
|yield                                               |yield*                           |
|----------------------------------------------------|---------------------------------|
|ใช้สำหรับคืนค่าผลลัพธ์แบบค่าเดียว แต่ไม่หยุดการทำงานของฟังก์ชัน |ใช้สำหรับคืนค่าผลลัพธ์ฟังก์ชัน recursive |




## Asynchronous Programming ในภาษาอื่นๆ
## ภาษา C

ภาษา C แท้จริงไม่มีระบบ Asynchronous แบบ Native อย่างที่มีในภาษาอื่น ๆ เช่น Dart หรือ Java โดยตรง ดังนั้นการจัดการกับ Asynchronous ใน C จะต้องใช้เทคนิคและเครื่องมือที่อยู่นอกเหนือจากภาษามาช่วย โดยทั่วไปแล้วจะใช้การทำงานแบบ Thread และการจัดการกับเวลาเพื่อจำลองการทำงานแบบ Asynchronous

## ภาษา Java
ภาษา Java สามารถเขียน asynchronous programming ได้หลายวิธีและไม่ได้มีคำว่า async เป็นคำสงวนเหมือน ภาาษา Dart ที่มีการรองรับการเขียน asynchronous programming โดยตรงด้วยคีย์เวิร์ด "async" และ "await" 
### Example Of async

```dart
class ThreadClass extends Thread{
    public void run(){
    System.out.println("Thread is running");
    }
}
class AsyncExample {
    public static void main(String[] args) {
        ThreadClass thread1 = new ThreadClass();
        thread1.start(); 
    }
}
```
>จากตัวอย่างมีการสร้าง Tread เพื่อที่จะสามารถทำงานหลายๆอย่างได้พร้อมกัน

<details>
<summary><strong>Output</strong></summary>
<pre><code>Thread is running
</code></pre>
</details>

## ภาษา Python
ภาษา Python จะมีโมดูล asyncio ซึ่งเป็นตัวช่วยสำหรับการเขียน asynchronous programming และมีมาตั้งแต่เวอร์ชั่น 3.4
### Example Of async
 
```dart

import asyncio
async def do_task(task_name):
    print(f"Start {task_name}")
    await asyncio.sleep(2)  # Simulate some asynchronous task
    print(f"End {task_name}")
async def main():
    task1 = do_task("Task 1")
    task2 = do_task("Task 2")
    await asyncio.gather(task1, task2)
asyncio.run(main())
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>Start Task 1
End Task 1
</code></pre>
</details>

## อ้างอิง
:https://www.tamemo.com/post/178/async-in-dart-1-isolates-event-loop/<br>
:https://www.tamemo.com/post/179/async-in-dart-2-future/<br>
:https://www.tamemo.com/post/180/async-in-dart-3-stream/<br>
:https://dev.java/learn/api/streams/<br>
:https://docs.python.org/3/library/asyncio-stream.html#streamwriter<br>
:https://dart-tutorial.com/asynchronous-programming/stream-in-dart/
___
# Slides and Clip
Slides : https://github.com/soonklang/dart-tutorial/files/12884394/StreaminDart.Ex.Async.pdf<br>
Clip : https://youtu.be/kMgyhTy7xOM](https://www.youtube.com/watch?v=dO88yiwcJcU)https://www.youtube.com/watch?v=dO88yiwcJcU
