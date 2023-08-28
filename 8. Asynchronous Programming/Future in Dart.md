

# Future in Dart

ใน dart Future แสดงถึง ค่าของตัวแปร(value) หรือ ข้อผิดพลาด(error) ที่ยังไม่สามารถถูกเรียกใช้ได้ในขณะหนึ่ง แต่มันจะแสดงถึงค่าที่มีความเป็นไปได้สูงที่จะถูกเรียกใช้ในอนาคต 

ถ้าจะให้เข้าใจได้ง่าย ก็เหมือนการที่เราเดินเข้าไปในร้านอาหาร สั่งออเดอร์ และร้านได้มอบ**กริ่ง**ที่จะดังต่อเมื่อออเดอร์นั่นเสร็จเรียบร้อย ในขณะที่รอ เราสามารถทำกิจกรรมอื่นๆได้ เช่น อ่านหนังสือในร้าน หรือ เล่นโทรศัพท์ ในขณะเดียวกันถ้าหากออเดอร์ของเราเสร็จ **กริ่ง**ก็จะดังและเราสามารถรับออเดอร์กลับบ้านได้ 

 ```bash
 ในเหตุการณ์เหล่านี้ที่ยกมา ตัวกริ่งเอง จะเปรียบเสมือนตัว Future นั่นเอง
```
### สถานะของFuture 
- Uncompleted

- Completed

### Uncompleted
เมื่อเราเรียกใช้ asynchronous funtion (เป็นฟั่งก์ชั่นที่เวลา เราสั่งงานอะไรไปแล้วถ้าเป็นงานที่ใช้เวลานาน มันก็จะไล่ไปทำคำสั่งถัดไปเลยโดยไม่ได้รอให้คำสั่งก่อนหน้าทำเสร็จ) มันหมายถึงว่า future นั้นรอเพื่อให้ ฟังก์ชั่น asynchronous ทำงานของมันให้เรียบร้อยก่อน หรือ แสดงerror ออกมา

### Completed
หากการทำงานจบลงด้วยดี หรือ ปรากฏข้อผิดพลาดออกมา ชนิดข้อมูลของตัวFuture จะคืนค่าออกมาตามชนิดข้อมูลที่เราประกาศไว้ เช่น **Future<String>** ก็จะคืนค่า String **Future<int>** ก็จะคืนค่า int แต่ถ้าหากเราไม่ประกาศชนิดตัวแปรไว้เลย ตัวfuture จะไม่คืนค่าอะไรออกมาเลย ดังนั้น ชนิดของข้อมูลของfuture ตัวนี้คือ **Future<void> **


> ℹ️ **Note:** ถ้าการทำงานของ asynchronous function ไม่สำเร็จไม่ว่าจะกรณีใดๆก็ตาม ตัวfuture ก็จะerror ตามไปด้วย

## วิธีการสร้าง Future ใน Dart
เราสามารถสร้าง future ใน dart โดยการใช้ class **Future**  และนี่คือตัวอย่างฟังก์ชั่น ที่จะคืนค่า **Future<String>** หลังจากผ่านไป 10 วินาที

```bash
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() async {
  return Future.delayed(Duration(seconds: 10), () => 'Mark');
}
```

เปรียบเทียบกับการทำแบบเดียวกันใน ภาษา **Java**
```bash
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




อีกวิธีในการสร้าง future คือการใช้ method **Future.value()** ที่จะคืนค่า **Future<String>** ในทันที

```bash
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() {
  return Future.value('Mark');
}
```

ใน **Java**
```bash
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


## วิธีการใช้ Future ใน Dart
เราสามารถใช้ future ใน dart โดยการใช้ method **then()** และนี่คือตัวอย่างฟังก์ชั่นที่จะคืนค่า **Future<String>** หลังจากผ่านไป 10 วินาที

```bash
// ฟังก์ชั่นเพื่อคืนค่า Future
Future<String> getName() async {
  return Future.delayed(Duration(seconds: 10), () => 'Anya forger');
}

// ฟังก์ชั่นหลัก
void main() {
  print("Start here");
  getName().then((value) => print(value));
  print("End");
}
```

Output 
```bash
Start here
End
Anya forger
```

การใช้งานแบบเดียวกันในภาษา **Java**
```bash
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
        System.out.println("Start here");
        CompletableFuture<String> nameFuture = getName();
        nameFuture.thenAccept(value -> System.out.println(value));
        System.out.println("End");
    }
}
```

Output ทีได้ออกมาจะเหมือนในภาษาDart ด้านบน



## ตัวอย่างการทำงานของ Future ในภาษา Dart

ในCode ตัวอย่างด้านล่าง เราจะสร้างฟังก์ชั่น ชื่อ **middleFunction()** ที่จะคืนค่า future ซึ่งฟังก์ชั่นตัวนี้จะคืนค่า **Future<String>** หลังจากผ่านไป 50 วินาที

```bash
void main() {
  print("Start tong nee na ja ");
  getData();
  print("job lao jaaaaa");
}

void getData() async{
  String data = await middleFunction();
  print(data);
}

Future<String> middleFunction(){
  return Future.delayed(Duration(seconds:50), ()=> "Anya forger love her mom");
}
```

ตัวอย่าง ในภาษา **Java**

Output
```bash
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.TimeUnit;

public class Main {
    public static void main(String[] args) {
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
                return "Anya forger love her mom";
            } catch (InterruptedException e) {
                throw new RuntimeException(e);
            }
        });
    }
}

```

Output
```bash
Start tong nee na ja 
job lao jaaaaa
Anya forger love her mom
```

เราจะเห็นได้ว่า โปรแกรมจะแสดงผล "Start tong nee na ja" ก่อน หลังจากนั้น จะเรียก **getData()** เพื่อดึงการในนั้นออกมา แต่การดึงข้อมูลออกมานั้นต้องรอ50วินาที โปรแกรมเลยไปทำงานในส่วนการแสดงผล "job lao jaaaaa" แทน เมื่อครบเวลา จึงแสดง "Anya forger love her mom" จากนั้นก็จบโปรแกรม

## ข้อแตกต่างระหว่าง ของตัว Dart และ Java
1.ภาษา และ Syntax:
- ตัวDart ใช้ **'async'** และ **'wait'** ซึ่งเป็นคีย์เวิร์ดสำคัญที่ใช้ในการเขียนโปรแกรมแบบ asynchronous ทำให้โค้ดอ่านง่ายมากขึ้น
- ในขณะที่ Java ต้องสร้างclass และ เรียกใช้ Thread เพื่อรองรับการทำงานแบบ asynchronous


## Link เนื้อหาเพิ่มเติม
[Dart-tutorial](https://dart-tutorial.com/asynchronous-programming/future-in-dart/)

[Dart.dev](https://api.dart.dev/stable/3.1.0/dart-async/Future-class.html)
