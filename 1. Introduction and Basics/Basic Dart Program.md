# Basic Dart Program
นี่เป็นโปรแกรม dart ที่พิมพ์ hello world บนหน้าจอโปรแกรมเมอร์ส่วนใหญ่เขียนโปรแกรมhello world เป็นโปรแกรมแรกของพวกเขา

 ```dart
 void main() { 
   print("Hello World!"); 
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Hello World!
</pre>
</details>

อธิบายโปรแกรม dart พื้นฐาน
 * void main ( )เป็นจุดเริ่มต้นที่โปรแกรมจะเริ่มทํางาน
 * แต่ละโปรแกรมเริ่มต้นด้วยฟังก์ชันหลัก
 * วงเล็บ{ }ระบุจุดเริ่มต้นและจุดสิ้นสุดของบล็อกโค้ด
 * print ("hello world ! "); พิมพ์ hello world ! บนจอ.
 * แต่ละคําสั่งรหัสต้องสิ้นสุดด้วยเครื่องหมายอัลกอริทึม

## **โปรแกรม dart พื้นฐานสําหรับพิมพ์ชื่อ** ##
```dart
 void main()
{
    var name = "Wikorn";
    print(name);
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## **โปรแกรมdartพื้นฐานที่เชื่อมต่อตัวแปรอย่างน้อยหนึ่งตัว** ##
ที่นี่ $variableName ใช้สําหรับการเชื่อมต่อตัวแปร. กระบวนการเชื่อมต่อนี้ในdartเรียกว่าการแก้ไขสตริง
```dart
 void main(){
  var firstName = "Wikorn";
  var lastName = "Sangsuk";
  print("$firstName $lastName");
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## **โปรแกรม dart สําหรับการคํานวณพื้นฐาน** ##
ดําเนินการบวกการลบการคูณและการหารในdart
```dart
void main() {
int num1 = 20; //declaring number1
int num2 = 10; //declaring number2
  
// Calculation
int sum = num1 + num2;
int diff = num1 - num2;
int mul = num1 * num2;
double div = num1 / num2; // It is double because it outputs number with decimal.
  
// displaying the output
print("The sum is $sum");
print("The diff is $diff");
print("The mul is $mul");
print("The div is $div");
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

## **สร้างโครงการ dart สมบูรณ์** ##
การจัดการไฟล์เดียวเป็นสิ่งที่ดีแต่ถ้าโครงการของคุณมีขนาดใหญ่ขึ้นคุณต้องจัดการการกําหนดค่าแพคเกจและไฟล์สินทรัพย์ ดังนั้นการสร้างโครงการdartจะช่วยให้คุณสามารถจัดการทั้งหมดนี้ได้
```dart
 dart create <project_name>
```
ซึ่งจะสร้างโครงการdartที่เรียบง่ายด้วยโค้ดสําเร็จรูปบางอย่าง

## **ขั้นตอนในการสร้างโครงการdart** ##
 * เปิดตําแหน่งโฟลเดอร์ที่พร้อมคําสั่ ง / เทอร์ มินัล
 * พิมพ์dart create project_name ( ตัวอย่างเช่น dart create first_app )
 * พิมพ์ cd first _ app
 * รหัสประเภท เปิดโครงการโดยใช้โค้ดสตูดิโอภาพ
 * หากต้องการตรวจสอบไฟล์dartหลักให้ไปที่bin/first_app.dartและแก้ไขโค้ดของคุณ

## **เรียกใช้ โครงการ dart** ##
ขั้นแรกให้เปิดตําแหน่งโครงการบนคําสั่ง/เทอร์มินัลและใช้คําสั่งนี้เพื่อเรียกใช้โครงการ

```dart
 dart run
```
Dartเป็นภาษาเชิงวัตถุที่มีไวยากรณ์สไตล์cและสามารถคัดลอกเป็นจาวาสคริปต์ได้ สนับสนุนเครื่องมือช่วยในการเขียนโปรแกรมที่หลากหลายเช่นอินเทอร์เฟซคลาสคอลเลกชันทั่วไปและตัวเลือก
## **แปลงรหัส dart เป็น Javascript** ##
คําสั่ง | คําอธิบาย
------------ | -------------
dart รวบรวมแฟ้ม js ชื่อแฟ้ม.dart | คอมไพล์ dart ไปเป็นJavascript. คุณสามารถเรียกใช้ไฟล์นี้ด้วยNode.js

## **เปรียบเทียบกับภาษาC พื้นฐานสําหรับพิมพ์ชื่อ** ##

```
#include <stdio.h>

int main() {
    char name[] = "Wikorn";
    printf("%s\n", name);
    return 0;
}
```

ในภาษา C เราใช้ #include <stdio.h> เพื่อใช้งานฟังก์ชัน printf และใช้ #include <string.h> เพื่อใช้งานฟังก์ชัน strcpy ในการก๊อปปี้ข้อความ (string) จากตัวแปร name ใน Dart มายัง name ในภาษา C และใน printf เราใช้ %s เพื่อพิมพ์ข้อความแบบฟอร์แมต.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## **เปรียบเทียบกับภาษาC พื้นฐานที่เชื่อมต่อตัวแปรอย่างน้อยหนึ่งตัว** ##

```
#include <stdio.h>
#include <string.h>

int main() {
    char firstName[] = "Wikorn";
    char lastName[] = "Sangsuk";
    printf("%s %s\n", firstName, lastName);
    return 0;
}

```

ในภาษา C เราใช้ #include <stdio.h> เพื่อใช้งานฟังก์ชัน printf และ #include <string.h> เพื่อใช้งานฟังก์ชัน strcpy หรือการใส่ข้อความลงในตัวแปรแบบอาเรย์เพื่อใช้เก็บชื่อและนามสกุล และใน printf เราใช้ %s เพื่อพิมพ์ข้อความแบบฟอร์แมต.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## **เปรียบเทียบกับภาษาC สําหรับการคํานวณพื้นฐาน** ##
ดําเนินการบวกการลบการคูณและการหารในภาษาC

```
#include <stdio.h>

int main() {
    int num1 = 20; // declaring number1
    int num2 = 10; // declaring number2
    
    // Calculation
    int sum = num1 + num2;
    int diff = num1 - num2;
    int mul = num1 * num2;
    double div = (double)num1 / num2; // It is double because it outputs number with decimal.
    
    // displaying the output
    printf("The sum is %d\n", sum);
    printf("The diff is %d\n", diff);
    printf("The mul is %d\n", mul);
    printf("The div is %.2lf\n", div);
    
    return 0;
}

```

ในภาษา C เราใช้ #include <stdio.h> เพื่อใช้งานฟังก์ชัน printf และในการทำการหารค่าเลขจำนวนเต็ม num1 ด้วย num2 เราแปลงตัวอักษรที่ได้จากการหารเป็นตัวเลขทศนิยมโดยแปลง 
num1 เป็น double ก่อนแล้วทำการหารและแปลงผลลัพธ์เป็น double ด้วย เพื่อให้แสดงผลทศนิยมได้ถูกต้อง และใน printf ใน C เราใช้ %d สำหรับจำนวนเต็มและ %.2lf สำหรับจำนวนทศนิยมที่มี 2 ตำแหน่งหลังจุดทศนิยม.

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

## **เปรียบเทียบกับภาษา Java พื้นฐานสําหรับพิมพ์ชื่อ** ##

```
public class Main {
    public static void main(String[] args) {
        String name = "Wikorn";
        System.out.println(name);
    }
}

```

ในภาษา Java เราใช้ public static void main(String[] args) เป็นจุดเริ่มต้นของโปรแกรมแทน void main() ในภาษา Dart และเราใช้ String แทน var ในการประกาศตัวแปรชนิดข้อความ และใช้ System.out.println() แทน print() ในการพิมพ์ข้อความ.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## **เปรียบเทียบกับภาษา Java พื้นฐานที่เชื่อมต่อตัวแปรอย่างน้อยหนึ่งตัว** ##

```
public class Main {
    public static void main(String[] args) {
        String firstName = "Wikorn";
        String lastName = "Sangsuk";
        System.out.println(firstName + " " + lastName);
    }
}


```

ในภาษา Java เราใช้ public static void main(String[] args) เป็นจุดเริ่มต้นของโปรแกรมแทน void main() ในภาษา Dart และใช้ String แทน var 
ในการประกาศตัวแปรชนิดข้อความ และในการต่อข้อความเราใช้ + แทนการใช้ $ ในการแทรกค่าตัวแปร และเราใช้ System.out.println() เหมือนเดิมในการพิมพ์ข้อความ.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## **เปรียบเทียบกับภาษา Java สําหรับการคํานวณพื้นฐาน** ##
ดําเนินการบวกการลบการคูณและการหารในภาษาC

```
public class Main {
    public static void main(String[] args) {
        int num1 = 20; // declaring number1
        int num2 = 10; // declaring number2
        
        // Calculation
        int sum = num1 + num2;
        int diff = num1 - num2;
        int mul = num1 * num2;
        double div = (double) num1 / num2; // It is double because it outputs number with decimal.
        
        // displaying the output
        System.out.println("The sum is " + sum);
        System.out.println("The diff is " + diff);
        System.out.println("The mul is " + mul);
        System.out.println("The div is " + div);
    }
}

```

ในภาษา Java เราใช้ public static void main(String[] args) เป็นจุดเริ่มต้นของโปรแกรมแทน void main() ในภาษา Dart และเราใช้ int ในการประกาศตัวแปรชนิดจำนวนเต็ม และในการทำการหารค่าเลขจำนวนเต็ม 
num1 ด้วย num2 เราแปลง num1 เป็น (double) ก่อนแล้วทำการหารและแปลงผลลัพธ์เป็น double ด้วย เพื่อให้แสดงผลทศนิยมได้ถูกต้อง และเราใช้ System.out.println() แทน print() ในการพิมพ์ข้อความ.

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

## **เปรียบเทียบกับภาษา Python พื้นฐานสําหรับพิมพ์ชื่อ** ##

```
def main():
    name = "Wikorn"
    print(name)

if __name__ == "__main__":
    main()

```

ในภาษา Python เราใช้ def เพื่อประกาศฟังก์ชัน main() แทน void main() ในภาษา Dart และเราใช้ print() เหมือนเดิมในการพิมพ์ข้อความ และใน Python เราใช้ if __name__ == "__main__": เพื่อกำหนดว่าคำสั่งที่ตามหลังจะทำงานเมื่อไฟล์ถูกเรียกใช้โดยตรง.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## **เปรียบเทียบกับภาษา Python พื้นฐานที่เชื่อมต่อตัวแปรอย่างน้อยหนึ่งตัว** ##

```
def main():
    firstName = "Wikorn"
    lastName = "Sangsuk"
    print("{} {}".format(firstName, lastName))

if __name__ == "__main__":
    main()


```

ในภาษา Python เราใช้ def เพื่อประกาศฟังก์ชัน main() แทน void main() ในภาษา Dart และในการต่อข้อความเราใช้ .format() หรือใน Python 3.6 และเวอร์ชันใหม่กว่าเราสามารถใช้ f-strings 
เพื่อแทรกตัวแปรลงในสตริงได้ โดยตัวอย่างด้านบนเลือกใช้ .format() และใน Python เราใช้ if __name__ == "__main__": เพื่อกำหนดว่าคำสั่งที่ตามหลังจะทำงานเมื่อไฟล์ถูกเรียกใช้โดยตรง.

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## **เปรียบเทียบกับภาษา Python สําหรับการคํานวณพื้นฐาน** ##
ดําเนินการบวกการลบการคูณและการหารในภาษาC

```
def main():
    num1 = 20  # declaring number1
    num2 = 10  # declaring number2
    
    # Calculation
    sum = num1 + num2
    diff = num1 - num2
    mul = num1 * num2
    div = num1 / num2  # It is double because it outputs number with decimal.
    
    # displaying the output
    print(f"The sum is {sum}")
    print(f"The diff is {diff}")
    print(f"The mul is {mul}")
    print(f"The div is {div}")

if __name__ == "__main__":
    main()

```

ในภาษา Python เราใช้ def เพื่อประกาศฟังก์ชัน main() แทน void main() ในภาษา Dart และใช้ # ในการคอมเมนต์เป็นหมายเหตุ และในการต่อข้อความใช้ + แทนการใช้ $ ในการแทรกค่าตัวแปร และเราใช้ print() 
เหมือนเดิมในการพิมพ์ข้อความ แต่เพิ่ม f ด้านหน้าสตริงและใช้ {} เพื่อแทรกตัวแปร. สุดท้ายใน Python เราใช้ if __name__ == "__main__": เพื่อกำหนดว่าคำสั่งที่ตามหลังจะทำงานเมื่อไฟล์ถูกเรียกใช้โดยตรง.

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

# Reference

https://www.javatpoint.com/dart-first-program

https://dart-tutorial.com/introduction-and-basics/basic-dart-program/

https://www.tutorialspoint.com/dart_programming/index.htm

https://www.tutorialspoint.com/dart_programming/dart_programming_overview.htm
