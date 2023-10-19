# Generate Random Number 🤡
ใน tutorial นี้คุณจะได้เรียนรู้เกี่ยวกับการสุ่มตัวเลขในภาษา Dart เราจะแนะนำให้คุณรู้จักกับ Built-in เมธอดของภาษาที่เราสามารถใช้สำหรับสุ่มตัวเลขในภาษาDart 

## เนื้อหาในหัวข้อนี้ ##
- การสุ่มตัวเลขด้วยคลาส Random
- การสุ่มตัวเลขจาก 1-100
- การสุ่มตัวเลขทศนิยม
- เปรียบความแตกต่างของการสุ่มตัวเลขของภาษา Dart , C , Java , Python

 ## การสุ่มตัวเลขด้วยคลาส Random
 คลาส Random ใช้สร้างค่าสุ่มใน Dart จากไลบรารี dart:math เราสามารถสร้างค่า boolean, integer หรือ double สุ่มได้โดยใช้คลาสนี้ ก่อนอื่นต้อง Import dart:math เข้ามาก่อน
 
`Import`
 ```dart    
import 'dart:math';
```

## การสุ่มตัวเลขจากคลาส Random จะมีด้วยกันอยู่ 2 แบบคือ

`แบบที่ 1 Random()`
 ```dart    
Random r1 = new Random();
```
`แบบที่ 2 Random.secure()`
 ```dart    
Random r2 = new Random.secure();
```

### แบบที่ 1 คือ Random([int? seed]) ###
   คือ ตัวสร้าง (constructor) ของคลาส Random ในภาษา Dart ที่ใช้สร้าง random number generator โดยมีพารามิเตอร์ชื่อ seed เป็นค่าทางเลือกที่คุณสามารถระบุได้ พารามิเตอร์ seed นี้ถูกใช้เพื่อกำหนดค่าเริ่มต้นของสถานะ random number generator ซึ่งจะทำให้ค่าที่สุ่มออกมามีลักษณะและลำดับที่สอดคล้องกันหากกำหนด seed

`Example`
 ```dart    
import 'dart:math';

void main() {
   print("\nUsing Random()");
   Random r1 = new Random();
   print(r1.nextInt(100)); //จะทำการสุ่มตััวเลขตั้งแต่ 0-99
}
```
<details>
  <summary><strong>Output</strong></summary>
</details>

```dart  
Using Random()
37
```
   ### แบบที่ 2 คือ Random.secure() 
 คือ Random.secure() ใช้ สร้างrandom number generator ที่มีความสามารถในการสร้างตัวเลขสุ่มที่เหมาะสำหรับการใช้งานทางความปลอดภัย โดยใช้แหล่งเอนโทรปีที่มีความสามารถในการสร้างตัวเลขสุ่มที่มีความสามารถเพิ่มเติมเหมือนในการทำงานเรื่องความปลอดภัย

 `Example`
 ```dart    
import 'dart:math';

void main() {
   print("\nUsing Random.secure()");
   Random r2 = new Random.secure();
   print(r2.nextInt(100));
}
```
<details>
  <summary><strong>Output</strong></summary>
</details>

```dart  
Using Random.secure()
29
```
> เราจะเห็นได้ว่า method nextInt() ที่รับ parameter เป็นจำนวนเต็ม จะทำการสุ่มตัวเลข ตั้งแต่ค่า default ก็คือ 0 จนถึง n-1
>
 ## ❗❗❗ แล้วถ้าเราอยากจะเปลี่ยนค่าเริ่มต้นจะต้องทำยังไง? ❗❗❗ 
 ## การสุ่มตัวเลขจาก 1-100
  โดยปกติแล้วตัวเลขที่ได้จากการสุ่มจากเมธอดทั้งหมดนั้นจะเริ่มต้นจาก 0 ซึ่งนี่เป็นการทำงานพื้นฐานของเมธอด แต่ในการเขียนโปรแกรมจริงนั้น คุณอาจต้องการสุ่มตัวเลขจากช่วงอื่นๆ ยกตัวอย่างเช่น 1 - 10, 1 - 100 หรือ 50 - 100 เป็นต้น ในตัวอย่างนี้ เราจะมาประยุกต์ใช้เมธอดจากตัวอย่างก่อนหน้าเพื่อสุ่มตัวเลขที่มีค่าระหว่าง 1 - 10 , 1 - 100 , 50 - 100   นี่เป็นโค้ดของโปรแกรม
  
 `Example`
 ```dart    
import 'dart:math';

void main() {
   Random r1 = new Random();     //ตัวเลขจำนวนเต็มที่บวกเข้าไปข้างหลังmethod จะเป็นตัวกำหนดค่าเริ่มต้น
   print(r1.nextInt(10)+1);      // สุ่มตัวเลขตั้งแต่ 1-10
   print(r1.nextInt(100)+1);    // สุ่มตัวเลขตั้งแต่ 1-100
   print(r1.nextInt(101)+50); // สุ่มตัวเลขตั้งแต่ 50-100
}
```
<details>
  <summary><strong>Output</strong></summary>
</details>

