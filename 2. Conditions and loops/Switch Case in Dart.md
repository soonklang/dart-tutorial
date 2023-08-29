# Switch Case in Dart

ใน tutorial นี้คุณจะเรียนรู้การใช้ switch case ในภาษา Dart เพื่อควบคุมกระแสของโปรแกรมของคุณ คำสั่ง switch case ใช้ในการประมวลผลบล็อกของโค้ดตามเงื่อนไขที่กำหนด

### Switch Case Statement
คำสั่ง switch ทำการประเมินนิพจน์และเปรียบเทียบผลลัพธ์ของมันกับค่าในเซ็ตหนึ่ง ถ้าเท่ากัน คำสั่ง switch จะดำเนินการในส่วนคำสั่งใน case ที่ตรงกัน

ภายในคำสั่ง switch ใช้ตัวดำเนินการเปรียบเทียบ (==) เพื่อเปรียบเทียบจำนวนเต็ม สตริง ชุดเลขประเภท (enumeration) หรือค่าคงที่ที่ระบุระหว่างการคอมไพล์

### หลักการทำงานของ Switch Case
![image](https://github.com/chonnigan/PL/assets/95559071/2c3d088d-25e0-4e04-ad54-466c3e2ba685)

## Syntax
- ### ในภาษา Dart , C, Java , Javascript ใช้ switch case
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
- หากนิพจน์ตรงกับค่าของ case ค่าที่ 1 คำสั่งใน case ค่าที่ 1 จะถูกประมวลผล ในทางเดียวกัน กรณีค่าที่ 2 จะถูกประมวลผลหากนิพจน์ตรงกับ case ค่าที่ 2 ถ้านิพจน์ตรงกับค่าของ case ค่าที่ 3 คำสั่งใน case ค่าที่ 3 จะถูกประมวลผล
- คีย์เวิร์ด **break** ใช้ในการบอก Dart ให้ออกจากคำสั่ง switch เนื่องจากคำสั่งในบล็อก case เสร็จสิ้น
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

> [!IMPORTANT]
> สามารถใช้ match case ได้ใน Python 3.10 หรือ version ที่ใหม่กว่า

### ตัวอย่างกรณีที่ใช้ If Else If
```dart
void main(){
   var color = 2;
if (color == 1) {
        print("Pink");
  }
else if (color == 2) {
       print("Yellow");
     }
else{
        print("Invalid color");
     }
 }
```
<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Yellow </code></pre>
</details>

## ตัวอย่างที่ 1: Switch Case
- ### ในภาษา Dart
```dart
void main() {
  var color = 2;
  switch (color) {
    case 1:
        print("Pink");
        break;
    case 2:
        print("Yellow");
      break;
    default:
        print("Invalid color");
      break;
  }
}
```
> ในกรณีที่1 switch ตรงกับ case 1 จะทำการ Print "Pink"
<br>กรณีที่2 switch ตรงกับ case 2 จะทำการ Print "ํYellow"
<br>และกรณีที่ switch ไม่ตรงกันกับ case ที่กล่าวมา จึงทำการ Print "Invalid color"
<br>จากโค้ดข้างต้น เราได้ประกาศและกำหนดค่าของ color ให้มีค่าเป็น 2 ซึ่งเข้าเงื่อนไข case 2 จึง Print "ํYellow" ออกมา

<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Yellow </code></pre>
</details>

- ### ในภาษา Java
```dart
public class Main {
    public static void main(String[] args) {
        int color = 2;
        switch (color) {
            case 1:
                System.out.println("Pink");
                break;
            case 2:
                System.out.println("Yellow");
                break;
            default:
                System.out.println("Invalid color");
                break;
        }
    }
}
```

<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Yellow </code></pre>
</details>

- ### ในภาษา Python
```dart
def main():
    color = 2
    match color:
        case 1:
            print("Pink")
        case 2:
            print("Yellow")
        case _:
            print("Invalid color")

if __name__ == "__main__":
    main()
```

<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Yellow </code></pre>
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

> ในกรณีที่1 switch ตรงกับ case sunny จะทำการ Print "Its a sunny day. Put sunscreen."
<br>กรณีที่2 switch ตรงกับ case snowy จะทำการ Print "Get your skis."
<br>กรณีที่3 switch ตรงกับ case cloudy หรือ rainy  จะทำการ Print "Please bring umbrella."
<br>และกรณีสุดท้ายที่ switch ไม่ตรงกันกับ case ที่กล่าวมา จึงทำการ Print "Sorry I am not familiar with such weather."
<br>จากโค้ดข้างต้น เราได้ประกาศและกำหนดค่าของ weather = "cloudy" ซึ่งเข้าเงื่อนไขของกรณีที่3 จึง Print "Please bring umbrella."

<details>
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
<details>
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
<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

## ตัวอย่างที่ 3:
- ### Switch Case On Enum
## Syntax
```dart
enum enum_name { 
  constant_value1, 
  constant_value2, 
  constant_value3 
  }
```
- ### Switch Using Enum ในภาษา Dart
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
<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### Switch Using Enum ในภาษา Java
```dart
public class Main {
    // Define enum outside the main function
    enum Weather { SUNNY, SNOWY, CLOUDY, RAINY }

    public static void main(String[] args) {
        Weather weather = Weather.CLOUDY;
        
        switch (weather) {
            case SUNNY:
                System.out.println("It's a sunny day. Put sunscreen.");
                break;
            case SNOWY:
                System.out.println("Get your skis.");
                break;
            case RAINY:
            case CLOUDY:
                System.out.println("Please bring an umbrella.");
                break;
            default:
                System.out.println("Sorry, I am not familiar with such weather.");
                break;
        }
    }
}
```
<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

- ### ในภาษา C
```dart
#include <stdio.h>
#include <string.h>

// Define enum outside the main function
enum Weather { SUNNY, SNOWY, CLOUDY, RAINY };

int main() {
    enum Weather weather = CLOUDY;
    
    switch (weather) {
        case SUNNY:
            printf("It's a sunny day. Put sunscreen.\n");
            break;
        case SNOWY:
            printf("Get your skis.\n");
            break;
        case RAINY:
        case CLOUDY:
            printf("Please bring an umbrella.\n");
            break;
        default:
            printf("Sorry, I am not familiar with such weather.\n");
            break;
    }
    
    return 0;
}
```
<details>
<summary><strong>ผลลัพธ์</strong></summary>
<pre><code> Please bring umbrella. </code></pre>
</details>

## ข้อดีของการใช้ Switch Case
คำสั่ง **switch case** เป็นรูปแบบที่เรียบง่ายของคำสั่ง if ที่ถูกซ้อน if-else กัน ปัญหาที่เกิดขึ้นจาก if-else ที่ถูกซ้อนกันคือมันสร้างความซับซ้อนในโปรแกรมเมื่อมีการเพิ่มเส้นทางหลายเส้นเพิ่มขึ้น คำสั่ง **switch case** จึงช่วยลดความซับซ้อนของโปรแกรมได้  

## เปรียบเทียบการใช้ Switch Case ในภาษา Dart และ ภาษาอื่นๆ
1. **การเรียกใช้งาน**: การใช้งาน switch case เริ่มต้นด้วยคำสั่ง switch และใช้คำสั่ง case เพื่อกำหนดเงื่อนไขที่เราต้องการเปรียบเทียบ
2. **ประเภทของเงื่อนไข**: ภาษา Dart และ ภาษา Java รองรับการใช้งาน switch case กับ strings และตัวเลข  ภาษา C รองรับ characters และ integers และใน ภาษา Python รองรับการใช้งาน match case
3. **Fall-Through** (กรณีถัดไปโดยไม่ต้องหยุด): ใน Dart และ C, คุณสามารถใช้งาน Fall-Through โดยไม่ต้องมี break ระหว่าง case ที่มีเงื่อนไขเป็นจริง ในขณะที่ใน Java และ Python คุณจำเป็นต้องระบุ break เพื่อหยุดการกระทำหรือย้ายไปยัง case ถัดไป
4. **Default Case** (ทำงานเมื่อไม่มีกรณีอื่นในคำสั่ง): ทุกภาษามี default หรือ else case ที่จะทำงานเมื่อไม่มีเงื่อนไขใดที่ตรงกัน

## **References**
https://dart-tutorial.com/conditions-and-loops/switch-case-in-dart/
<br>https://www.darttutorial.org/dart-tutorial/dart-switch/
<br>https://www.geeksforgeeks.org/python-match-case-statement/
<br>https://www.w3schools.com/c/c_switch.php
<br>https://www.w3schools.com/java/java_switch.asp
<br>https://www.w3schools.com/js/js_switch.asp
<br>https://www.javatpoint.com/dart-switch-case-statement
