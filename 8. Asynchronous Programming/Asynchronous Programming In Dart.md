
# Asynchronous Programming In Dart

การทำงานในรูปแบบ Asynchronous ช่วยให้โปรแกรมของเราสามารถทำงานต่อเนื่องอย่างสมบูรณ์ได้ ในขณะที่ยังมีการดำเนินการอื่นอยู่ ยกตัวอย่างเช่น การเรียกดูข้อมูลผ่านเครือข่ายเน็ตเวิร์ค การบันทึกข้อมูลลงฐานข้อมูล การอ่านข้อมูลจากไฟล์ เป็นต้น

## Synchronous Programming

ในการเขียนโปรแกรมแบบ Synchronous คือโปรแกรมที่รอคอยให้คำสั่งหนึ่งทำงานจนเสร็จสิ้นก่อนจึงจะดำเนินการต่อไป ข้อเสียในการใช้วิธีการนี้คือหากส่วนหนึ่งของโค้ดใช้เวลานานในการประมวลผล บล็อกถัดๆ มาที่ไม่เกี่ยวข้องกันจะถูกบล็อกจากการดำเนินการ 

**ตัวอย่างของการโปรแกรมแบบ Synchronous*

```dart
void main() {
  print("First Operation"); 
  print("Second Big Operation"); 
  print("Third Operation"); 
  print("Last Operation"); 
}
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>
First Operation
Second Big Operation
Third Operation
Last Operation
</code></pre>
</details>

ในตัวอย่างนี้สามารถเห็นได้ว่าโปรแกรมจะพิมพ์ออกมาทีละบรรทัด ถ้าสมมติว่า Second Big Operation ต้องใช้เวลา 3 วินาที Third Operation และ Last Operation ก็จะต้องรอเป็นเวลา 3 วินาทีถึงจะทำงานได้ โดยปัญหานี้เราสามารถนำการเขียนโปรแกรมแบบ Asynchronous มาแก้ไขได้

## Asynchronous Programming

ในการโปรแกรมแบบไม่ซิงโครนัส การดำเนินการของโปรแกรมจะดำเนินต่อไปยังบรรทัดถัดไปโดยไม่ต้องรอให้งานอื่นเสร็จสิ้นก่อน

>ℹ️ **Note:** การโปรแกรมแบบ Asynchronous ช่วยเพิ่มความเร็วในการตอบสนองของโปรแกรม

**ตัวอย่างของการโปรแกรมแบบไม่ซิงโครนัส**
```dart
void main() {
  print("First Operation");   
  Future.delayed(Duration(seconds:3),()=>print('Second Big Operation'));
  print("Third Operation"); 
  print("Last Operation"); 
}

```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
First Operation
Third Operation
Last Operation
Second Big Operation
</code></pre>
</details>

ในตัวอย่างนี้สามารถเห็นได้ว่าจะพิมพ์ Second Big Operation เป็นอย่างสุดท้าย เนื่องจากต้องใช้เวลา 3 วินาทีในการทำงานแต่ Third Operation กับ 
Last Operation นั้นไม่จำเป็นต้องรอ 3 วินาที



**Note**:  `Future` หมายถึงค่าที่จะได้มาหรือสิ่งที่จะเกิดขึ้นในอนาคตข้างหน้า ซึ่งในส่วนนี้จะได้เรียนในเนื้อหาส่วนต่อไป

### การเขียน Asynchronous Programming ในภาษาอื่นๆ

### C
```c
#include <stdio.h>
#include <unistd.h>

void delayedPrint() {
    sleep(3);
    printf("Second Big Operation\n");
}

int main() {
    printf("First Operation\n");
    delayedPrint();
    printf("Third Operation\n");
    printf("Last Operation\n");
    return 0;
}
```
>ในที่นี้โปรดทราบว่าฟังก์ชัน sleep() จากไลบรารี unistd.h ใช้เพื่อเพียงแค่เลียนแบบการใช้ Future.delayed() ในโปรแกรม Dart เท่านั้น นอกจากนี้ C ไม่มีการรองรับการเขียนโปรแกรมแบบ Asynchronous และ Futures ในตัวแบบเดียวกับที่ Dart มี ดังนั้นโค้ดนี้จึงถูกเขียนในลักษณะ Synchronous 

### Java
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("First Operation");
        
        Thread thread = new Thread(() -> {
            try {
                Thread.sleep(3000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("Second Big Operation");
        });
        
        thread.start();
        
        System.out.println("Third Operation");
        System.out.println("Last Operation");
    }
}
```

### Python
```python
import threading
import time

def delayed_print():
    time.sleep(3)
    print("Second Big Operation")

print("First Operation")

thread = threading.Thread(target=delayed_print)
thread.start()

print("Third Operation")
print("Last Operation")

```

## ทำไมเราต้องใช้การเขียนโปรแกรมแบบ Asynchronous
การดำเนินการแบบ Asynchronous ช่วยให้โปรแกรมของคุณสามารถทำงานเสร็จสิ้นขณะที่รอการดำเนินการอื่นๆอยู่ ต่อไปนี้คือบางการดำเนินการแบบไม่ซิงโครนัสที่พบบ่อย

-   รับข้อมูลจากอินเทอร์เน็ต
-   เขียนข้อมูลลงในฐานข้อมูล
-   ดำเนินการที่ใช้เวลานาน
-   อ่านข้อมูลจากไฟล์
-   ดาวน์โหลดไฟล์ ฯลฯ

การดำเนินการแบบ Asynchronous มักใช้เวลานาน ดังนั้นจึงมักจะให้ผลลัพธ์ในรูปแบบของ `Future` หากผลลัพธ์มีส่วนหลายๆ ส่วน จะให้ผลลัพธ์ในรูปแบบของ `Stream` ซึ่งเราจะได้เรียนรู้เพิ่มเติมเกี่ยวกับ `Future` และ `Stream` ในเนื้อหาส่วนถัดไป

  
## คำศัพท์สำคัญ
-   **Synchronous Operation**: การดำเนินการแบบซิงโครนัสบล็อกการดำเนินการอื่นจนกว่าจะเสร็จสิ้น
-   **Synchronous Function**: ฟังก์ชันแบบซิงโครนัสทำเฉพาะการดำเนินการแบบซิงโครนัส
-   **Asynchronous Operation**:การดำเนินการแบบไม่ซิงโครนัสอนุญาตให้การดำเนินการอื่นเริ่มทำงานก่อนที่จะเสร็จสิ้น
-   **Asynchronous Function**: ฟังก์ชันแบบไม่ซิงโครนัสดำเนินการอย่างน้อยหนึ่งการดำเนินการแบบไม่ซิงโครนัสและยังสามารถดำเนินการแบบซิงโครนัสได้ด้วย

## **Reference**
[Asynchronous programming: futures, async, await | Dart](https://dart.dev/codelabs/async-await)
[Dart Programming - Async | Tutorialspoint](https://www.tutorialspoint.com/dart_programming/dart_programming_async.htm)
[Asynchronous Programming :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://dart-tutorial.com/asynchronous-programming/asynchronous-programming-in-dart/)
[การใช้งาน Asynchronous Programming ในภาษา Dart เบื้องต้น เนื คอร์สเรียน เรียนฟรี ออนไลน์ บทความ (ninenik.com)](https://www.ninenik.com/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99_Asynchronous_Programming_%E0%B9%83%E0%B8%99%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2_Dart_%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99-949.html)