```dart  
9
55
78
```
> เราจะเห็นได้ว่าหลัง method nextInt() ที่บวกด้วยค่า constant จะเป็นตัวกำหนดค่าเริ่มต้น
> 
> ส่วนค่าใน parameter จะเป็นตัวกำหนดค่าสุดท้ายที่จะสุ่มได้ ถ้าค่าเริ่มต้นคือ 1 และ ค่าสุดท้ายคือ n
>
> range ของเลขที่จะสุ่มคือ [ 0 , n - 1]

## การสุ่มตัวเลขทศนิยม
   การสุ่มตัวเลขทศนิยมเราใช้ method `nextDouble()` ในการสุ่ม

`Example`
```dart    
import 'dart:math';

void main() {
   Random r1 = new Random();
   print(r1.nextDouble()); 
   print(r1.nextDouble()*256);
   print((r1.nextDouble()*(256-250)+250));  
}
```
<details>
  <summary><strong>Output</strong></summary>
</details>

```dart  
0.6221115104341204
176.945116547545
253.53952131205276
```

> เราจะเห็นได้ว่า method nextDouble() ถ้าเราไม่ * ค่าคงที่เข้าไปข้างหลังช่วงที่จะสุ่มได้จะเป็น [0.0 , 1.0)
>
> แต่ถ้าเราทำการ * ค่าคงที่เข้าไปหลัง nextDouble() จะเป็นการกำหนดช่วงค่าสุดท้ายที่จะสุ่มได้ 
> อย่างเช่นตัวอย่าง r1.nextDouble()*256 ช่วงของตัวเลขที่จะสุ่มได้คือ [0.0 , 256.0)
### เปรียบความแตกต่างของการสุ่มตัวเลขของภาษา Dart , C , Java , Python

- ตัวอย่างการสุ่มเลข 0 - 99
  
### Dart
```dart    
import 'dart:math';

void main() {
   Random r1 = new Random();
   print(r1.nextInt(100));
}
```

<details>
  <summary><strong>Output</strong></summary>
</details>

```dart    
40
```

### C
```C  
#include <stdio.h>      
#include <stdlib.h>  
void main()  
{     
   int num;  
   num = rand() % 99
   printf ("%d", num);  
}  
```

<details>
  <summary><strong>Output</strong></summary>
</details>

```C   
65
```

### Java
```Java 
import java.util.Random;
   
public class generateRandom{
   
    public static void main(String args[])
    {
        Random rand = new Random();
        int rand_int1 = rand.nextInt(100);
        System.out.println(rand_int1);
    }
}
```

<details>
  <summary><strong>Output</strong></summary>
</details>

```Java  
99
```
### Python
```Python 
import random
print(random.randint(0,99))
```

<details>
  <summary><strong>Output</strong></summary>
</details>

```Python  
11
```

> ✔️เราจะเห็นได้ว่า ภาษา Dart,C และ Python มีการใช้ Random ที่คล้ายกันคือการรับ parameter ค่าคงที่ที่กำหนดช่วงของค่าสุดท้ายที่สามารถสุ่มได้ ✔️
> 
> ❗❗ แต่ในภาษา C จะต้องนำตัวเลขมา % ข้างหลังเพื่อกำหนดค่าสิ้นสุดที่สามารถสุ่มได้ ❗❗

## Link Slide : 
- [Generate Random Number Silde(google_drive)](https://docs.google.com/presentation/d/1aEdE28PKA6iLmqUr6I7x7cfrGzo6Ma_C/edit?usp=sharing&ouid=113718269283843830663&rtpof=true&sd=true)
- [Generate_Random_Number_640710974.pdf(google_drive)](https://drive.google.com/file/d/1sh1qwjz8mH_wQnZ-9X3jufvEtjjhb63R/view?usp=sharing)
- [Generate_Random_Number_640710974.pdf](https://github.com/soonklang/dart-tutorial/files/12884723/Generate_Random_Number_640710974.pdf)
- [Generate_Random_Number_640710974.pptx](https://github.com/soonklang/dart-tutorial/files/12889115/Generate_Random_Number_640710974.pptx)

Link Video : [Generate Random Number Video](https://youtu.be/F55rFfzL85Y)

## Reference
[Random class - dart:math library - Dart API](https://api.dart.dev/stable/3.1.0/dart-math/Random-class.html)
<br>
[Generate Random Number - Dart Tutorial](https://dart-tutorial.com/dart-how-to/generate-random-number-in-dart/)
<br>
[Dart/Flutter - Generate Random Number Examples](https://www.woolha.com/tutorials/dart-generate-random-number-examples)
<br>
[Generating random numbers in Java](https://www.geeksforgeeks.org/generating-random-numbers-in-java/)
<br>
[Random Function in C - javatpoint](https://www.javatpoint.com/random-function-in-c#:~:text=In%20the%20C%20programming%20language,need%20to%20implement%20the%20stdlib.)
<br>
[Python Program to Generate a Random Number](https://www.programiz.com/python-programming/examples/random-number)
<br>
[java.util.Random (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/util/Random.html)
<br>
[dart:math - math and random](https://dart.dev/guides/libraries/library-tour#math-constants)
<br>
[Random — Python 3.11.5 documentation](https://docs.python.org/3/library/random.html)
<br>
[ISO Random (The GNU C Library)](https://www.gnu.org/software/libc/manual/html_node/ISO-Random.html)
