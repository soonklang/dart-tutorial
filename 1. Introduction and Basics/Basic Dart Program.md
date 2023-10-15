# Basic Dart Program

Dart เป็นภาษาที่เอาไว้สำหรับสร้างแอพพลิเคชันบนเเพลตฟอร์มที่หลากหลายโดยได้ทั้ง mobie,destop,server เเละ web 
ภาษา Dart สามารถใช้ร่วมกับ Flutter ที่เป็นเครื่องมือช่วยสร้าง UI ของ Google ใช้ได้ทั้งกับ Android และ iOS

โค้ดตัวอย่างโปรแกรมแสดงข้อความ “Hello World” ในภาษา Dart 

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

โปรแกรม dart พื้นฐาน
 * void main ( ) เป็นจุดเริ่มต้นที่โปรแกรมจะเริ่มทํางาน
 * แต่ละโปรแกรมเริ่มต้นด้วยฟังก์ชันหลัก
 * วงเล็บเปิดปิด หรือ ปีกกา{ } ระบุจุดเริ่มต้นและจุดสิ้นสุดของบล็อกโค้ด
 * print ("hello world ! "); พิมพ์ hello world ! บนจอ.
 * แต่ละคําสั่งรหัสต้องสิ้นสุดด้วยเครื่องหมาย semicolon

## ภาษา Dart
## พื้นฐานสําหรับPrint ข้อความ
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

## พื้นฐานเชื่อมตัวแปรอย่างน้อยหนึ่งตัว
$variableName ใช้สําหรับการเชื่อมตัวแปร. การเชื่อมต่อนี้ในdartเรียกว่าการแก้ไขสตริง
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

## ตัวดำเนินการทางคณิตศาสตร์
ดําเนินการบวกการลบการคูณและการหารในdart
```dart
void main() {
int num1 = 20; 
int num2 = 10; 
  
// Calculation
int sum = num1 + num2;
int diff = num1 - num2;
int mul = num1 * num2;  // * คือ เครื่องหมายคูณ
double div = num1 / num2; // / คือ เครื่องหมายหาร
  
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

## สร้างโครงการ dart สมบูรณ์
การจัดการไฟล์เดียวเป็นสิ่งที่ดีแต่ถ้าโครงการของคุณมีขนาดใหญ่ขึ้นคุณต้องจัดการการกําหนดค่าแพคเกจและไฟล์สินทรัพย์ ดังนั้นการสร้างโครงการdartจะช่วยให้คุณสามารถจัดการทั้งหมดนี้ได้
```dart
 dart create <project_name>
```
สร้างโครงการ dart ที่เรียบง่ายด้วยโค้ดสําเร็จรูปบางอย่าง

## ขั้นตอนในการสร้างโครงการdart
 * เปิดตําแหน่งโฟลเดอร์ที่พร้อมprompt/terminal.
 * Type dart create project_name ( ตัวอย่างเช่น dart create first_app )
 * Type cd first_app
 * Type code . เปิดโครงการโดยใช้โค้ด studio code
 * หากต้องการตรวจสอบไฟล์ dart หลักให้ไปที่ bin/first_app.dart และแก้ไขโค้ดของคุณ

## เรียกใช้โครงการ dart

ขั้นแรกให้เปิดตําแหน่งโครงการบน command/terminal และใช้คําสั่งนี้เพื่อเรียกใช้โครงการ

```dart
 dart run
