


# Future in Dart 🌠 

ใน dart Future แสดงถึง ค่าของตัวแปร(value) หรือ ข้อผิดพลาด(error) ที่ยังไม่สามารถถูกเรียกใช้ได้ในขณะหนึ่ง **แต่มันจะแสดงถึงค่าที่มีความเป็นไปได้สูงที่จะถูกเรียกใช้ในอนาคต** 

![Alt Text](https://media1.giphy.com/media/l0CRCmMBYQbL7dCmI/giphy.gif?cid=ecf05e470nis1vatq1klsfbt971hesjdxotahe9iyatwkdp6&ep=v1_gifs_search&rid=giphy.gif&ct=g)

ถ้าจะให้เข้าใจได้ง่าย ก็เหมือนการที่เราเดินเข้าไปในร้านอาหาร สั่งออเดอร์ และร้านได้มอบ**กริ่ง**ที่จะดังต่อเมื่อออเดอร์นั่นเสร็จเรียบร้อย ในขณะที่รอ เราสามารถทำกิจกรรมอื่นๆได้ เช่น อ่านหนังสือในร้าน หรือ เล่นโทรศัพท์ ในขณะเดียวกันถ้าหากออเดอร์ของเราเสร็จ **กริ่ง**ก็จะดังและเราสามารถรับออเดอร์กลับบ้านได้ 

 ```bash
 ในเหตุการณ์เหล่านี้ที่ยกมา ตัวกริ่งเอง จะเปรียบเสมือนตัว Future นั่นเอง
```
## สถานะของFuture 
มีด้วยกันทั้งหมดสองแบบ คือ:
- Uncompleted

- Completed

### Uncompleted
เมื่อเราเรียกใช้ asynchronous function (เป็นฟั่งก์ชั่นที่เวลา เราสั่งงานอะไรไปแล้วถ้าเป็นงานที่ใช้เวลานาน มันก็จะไล่ไปทำคำสั่งถัดไปเลยโดยไม่ได้รอให้คำสั่งก่อนหน้าทำเสร็จ) มันหมายถึงว่า future นั้นรอเพื่อให้ ฟังก์ชั่น asynchronous ทำงานของมันให้เรียบร้อยก่อน หรือ แสดงerror ออกมา

### Completed
หากการทำงานจบลงด้วยดี หรือ ปรากฏข้อผิดพลาดออกมา ชนิดข้อมูลของตัวFuture จะคืนค่าออกมาตามชนิดข้อมูลที่เราประกาศไว้ เช่น `Future<String>` ก็จะคืนค่า String `Future<int>` ก็จะคืนค่า int แต่ถ้าหากเราไม่ประกาศชนิดตัวแปรไว้เลย ตัวfuture จะไม่คืนค่าอะไรออกมาเลย ดังนั้น ชนิดของข้อมูลของfuture ตัวนี้คือ `Future<void>`


> ℹ️ **Note:** ถ้าการทำงานของ asynchronous function ไม่สำเร็จไม่ว่าจะกรณีใดๆก็ตาม ตัวfuture ก็จะerror ตามไปด้วย

## วิธีการสร้าง Future ใน Dart
เราสามารถสร้าง future ใน dart โดยการใช้ class **Future**  และนี่คือตัวอย่างฟังก์ชั่น ที่จะคืนค่า **Future<String>** หลังจากผ่านไป 10 วินาที

```bash
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() async {
  return Future.delayed(Duration(seconds: 10), () => 'Mark');
}
```

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **C**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>

typedef struct Future {
    char* value;
} Future;

void delay(int seconds) {
    sleep(seconds);
}

void complete(Future* future, char* value) {
    future->value = strdup(value);
}

Future getName() {
    Future future;
    delay(10);
    complete(&future, "Mark");
    return future;
}

int main() {
    printf("Start\n");
    Future nameFuture = getName();
    printf("name: %s\n", nameFuture.value);
    printf("End\n");
    return 0;
}
```

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Java**
```Java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.TimeUnit;

public class Main {
    public static CompletableFuture<String> getName() {
        CompletableFuture<String> future = new CompletableFuture<>();
        new Thread(() -> {
            try {
                Thread.sleep(10000); // การสั่งให้ตัว Thread รอ 10วินาที
                future.complete("Mark");
            } catch (InterruptedException e) {
                future.completeExceptionally(e);
            }
        }).start();
        return future;
    }

    public static void main(String[] args) {
        CompletableFuture<String> userNameFuture = getName();
        userNameFuture.thenAccept(result -> System.out.println("name: " + result));
    }
}

```
เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Python**
```Python
import asyncio

async def get_name():
    await asyncio.sleep(10)  # Sleep for 10 seconds
    return "Mark"

async def main():
    print("Start")
    name = await get_name()
    print(f"name: {name}")
    print("End")

asyncio.run(main())

```
 


### อีกวิธีในการสร้าง future คือการใช้ method **Future.value()** ที่จะคืนค่า **Future<String>** ในทันที

```Dart
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() {
  return Future.value('Mark');
}
```
เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **C**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

typedef struct Future {
    char* value;
} Future;

Future createFuture(char* value) {
    Future future;
    future.value = strdup(value);
    return future;
}

int main() {
    Future nameFuture = createFuture("Mark");
    printf("name: %s\n", nameFuture.value);
    return 0;
}
```

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Java**
```Java
import java.util.concurrent.CompletableFuture;

public class Main {
    public static CompletableFuture<String> getName() {
        return CompletableFuture.completedFuture("Mark");
    }

    public static void main(String[] args) {
        CompletableFuture<String> nameFuture = getName();
        nameFuture.thenAccept(result -> System.out.println("Name: " + result));
    }
}
```

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Python**

```Python
import asyncio

async def get_name():
    return "Mark"

async def main():
    name = await get_name()
    print(f"name: {name}")

asyncio.run(main())
```




## วิธีการใช้ Future ใน Dart
เราสามารถใช้ future ใน dart โดยการใช้ method **then()** และนี่คือตัวอย่างฟังก์ชั่นที่จะคืนค่า **Future<String>** หลังจากผ่านไป 10 วินาที

```Dart
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() async {
  return Future.delayed(Duration(seconds: 10), () => 'Anya forger');
}

// ฟังก์ชั่นหลัก
void main() {
  print("Hi! This is Dart language!!");
  print("Start here");
  getName().then((value) => print(value));
  print("End");
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
Hi! This is Dart language!!
Start here
End
Anya forger
</code></pre>
</details>

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **C**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>

typedef struct Future {
    char* value;
} Future;

void delay(int seconds) {
    sleep(seconds);
}

void complete(Future* future, char* value) {
    future->value = strdup(value);
}

Future getName() {
    Future future;
    delay(10);
    complete(&future, "Anya forger");
    return future;
}

int main() {
    printf("Hi! This is C language!!");
    printf("Start here\n");
    Future nameFuture = getName();
    printf("%s\n", nameFuture.value);
    printf("End\n");
    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>
Hi! This is C language!!
Start here
End
Anya forger
</code></pre>
</details>


เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Java**
```Java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.TimeUnit;

public class Main {
    public static CompletableFuture<String> getName() {
        return CompletableFuture.supplyAsync(() -> {
            try {
                Thread.sleep(10000); // สั่งให้Thread รอ 10 วินาที
                return "Anya forger";
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        });
    }

    public static void main(String[] args) {
        System.out.println("Hi! This is Java language!!");
        System.out.println("Start here");
        CompletableFuture<String> nameFuture = getName();
        nameFuture.thenAccept(value -> System.out.println(value));
        System.out.println("End");
    }
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
Hi! This is Java language!!
Start here
End
Anya forger
</code></pre>
</details>

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Python**

```Python
import asyncio

async def get_name():
    await asyncio.sleep(10)  # Sleep for 10 seconds
    return "Anya forger"

async def main():
    print("Start here")
    name = await get_name()
    print(name)
    print("End")

asyncio.run(main())
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
Hi! This is Python language!!
Start here
End
Anya forger
</code></pre>
</details>


## ตัวอย่างการทำงานของ Future ในภาษา Dart

ในCode ตัวอย่างด้านล่าง เราจะสร้างฟังก์ชั่น ชื่อ **middleFunction()** ที่จะคืนค่า future ซึ่งฟังก์ชั่นตัวนี้จะคืนค่า **Future<String>** หลังจากผ่านไป 50 วินาที

```Dart
void main() {
  print("Dart example :")  
  print("Start tong nee na ja ");
  getData();
  print("job lao jaaaaa");
}

void getData() async{
  String data = await middleFunction();
  print(data);
}

Future<String> middleFunction(){
  return Future.delayed(Duration(seconds:50), ()=> "Anya forger love her mom but i have to wait 50 sec ToT");
}
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>
Dart example :
Start tong nee na ja 
job lao jaaaaa
Anya forger love her mom but i have to wait 50 sec ToT
</code></pre>
</details>

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **C**
```C
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <pthread.h>

typedef struct Future {
    char* value;
} Future;

void delay(int seconds) {
    sleep(seconds);
}

void complete(Future* future, char* value) {
    future->value = strdup(value);
}

void* middleFunction(void* arg) {
    Future* future = (Future*)arg;
    delay(50);
    complete(future, "Anya forger love her mom but I have to wait 50 sec ToT");
    return NULL;
}

Future getData() {
    Future future;
    pthread_t thread;
    pthread_create(&thread, NULL, middleFunction, &future);
    pthread_join(thread, NULL);
    return future;
}

int main() {
    printf("C example :\n");
    printf("Start tong nee na ja\n");
    Future dataFuture = getData();
    printf("%s\n", dataFuture.value);
    printf("job lao jaaaaa\n");
    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>
C example :
Start tong nee na ja 
job lao jaaaaa
Anya forger love her mom but i have to wait 50 sec ToT
</code></pre>
</details>

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Java**


```Java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.TimeUnit;

public class Main {
    public static void main(String[] args) {
        System.out.println("Java example :")
        System.out.println("Start tong nee na ja ");
        getData();
        System.out.println("job lao jaaaaa");
    }

    public static void getData() {
        CompletableFuture<String> dataFuture = middleFunction();
        dataFuture.thenAccept(data -> System.out.println(data));
    }

    public static CompletableFuture<String> middleFunction() {
        return CompletableFuture.supplyAsync(() -> {
            try {
                TimeUnit.SECONDS.sleep(50); // Sleep for 50 seconds
                return "Anya forger love her mom but i have to wait 50 sec ToT";
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        });
    }
}

```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
Java example :
Start tong nee na ja 
job lao jaaaaa
Anya forger love her mom but i have to wait 50 sec ToT
</code></pre>
</details>


```Python
import asyncio

async def get_data():
    print("Python example:")
    print("Start tong nee na ja ")
    await get_middle_function()
    print("job lao jaaaaa")

async def get_middle_function():
    data = await middle_function()
    print(data)

async def middle_function():
    await asyncio.sleep(50)  # Sleep for 50 seconds
    return "Anya forger love her mom but I have to wait 50 sec ToT"

async def main():
    await get_data()

asyncio.run(main())
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>
Python example :
Start tong nee na ja 
job lao jaaaaa
Anya forger love her mom but i have to wait 50 sec ToT
</code></pre>
</details>

เราจะเห็นได้ว่า โปรแกรมจะแสดงผล "ชื่อภาษานั้นๆ example" และตามด้วย "Start tong nee na ja" ก่อน หลังจากนั้น จะเรียก **getData()** เพื่อดึงข้อมูลในนั้นออกมา แต่การดึงข้อมูลออกมานั้นต้องรอ50วินาที โปรแกรมเลยไปทำงานในส่วนการแสดงผล "job lao jaaaaa" แทน เมื่อครบเวลา จึงแสดง "Anya forger love her mom" จากนั้นก็จบโปรแกรม

## ข้อแตกต่างหลักๆระหว่าง Dart และ ภาษาโปรแกรมอื่นๆ
 - ใน Dart `await` ใช้พร้อมกับ `Future.delayed` เพื่อใช้ในการรอโปรแกรมให้ไปทำงานส่วนตรงอื่นก่อน ซึ่งไม่ต้องสร้างคำสั่งเพิ่มเติมขึ้นมา

 - ใน C ในการทำ Delay เราจะใช้คำสั่ง `Sleep()` แทนเพื่อสั่งรอ

 - ใน Java เราใช้ method `Thread.sleep()` เพื่อใช้ในการรอโปรแกรมให้ไปทำงานส่วนตรงอื่นก่อน และไม่มีการสั่งรอโดยตรงเหมือน Dart จึงต้องเรียก Thread เข้ามาใช้ด้วย

 - ใน Python ฟังก์ชั่น `time.sleep()` ต้อง import เข้ามาก่อนจึงจะสามารถเรียกใช้ได้


## Link เนื้อหาเพิ่มเติม
https://dart-tutorial.com/asynchronous-programming/future-in-dart/

https://api.dart.dev/stable/3.1.0/dart-async/Future-class.html

https://docs.oracle.com/javase/8/docs/api/java/lang/Thread.html

https://devdocs.io/c/language/typedef

https://pubs.opengroup.org/onlinepubs/009696799/functions/sleep.html

https://docs.python.org/3/library/asyncio.html

https://docs.oracle.com/cd/E26502_01/html/E35303/tlib-1.html

## Video
[Future in Dart](https://youtu.be/AB3Ft04H6e0?si=WBOllNT2BylqR1Qd)

## Slide
[Future in Dart](https://drive.google.com/file/d/1x5U_ROHOfKfRq3SQeNZ6SB6uHzXo-KnZ/view?usp=sharing)
