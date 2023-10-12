# Switch Case in Dart

ใน tutorial นี้จะเรียนรู้การใช้ **switch case** ในภาษา **Dart** เพื่อควบคุมการทำงานของโปรแกรม โดยคำสั่ง switch case จะใช้ในการประมวลผลโปรแกรมตามเงื่อนไขที่กำหนด

### Switch Case Statement
คำสั่ง **switch** ทำการตรวจสอบนิพจน์(expression) และเปรียบเทียบผลลัพธ์กับค่าที่กำหนด ถ้าเท่ากัน คำสั่ง **switch** จะดำเนินการในคำสั่งส่วนนั้นของ **case** ที่ตรงกัน

ภายในคำสั่ง switch ใช้ตัวดำเนินการเปรียบเทียบ (==) เพื่อเปรียบเทียบจำนวนเต็ม, สตริง, ชุดเลขประเภท (enumeration) หรือค่าคงที่ที่ระบุระหว่างการคอมไพล์

### หลักการทำงานของ Switch Case
![flow-SwitchCase](https://github.com/soonklang/dart-tutorial/assets/95559071/019cb533-7aea-462f-b251-3144a7a6b9a7)
## Syntax
- ### ในภาษา Dart, C, Java, Javascript, C++, C# จะใช้ switch case
```dart
switch(expression) {
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
    case value3:
        // statements
        break;
    default:
       // default statements
}
```
กระบวนการทำงาน **switch case**
- นิพจน์ถูกประเมินครั้งเดียวและเปรียบเทียบกับค่าของแต่ละ **case**
- ถ้านิพจน์ตรงกันกับค่าของ **case 1** คำสั่งใน **case 1** จะถูกประมวลผล ในทางเดียวกัน กรณีค่าที่ 2 จะถูกประมวลผลหากนิพจน์ตรงกับ **case 2** ถ้านิพจน์ตรงกับค่าของ **case 3** คำสั่งใน **case** 3 ก็จะถูกประมวลผล
- คีย์เวิร์ด **break** ใช้ในการบอกให้ออกจากคำสั่ง **switch** เนื่องจากคำสั่งใน case block เสร็จสิ้น
- หากไม่มีการตรงกัน คำสั่งในบล็อก **default** จะถูกประมวลผล

> [!NOTE]
> **สามารถใช้ Switch case เพื่อเป็นทางเลือกแทนเงื่อนไข if-else-if ได้**

- ### ในภาษา Python ใช้ match case
```dart
parameter = "Geeksforgeeks"
match parameter:
    case first  :
        do_something(first)
    case second :
        do_something(second)       
    case third :
        do_something(third)
        .............
        ............
    case n :
        do_something(n)
    case _  :
          nothing_matched_function()
```
กระบวนการทำงาน **match case**
- ภาษา Python ใช้ match แทน switch
- คำสั่งและการทำงานคล้ายๆกับ switch case เพียงแต่มีบางคำที่ใช้ต่างกัน 

> [!IMPORTANT]
> **match case** เป็นคำสั่งใหม่ที่เพิ่มเข้ามา สามารถใช้ได้ใน Python 3.10 หรือ version ที่ใหม่กว่า

### ตัวอย่างกรณีที่ใช้ If Else If
```dart
void main(){
   var number = 3;
if (number == 1) {
        print("Number One.");
  }
else if (number == 2) {
       print("Number Two.");
     }
else if (number == 3) {
        print("Number Three.");
    }
else{
        print("Other.");
     }
 }
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Number Three. </code></pre>
</details>

## ตัวอย่างที่ 1: Switch Case
- ### ในภาษา Dart
```dart
void main() {
  int number = 3;
  switch (number) {
    case 1:
      print("Number One.");
      break;
    case 2:
      print("Number Two.");
      break;
    case 3:
      print("Number Three.");
      break;
    default:
      print("Other.");
  }
}

```
> - ในกรณีที่ 1 switch ตรงกับ case 1 จะแสดงผลลัพธ์ Number One.
> - กรณีที่ 2 switch ตรงกับ case 2 จะแสดงผลลัพธ์ Number Two.
> - กรณีที่ 3 switch ตรงกับ case 3 จะแสดงผลลัพธ์ Number Three.
> - และกรณีที่ switch ไม่ตรงกันกับ case ที่กล่าวมา จึงแสดงผลลัพธ์ Other.
> - จากcodeข้างต้น เราได้ประกาศและกำหนดค่าของ number ให้มีค่าเป็น 3 ซึ่งเข้าเงื่อนไข case 3 จึงแสดงผลลัพธ์ Number Three. ออกมา

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Number Three. </code></pre>
</details>

- ### ในภาษา Java
```dart
public class Main {
    public static void main(String[] args) {
        int number = 3;
        switch (number) {
            case 1:
                System.out.println("Number One.");
                break;
            case 2:
                System.out.println("Number Two.");
                break;
            case 3:
                System.out.println("Number Three.");
                break;
            default:
                System.out.println("Other.");
                break;
        }
    }
}
```

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Number Three. </code></pre>
</details>

- ### ในภาษา C
```dart
#include <stdio.h>

int main() {
    int number = 3;
    switch (number) {
        case 1:
            printf("Number One.\n");
            break;
        case 2:
            printf("Number Two.\n");
            break;
        case 3:
            printf("Number Three.\n");
            break;
        default:
            printf("Other.\n");
    }

    return 0;
}
```

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Number Three. </code></pre>
</details>

- ### ในภาษา Python
```dart
def main():
    number = 3
    match number:
        case 1:
            print("Number One.")
        case 2:
            print("Number Two.")
        case 3:
            print("Number Three.")
        case _:
            print("Other.")

if __name__ == "__main__":
    main()
```

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Number Three. </code></pre>
</details>


## ตัวอย่างที่ 2: Switch Case On String
- ### ในภาษา Dart
```dart
void main() {
 const weather = "cloudy";
  switch (weather) {
    case "sunny":
        print("Its a sunny day. Put sunscreen.");
        break;
    case "snowy":
        print("Get your skis.");
      break;
    case "cloudy":
    case "rainy": 
      print("Please bring umbrella.");
      break;
    default:
        print("Sorry I am not familiar with such weather.");
      break;
  }
}
```

> - ในกรณีที่ 1 switch ตรงกับ case sunny จะแสดงผลลัพธ์ Its a sunny day. Put sunscreen.
> - กรณีที่ 2 switch ตรงกับ case snowy จะแสดงผลลัพธ์ Get your skis.
> - กรณีที่ 3 switch ตรงกับ case cloudy หรือ rainy  จะแสดงผลลัพธ์ Please bring umbrella.
> - และกรณีสุดท้ายที่ switch ไม่ตรงกันกับ case ที่กล่าวมา จะแสดงผลลัพธ์ Sorry I am not familiar with such weather.
> - จากcodeข้างต้น ได้ประกาศและกำหนดค่าของ weather = cloudy ซึ่งเข้าเงื่อนไขของกรณีที่ 3 จึงแสดงผลลัพธ์ Please bring umbrella.

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### ในภาษา Java
```dart
public class Main {
    public static void main(String[] args) {
        final String weather = "cloudy";
        switch (weather) {
            case "sunny":
                System.out.println("It's a sunny day. Put sunscreen.");
                break;
            case "snowy":
                System.out.println("Get your skis.");
                break;
            case "cloudy":
            case "rainy":
                System.out.println("Please bring an umbrella.");
                break;
            default:
                System.out.println("Sorry, I am not familiar with such weather.");
                break;
        }
    }
}
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>


- ### ในภาษา Python
```dart
def main():
    weather = "cloudy"
    match weather:
        case "sunny":
            print("It's a sunny day. Put sunscreen.")
        case "snowy":
            print("Get your skis.")
        case "cloudy"| "rainy":
            print("Please bring an umbrella.")
        case _:
            print("Sorry, I am not familiar with such weather.")

if __name__ == "__main__":
    main()
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

## ตัวอย่างที่ 3: Switch continue 
- ### ในภาษา Dart ตัวอย่างที่ 1
```dart
void main() {
  var command = 'TUESDAY';
  switch (command) {
    case 'MONDAY':
      print('MONDAY');
      break;
    case 'TUESDAY':
      print('TUESDAY');
      continue nowClosed;
    nowClosed:
    case 'NOW_CLOSED':
      print('This is now closed');
      break;
    case 'WEDNESDAY':
      print('WEDNESDAY');
      break;
    case 'THURSDAY':
      print('THURSDAY');
      break;
    case 'FRIDAY':
      print('FRIDAY');
      break;
    default:
      print('It\'s weekend');
  }
}
```
> - กำหนดค่าของตัวแปร command เป็น TUESDAY เพื่อใช้ทดสอบ switch กับเงื่อนไขต่างๆ
> - ใช้ switch ตรวจสอบค่าของ command ตามเงื่อนไขของ case 
> - ถ้าค่าของ command ตรงกับ case จะดำเนินการใน block ส่วนนั้น
> - ในกรณีที่ มี continue จะข้ามไปยัง lebel ที่กำหนด เช่น case TUESDAY จะข้ามไปยัง lebel ที่ชื่อ nowClosed
เมื่อเจอ continue ใน case TUESDAY code จะข้ามไปทำงานใน case NOW_CLOSED ต่อทันที และแสดงผล This is now closed
> - เมื่อคำสั่งใน block ของ case NOW_CLOSED ทำงานเสร็จสิ้น เราใช้คำสั่ง break เพื่อออกจาก switch และไม่ทำงานใน case อื่น ๆ ถ้าหากค่าของ command ไม่ตรงกับเงื่อนไขที่มี
> - ถ้าไม่เข้ากับ case ไหนเลย จะทำงานใน block default และแสดงผลลัพธ์เป็น It's weekend

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code>TUESDAY
This is now closed </code></pre>
</details>

- ### ในภาษา Dart ตัวอย่างที่ 2
```dart
void main() {
  String animal = 'tiger';
  switch (animal) {
    case 'tiger':
      print("it's a tiger");
      continue alsoCat;
    case 'lion':
      print("it's a lion");
      continue alsoCat;
    alsoCat: // ตำแหน่งที่เราจะทำการตัดสินใจต่อ
    case 'cat':
      print("it's a cat");
      break;
  }
}

```
> - กำหนดค่าของตัวแปร animal เป็น tiger เพื่อใช้ทดสอบ switch กับเงื่อนไขต่างๆ
> - ใน switch case เรามีการใช้ continue เพื่อข้ามไปทำงานที่ alsoCat
> - หลังจากทำงานใน case tiger หรือ case lion ใน alsoCat กำหนดตำแหน่งที่เราจะทำการตัดสินใจต่อ
> - ใน case cat จะทำงานและแสดงผล "it's a cat" หลังจากทำงานที่ alsoCat.

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code>it's a tiger
it's a cat</code></pre>
</details>

## ตัวอย่างที่ 4:
- ### Switch Case On Enum
## Syntax
```dart
enum enum_name { 
  constant_value1, 
  constant_value2, 
  constant_value3 
  }
```
- ### ในภาษา Dart
```dart
// define enum outside main function
enum Weather{ sunny, snowy, cloudy, rainy}
// main method
void main() {
 const weather = Weather.cloudy;
  switch (weather) {
    case Weather.sunny:
        print("Its a sunny day. Put sunscreen.");
        break;
    case Weather.snowy:
        print("Get your skis.");
      break;
    case Weather.rainy:
    case Weather.cloudy:
      print("Please bring umbrella.");
      break;
    default:
        print("Sorry I am not familiar with such weather.");
      break;
  }
}
```
> - จากcodeข้างต้น ได้มีการนิยาม enum Weather ที่เก็บสภาพอากาศ (sunny, snowy, cloudy, rainy)
> - โดยได้มีการกำหนดค่า weather ให้เป็น cloudy โดยใช้ enum Weather เป็นชนิดข้อมูล โดยใช้ switch case ในการตรวจสอบค่า weather
> - เมื่อทำการตรวจสอบแล้วพบว่าตรงกับ case Weather.cloudy
> - จึงแสดงผลลัพธ์ Print Please bring an umbrella. ออกมา

<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### ในภาษา Java
```dart
public class Main {
    // Define enum outside the main function
    enum Weather { sunny, snowy, cloudy, rainy }

    public static void main(String[] args) {
        Weather weather = Weather.cloudy;
        
        switch (weather) {
            case sunny:
                System.out.println("It's a sunny day. Put sunscreen.");
                break;
            case snowy:
                System.out.println("Get your skis.");
                break;
            case rainy:
            case cloudy:
                System.out.println("Please bring an umbrella.");
                break;
            default:
                System.out.println("Sorry, I am not familiar with such weather.");
                break;
        }
    }
}
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### ในภาษา C
```dart
#include <stdio.h>
#include <string.h>

// Define enum outside the main function
enum Weather { sunny, snowy, cloudy, rainy };

int main() {
    enum Weather weather = cloudy;
    
    switch (weather) {
        case sunny:
            printf("It's a sunny day. Put sunscreen.\n");
            break;
        case snowy:
            printf("Get your skis.\n");
            break;
        case rainy:
        case cloudy:
            printf("Please bring an umbrella.\n");
            break;
        default:
            printf("Sorry, I am not familiar with such weather.\n");
            break;
    }
    
    return 0;
}
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### ในภาษา Python
```dart
from enum import Enum

class Weather(Enum):
    sunny = 1
    snowy = 2
    cloudy = 3
    rainy = 4

def main():
    weather = Weather.cloudy
    match weather:
        case Weather.sunny:
            print("It's a sunny day. Put on sunscreen.")
        case Weather.snowy:
            print("Get your skis.")
        case Weather.rainy| Weather.cloudy:
            print("Please bring an umbrella.")
        case _:
            print("Sorry, I am not familiar with such weather.")

if __name__ == "__main__":
    main()
```
<details open>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

## ข้อดีของการใช้ Switch Case
คำสั่ง **switch case** เป็นรูปแบบที่เรียบง่ายของคำสั่ง if ที่ถูกซ้อน if-else กัน หรือ if else if ปัญหาที่เกิดขึ้นจาก if-else ที่ถูกซ้อนกันคือมันสร้างความซับซ้อนในโปรแกรมเมื่อมีการเพิ่มเส้นทางหลายเส้นเพิ่มขึ้น คำสั่ง **switch case** จึงช่วยลดความซับซ้อนของโปรแกรมได้  

## เปรียบเทียบการใช้ Switch Case ในภาษา Dart และ ภาษาอื่นๆ
1. **การเรียกใช้งาน**: การใช้งาน switch case เริ่มต้นด้วยคำสั่ง switch และใช้คำสั่ง case เพื่อกำหนดเงื่อนไขที่เราต้องการเปรียบเทียบ
2. **ประเภทของเงื่อนไข**: ภาษา Dart และ ภาษา Java รองรับการใช้งาน switch case กับ strings และตัวเลข  ภาษา C รองรับ characters และ integers และใน ภาษา Python รองรับการใช้งาน match case
3. **Fall-Through** (กรณีถัดไปโดยไม่ต้องหยุด): ใน Dart และ C สามารถใช้งาน Fall-Through โดยไม่ต้องมี break ระหว่าง case ที่มีเงื่อนไขเป็นจริง ในขณะที่ Java และ Python จำเป็นจะต้องระบุ **break** เพื่อหยุดการกระทำหรือย้ายไปยัง case ถัดไป
4. **Default Case** (ทำงานเมื่อไม่มีกรณีอื่นในคำสั่ง): ทุกภาษามี default หรือ else case ที่จะทำงานเมื่อไม่มีเงื่อนไขใดที่ตรงกัน

## **References**
- https://dart-tutorial.com/conditions-and-loops/switch-case-in-dart/
- https://www.darttutorial.org/dart-tutorial/dart-switch/
- https://www.geeksforgeeks.org/python-match-case-statement/
- https://www.w3schools.com/c/c_switch.php
- https://www.w3schools.com/java/java_switch.asp
- https://www.w3schools.com/js/js_switch.asp
- https://www.javatpoint.com/dart-switch-case-statement
- https://flutterrdart.com/dart-switch-case-statement-with-examples/
- https://flutterbyexample.com/lesson/switch-statements-and-case

## **Link Video**
https://youtu.be/OU0TFuwThdc


## **Slides**
[Switch Case in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12880759/Switch.Case.in.Dart.pdf)
<br>[Switch Case in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12880765/Switch.Case.in.Dart.pptx) (V.1)
<br>[Switch Case in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12882181/Switch.Case.in.Dart.pptx) (V.2)