```
Dartเป็นภาษาเชิงวัตถุที่มีไวยากรณ์สไตล์c และสามารถคัดลอกเป็นจาวาสคริปต์ได้ สนับสนุนเครื่องมือช่วยในการเขียนโปรแกรมที่หลากหลายเช่นอินเทอร์เฟซคลาสคอลเลกชันทั่วไปและตัวเลือก
## Convert Dart Code To Javascript
Command | Description
------------ | -------------
dart compile js filename.dart | Compile dart to javascript. You can run this file with Node.js.

## เปรียบเทียบขนิดข้อมูลกับภาษาอื่นๆ

   ## ภาษา C

## ชนิดของข้อมูลในภาษา C

ในภาษาC แบ่งประเภทของข้อมูลออกได้เป็น 6 ประเภทด้วยกันคือ

* int ชนิดข้อมูลเลขจำนวนเต็ม
* float ชนิดข้อมูลเลขทศนิยม
* octal ชนิดข้อมูลเลขฐานแปด
* hex ชนิดข้อมูลเลขฐานสิบหก
* char ข้อมูลชนิดตัวอักขระ 
* string ข้อมูลชนิดตัวอักษร
  
## พื้นฐานสําหรับPrint ข้อความ

```
#include <stdio.h>

int main() {
    char name[] = "Wikorn";
    printf("%s\n", name);
    return 0;
}
```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## พื้นฐานเชื่อมตัวแปรอย่างน้อยหนึ่งตัว

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

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## ตัวดำเนินการทางคณิตศาสตร์
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

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

   ## ภาษา Java
   
## ชนิดของข้อมูลในภาษา Java

ในภาษา Java แบ่งประเภทของข้อมูลออกได้เป็น 4 ประเภทด้วยกันคือ

* ข้อมูลตรรกะ (logical) คือ boolean
* ข้อมูลอักขระ (textual) คือ char
* ข้อมูลตัวเลขจำนวนเต็ม (integer) คือ byte, short, int และ long
* ข้อมูลตัวเลขทศนิยม (floating point) คือ float และ double

## พื้นฐานสําหรับPrint ข้อความ

```
public class Main {
    public static void main(String[] args) {
        String name = "Wikorn";
        System.out.println(name);
    }
}

```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## พื้นฐานเชื่อมตัวแปรอย่างน้อยหนึ่งตัว

```
public class Main {
    public static void main(String[] args) {
        String firstName = "Wikorn";
        String lastName = "Sangsuk";
        System.out.println(firstName + " " + lastName);
    }
}


```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## ตัวดำเนินการทางคณิตศาสตร์
ดําเนินการบวกการลบการคูณและการหารในภาษา Java

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

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

   ## ภาษา Python
   
## ชนิดของข้อมูลในภาษา Python

ในภาษา Python แบ่งประเภทของข้อมูลออกได้เป็น 6 ประเภทด้วยกันคือ

* ตัวเลข (Numbers)
* สายอักขระ (String)
* ลิสต์ (List)
* ทูเพิล (Tuple)
* ดิกชันนารี (Dictionary)
* เซต (Set)

## พื้นฐานสําหรับPrint ข้อความ
```
def main():
    name = "Wikorn"
    print(name)

if __name__ == "__main__":
    main()

```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn
</pre>
</details>

## พื้นฐานเชื่อมตัวแปรอย่างน้อยหนึ่งตัว

```
def main():
    firstName = "Wikorn"
    lastName = "Sangsuk"
    print("{} {}".format(firstName, lastName))

if __name__ == "__main__":
    main()


```

<details open>
<summary><b>Output</b></summary>
 <pre>
Wikorn Sangsuk
</pre>
</details>

## ตัวดำเนินการทางคณิตศาสตร์
ดําเนินการบวกการลบการคูณและการหารในภาษา Python

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

<details open>
<summary><b>Output</b></summary>
 <pre>
The sum is 30
The diff is 10
The mul is 200
The div is 2.0
</pre>
</details>

## Reference

https://www.javatpoint.com/dart-first-program

https://dart-tutorial.com/introduction-and-basics/basic-dart-program/

https://www.tutorialspoint.com/dart_programming/index.htm

https://www.tutorialspoint.com/dart_programming/dart_programming_overview.htm

## Slides & Clip
link vdo : https://youtu.be/1C6uwTi5MbU

pptx file : [Basic Dart Program.pptx](https://github.com/soonklang/dart-tutorial/files/12908585/Basic.Dart.Program.pptx)



