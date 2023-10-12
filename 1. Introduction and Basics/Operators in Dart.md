# Operators in Dart
 -  ตัวดำเนินการใช้ในการดำเนินการทางคณิตศาสตร์ เเละดำเนินการตรรกะกับตัวเเปร การดำเนินการเเต่ละครั้งใน Dart จะใช้สัญลักษณ์ที่เรียกว่า Operator เพื่่อเเสดงการดำเนินการที่จะทำ
# สิ่งที่ควรรู้
 - Operands คือ ตัวถูกดำเนินการ เช่น ตัวเลขหรือ ตัวเเปร
 - Operators คือ ตัวดำเนินการ ที่ใช้ในการดำเนินการทางคณิตศาสตร์ เพื่อให้ได้ผลลัพธ์
 # ประเภทของ Operators
 - Arithmetic Operators
 - Increment and Decrement Operators
 - Assignment Operators
 - Logical Operators
 - Type Test Operators
 - Bitwise Operators
# Arithmetic Operators
## ตัวดำเนินการทางคณิตศาสตร์ คือตัวดำเนินการที่ใช้เพื่อกระทำการดำเนินการทางคณิตศาสตร์ระหว่างตัวแปรหรือค่าคงที่ เช่น การบวก การลบ การคูณ และการหาร
## ในภาษา C เเละ Java จะมีตัวดำเนินการเหมือนกันดังนี้
- "+" เรียกว่า การบวก สำหรับการรวมตัวถูกดำเนินการ เช่น C = A + B
- "-" เรียกว่า การลบ สำหรับการลบตัวดำเนินการ เช่น C = A - B
- "*" เรียกว่า การคูณ สำหรับการคูณตัวดำเนินการ เช่น C = A * B
- "/" เรียกว่า การหาร สำหรับการหารตัวดำเนินการ เช่น C = A / B
- "%" เรียกว่า การหารเอาเศษ สำหรับการหารโดยจะได้ผลลัพธ์เป็นจำนวนเศษ เช่น C = A % B
## ตัวอย่างของภาษา C
```dart
#include <stdio.h>

int main()
{
    int a = 5;
    int b = 10;
    printf("a + b = %d\n", a + b);
    printf("a - b = %d\n", a - b);
    printf("a * b = %d\n", a * b);
    printf("a / b = %d\n", a / b);
    printf("a % b = %d\n", a % b);
    return 0;
}
```
## คำตอบที่ได้
```dart
a + b = 15
a - b = -5
a * b = 50
a / b = 0
a % b = 5
```
## ตัวอย่างของภาษา Java
```dart
public class ArithmeticOperator {
    public static void main (String[] atgs) {
        int a = 5;
        int b = 3;

        System.out.println(a + " + " + b + " = " + (a + b));
        System.out.println(a + " - " + b + " = " + (a - b));
        System.out.println(a + " * " + b + " = " + (a * b));
        System.out.println(a + " / " + b + " = " + (a / b));
        System.out.println(a + " % " + b + " = " + (a % b));
    }
}
```
## คำตอบที่ได้
```dart
5 + 3 = 8
5 - 3 = 2
5 * 3 = 15
5 / 3 = 1
5 % 3 = 2
```
## ใน Dart จะมีตัวดำเนินการเพิ่มขึ้นมาอีกสองตัวดังนี้
- -expr เรียกว่า Unary minus สำหรับการกลับค่าเป็นค่าตรงข้าม เช่น  -(2) => 2)
- ~/ เรียกว่า Integer Division สำหรับการหารโดยจะได้ผลลัพธ์เป็น integer
## ตัวอย่างของภาษา Dart
```dart
void main() {
 // declaring two numbers 
 int num1=10;
 int num2=3;
 
 // performing arithmetic calculation
 int sum=num1+num2;       // การบวก
 int diff=num1-num2;      // การลบ
 int unaryMinus = -num1;    // unary minus  
 int mul=num1*num2;       // การคูณ
 double div=num1/num2;    // การหาร
 int div2 =num1~/num2;     // การหารเเบบได้ผลลัพธ์เป็น integer
 int mod=num1%num2;       // การหารเอาเศษ
 
//Printing info 
 print("The addition is $sum.");
 print("The subtraction is $diff.");
 print("The unary minus is $unaryMinus.");
 print("The multiplication is $mul.");
 print("The division is $div.");
 print("The integer division is $div2.");
 print("The modulus is $mod."); 
}
```
## คำตอบที่ได้
```dart
The addition is 13.
The subtraction is 7.
The unary minus is -10.
The multiplication is 30.
The division is 3.3333333333333335. // เมื่อหารเเบบปรกติจะได้ผลลัพธ์เป็น double
The integer division is 3.   // หารเเบบ Integer Divisionได้ผลลัพธ์เป็น integer
The modulus is 1.
```
## ใน Python จะเพิ่มOperatorขึ้นมาอีก 2 ตัว คือ
- "//"	เรียกว่า Division and floor ตัวอย่าง	a // b คือ การแบบการหารที่ได้ผลลัพธ์เป็นจำนวนเต็ม
- "**"	เรียกว่า Power	ตัวอย่าง a ** b คือ การหาเลขยกกำลัง
## ตัวอย่างของภาษา Python
```dart
a = 5
b = 3
print("a + b = ", a + b)
print("a - b = ", a - b)
print("a * b = ", a * b)
print("a / b = ", a / b)
print("a // b = ", a // b) # floor number to integer
print("a % b = ", a % b)   # get division remainder
print("a ** b = ", a ** b) # power
```
## คำตอบที่ได้
```dart
a + b =  8
a - b =  2
a * b =  15
a / b =  1.6666666666666667
a // b =  1
a % b =  2
a ** b =  125
```
# Increment and Decrement Operators
## ตัวดำเนินการเพิ่มและลดค่า คือตัวดำเนินการที่ใช้เพื่อบวกหรือลบค่าออกจากตัวแปรทีละ 1 โดยการเพิ่มเครื่องหมาย ++ หรือ –- โดยถ้าใส่ข้างหน้าจะทำการเพิ่มค่าของตัวแปรขึ้นทันทีก่อนที่จะประมวลผลคำสั่งนั้น ส่วนถ้าใส่ไว้ข้างหลังจะเพิ่มค่าหลังจากที่ประมวลผลคำสั่งนั้นเสร็จสิ้นแล้ว
- ++var เรียกว่า Pre Increment คือการ เพิ่ม Value ไป 1 โดย var = var + 1 ค่านิพจน์คือ Var+1
- --var เรียกว่า Pre Decrement คือการ ลดค่า Value ไป 1 โดย var = var - 1 ค่านิพจน์คือ Var-1
- var++ เรียกว่า Post Increment คือการ เพิ่มค่า value ไป 1 โดย var = var ค่านิพจน์คือ var
- var-- เรียกว่า Post Decrement คือการ ลดค่า value ไป 1 โดย var = var ค่านิพจน์คือ var
  ## ตัวอย่างของภาษา C
```dart
#include <stdio.h>

int main()
{
    int a = 1;
    int b = 10;
    a++;
    b--;
    printf("a=%d, b=%d", a, b);
    return 0;
}
```
## คำตอบที่ได้
```dart
a=2, b=9
```
## ตัวอย่างของภาษา Java
```dart
public class IncrementDecrement {
    public static void main (String[] atgs) {
        int i = 5;
        int j = 5;
        System.out.println("++i = " + (++i));
        System.out.println("j++ = " + (j++));
        // At this line either i and j are 6
    }
}
```
## คำตอบที่ได้
```dart
++i = 6
j++ = 5
```
## ตัวอย่างของภาษา Dart
```dart
void main() {
// declaring two numbers 
 int num1=0;
 int num2=0;
 
// performing increment / decrement operator  

// pre increment   
num2 = ++num1;
print("The value of num2 is $num2");

// reset value to 0 
num1 = 0;
num2 = 0;

// post increment  
num2 =  num1++;
print("The value of num2 is $num2");  
  
}
```
## คำตอบที่ได้
```dart
The value of num2 is 1
The value of num2 is 0
```
# Relational Operators
## ตัวดำเนินการเชิงสัมพันธ์เรียกอีกอย่างว่าตัวดำเนินการเปรียบเทียบ ใช้ในการเปรียบเทียบ เหมือนกันทั้ง ภาษา C,Java เเละ Dart
- ">" เครื่องหมาย มากกว่า ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการทางซ้ายมากกว่าค่าของตัวถูกดำเนินการทางขวาหรือไม่ ถ้าใช่ เงื่อนไขจะกลายเป็นจริง เช่น (A > B) ไม่เป็นความจริง
- "<" เครื่องหมาย น้อยกว่า ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการทางซ้ายน้อยกว่าค่าของตัวถูกดำเนินการทางขวาหรือไม่ ถ้าใช่ เงื่อนไขจะกลายเป็นจริง เช่น (A < B) เป็นจริง
- ">=" เครื่องหมาย มากกว่าหรือเท่ากับ ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการทางซ้ายมากกว่าหรือเท่ากับค่าของตัวถูกดำเนินการทางขวาหรือไม่ ถ้าใช่ เงื่อนไขจะกลายเป็นจริง เช่น (A >= B) ไม่เป็นความจริง
- "<=" เครื่องหมาย น้อยกว่าหรือเท่ากับ ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการทางซ้ายน้อยกว่าหรือเท่ากับค่าของตัวถูกดำเนินการทางขวาหรือไม่ ถ้าใช่ เงื่อนไขจะกลายเป็นจริง เช่น (A <= B) เป็นจริง
- "==" เครื่องหมาย เปรียบเทียบ ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการสองตัวเท่ากันหรือไม่ ถ้าใช่ เงื่อนไขจะกลายเป็นจริง เช่น (A == B) ไม่เป็นความจริง
- "!=" เครื่องหมาย ไม่เท่ากับ ใช้ในการตรวจสอบว่าค่าของตัวถูกดำเนินการสองตัวเท่ากันหรือไม่ หากค่าไม่เท่ากัน เงื่อนไขจะกลายเป็นจริง เช่น (A != B) เป็นจริง
## ตัวอย่างของภาษา C
```dart
#include <stdio.h>

int main()
{
    int a = 5;
    int b = 10;

    if (a == b)
    {
        printf ("a and b are equal");
    }
    else
    {
        printf ("a and b are not equal");
    }

    return 0;
}
```
## คำตอบที่ได้
```dart
a and b are not equal
```
## ตัวอย่างของภาษา Java
```dart
public class ComparisonOperators {
    public static void main (String[] atgs) {
        int a = 5;
        int b = 8;

        System.out.println(a + " equal to " + b  + " -> " + (a == b));
        System.out.println(a + " not equal to " + b  + " -> " + (a != b));
        System.out.println(a + " less than " + b  + " -> " + (a < b));
        System.out.println(a + " more than " + b  + " -> " + (a > b));
        System.out.println(a + " less than or equal " + b  + " -> " + (a <= b));
        System.out.println(a + " more than or equal " + b  + " -> " + (a >= b));
    }
}
```
## คำตอบที่ได้
```dart
5 equal to 8 -> false
5 not equal to 8 -> true
5 less than 8 -> true
5 more than 8 -> false
5 less than or equal 8 -> true
5 more than or equal 8 -> false
# ตัวอย่างของภาษา Dart
```
## ตัวอย่างของภาษา Dart
```dart
void main() {
  
 int num1=10;
 int num2=5;
 //printing info
 print(num1==num2); 
 print(num1<num2);
 print(num1>num2);
 print(num1<=num2);
 print(num1>=num2);
}
```
## คำตอบที่ได้
```dart
false
false
true
false
true
```
## สำหรับภาษา Python จะเพิ่มตัวดำเนินการ is และ is not จะเกี่ยวข้องกับ การเขียนโปรแกรมเชิงวัตถุ ซึ่งเป็นรูปแบบการเขียนโปรแกรมขั้นสูง มันใช้สำหรับตรวจสอบความเท่ากันของออบเจ็ค โดยออบเจ็คเหล่านั้นจะต้องอ้างถึงที่อยู่ตำแหน่งเดียวกันในหน่วยความจำ (Reference type)
# Logical Operators
## ใช้ในการเปรียบเทียบค่าต่างๆ
- "&&" เรียกว่า เเละ จะให้ผลลัพธ์เป็นจริงเมื่อเงื่อนไขทั้งสองเป็นจริง แต่ถ้าเงื่อนไขใดเป็นเท็จ หรือทั้งสองเงื่อนไขเป็นเท็จจะทำให้ผลลัพธ์เป็นเท็จ เช่น (A && B) เป็นเท็จ
- "||" เรียกว่า หรือ จะให้ผลลัพธ์เป็นจริงเมื่อเงื่อนไขใดเงื่อนไขหนึ่งเป็นจริง หรือเป็นจริงทั้งสองเงื่อนไข แต่ถ้าเป็นเท็จทั้งสองเงื่อนไขจะทำให้ผลลัพธ์เป็นเท็จ เช่น (A || B) เป็นจริง
- "!" เรียกว่า ไม่ใช่ จะให้ผลลัพธ์เป็นจริงเมื่อเงื่อนไขหลัง not เป็นเท็จ แต่ถ้าเงื่อนไขหลัง not เป็นจริงจะทำให้ผลลัพธ์เป็นเท็จ  เช่น !(A && B) เป็นจริง
## ตัวอย่างของภาษา C
```dart
#include <stdio.h>

int main()
{
    int a = 10;
    bool b = 1;
    bool c = 0;

    // using "not" operator
    if (!(a == 10))
        printf("a is not equal to 10.\n");
    else
        printf("a is equal to 10.\n");

    // using "and" operator
    if (b && c)
        printf("True.\n");
    else
        printf("False.\n");

    // using "or" operator
    if (b || c)
        printf("True.\n");
    else
        printf("False.\n");

    return 0;
}
```
## คำตอบที่ได้
```dart
a is equal to 10.
False.
True.
```
## ตัวอย่างของภาษา Java
```dart
public class LogicalOperators {
    public static void main (String[] atgs) {

        int score = 8;
        int level = 4;

        if (score >= 10 && level >= 5) {
            System.out.println("You get a gold badge.");
        }

        if (score >= 10 || level >= 3) {
            System.out.println("You get a bronze badge.");
        }
    }
}
```
## คำตอบที่ได้
```dart
You get a bronze badge
```
## ตัวอย่างของภาษา Dart
```dart
void main(){
  int userid = 123;
    int userpin = 456;

    // Printing Info
    print((userid == 123) && (userpin== 456)); // print true
    print((userid == 1213) && (userpin== 456)); // print false.
    print((userid == 123) || (userpin== 456)); // print true.
    print((userid == 1213) || (userpin== 456)); // print true
    print((userid == 123) != (userpin== 456));//print false

}
```
## คำตอบที่ได้
```dart
true
false
true
true
false
```
## ตัวอย่างของภาษา Python
```dart
print('Log in page')
username = input('Username: ')
password = input('Password: ')

if (username == 'mateo' and password == '3456'):
    print('Welcome Mateo, you\'ve logged in.')
else:
    print('Invalid username or password.')
```
## คำตอบที่ได้
```dart
Log in page
Username: mateo
Password: 3456
Welcome Mateo, you've logged in.
```
# Type Test Operators
## ใน Dart Type Test Operators ใช้ในการตรวจสอบชนิดของตัวแปรหรือข้อมูล มีประโยชน์สำหรับการตรวจสอบประเภทขณะรันไทม์
- is ใช้เช็คว่าเป็นชนิดข้อมูลนั้นหรือไม่
- is! ใช้เช็คว่าไม่ใช่ชนิดข้อมูลนั้น
## ตัวอย่างของภาษา Dart
```dart
void main() {
  String value1 = "Dart Tutorial";
  int age = 10;
  
  print(value1 is String);
  print(age is !int);
}
```
## คำตอบที่ได้
```dart
true
false
```
## สำหรับ String ต้องใส่ค่าให้ตัวเเปรก่อน (ไม่เป็น null) จึงจะสามารถตรวจสอบได้อย่างถูกต้อง
## ตัวอย่างของภาษา Dart
```dart
String a;
print(a is String);		// false
String b = 'aaa';
print(b is String);		// true
```
# Bitwise operators
## คือ ตัวดำเนินการแบบบิต เป็นตัวดำเนินการที่ใช้กับชนิดข้อมูลเลขจำนวนเต็ม (integer) เท่านั้น โดยจะแปลงเป็นเลขฐาน 2 (8-bit) ก่อนดำเนินการ หลังจากนั้น จะแปลงค่ากลับเป็นฐาน 10 กลับมา 
## ประเภทตัวดำเนินการระดับบิต
- "&"	Bitwise AND
- "|"	Bitwise inclusive OR
- "^" Bitwise exclusive OR
- "~" bit inversion
- "<<"	Shift bits left
- ">>"	Shift bits right
## ตัวอย่างของภาษา C
```dart
#include <stdio.h>

int main()
{
    int a = 2; // 00000010
    int b = 5; // 00000101
    printf("a & b = %d\n", a & b);    // 00000000 = 0
    printf("a & b = %d\n", a | b);    // 00000111 = 7
    printf("~a = %d\n", ~a);          // 11111101 = -1
    printf("a >> 1 = %d\n", a >> 1);  // 00000001 = 1
    printf("a << 1 = %d\n", a << 1);  // 00000100 = 8
    return 0;
}
```
## ในตัวอย่าง เป็นโปรแกรมในการใช้งานตัวดำเนินการระดับบิตกับการจัดการข้อมูลประเภท Integer เราได้ประกาศตัวแปร a และ b และได้คอมเมนต์ค่าของ Binary ที่ถูกเก็บไว้ในหน่วยความจำ การทำงานของตัวดำเนินการ & และ | นั้นทำงานกับคู่ของแต่ละบิตของตัวแปรทั้งสอง ส่วนอีกสามตัวดำเนินการที่เหลือนั้นกระทำกับตัวแปรเดียว ในตัวดำเนินการ ~ นั้นเป็นการกลับบิต และสำหรับตัวดำเนินการ Bit shift นั้นเมื่อเลื่อนบิตไปทางซ้ายจะทำให้ค่าเพิ่มขึ้นสองเท่า และเมื่อเลื่อนบิตไปทางขวาก็จะทำให้ค่าลดลงสองเท่า

## คำตอบที่ได้
```dart
a & b = 0
a & b = 7
~a = -3
a >> 1 = 1
a << 1 = 4
```
## ตัวอย่างของภาษา Java
```dart
public class BitwiseOperators {
    public static void main (String[] atgs) {
        int a = 5;
        int b = 3;

        System.out.println(a + " & " + b + " = " + (a & b));
        System.out.println(a + " | " + b + " = " + (a | b));   
        System.out.println("~" + a + " = " + (~a));    
        System.out.println(a + " << 1 = " + (a << 1));
    }
}
```
## คำตอบที่ได้
```dart
5 & 3 = 1
5 | 3 = 7
~5 = -6
5 << 1 = 10
```
## ตัวอย่างของภาษา Dart
## & (AND) เป็นการหาเลข 1 ที่ตำแหน่ง(บิด)เดียวกัน มีเงื่อนไขดังนี้
ถ้า 1&1 เป็น 1, ถ้า 1&0 เป็น 0, ถ้า 0&1 เป็น 0, ถ้า 0&0 เป็น 0
```dart
5 & 3  มีค่าเท่ากับ 1  เนื่องจาก
5 แปลงเป็นเลขฐานสองได้เป็น		0000 0101
3 แปลงเป็นเลขฐานสองได้เป็น		0000 0011
ผลลัพธ์เมื่อ AND กันแต่ละบิต ได้	0000 0001 มีค่าเท่ากับ 1 (เลขฐานสิบ)
```
## | (Or) เป็นการตัวเลข 1 อย่างน้อย 1 ตามตำแหน่งเข้าด้วยกัน มีเงื่อนไขดังนี้
ถ้า 1|1 เป็น 1, ถ้า 1|0 เป็น 1, ถ้า 0|1 เป็น 1, ถ้า 0|0 เป็น 0
```dart
5 | 3  มีค่าเท่ากับ 7  เนื่องจาก
5 แปลงเป็นเลขฐานสองได้เป็น		0000 0101
3 แปลงเป็นเลขฐานสองได้เป็น		0000 0011
ผลลัพธ์เมื่อ OR กันแต่ละบิต ได้	0000 0111 มีค่าเท่ากับ 7 (เลขฐานสิบ)
```
## ^ (XOR) เป็นการตัวเลข 0 อย่างน้อย 1 ตามตำแหน่งเข้าด้วยกัน มีเงื่อนไขดังนี้
ถ้า 1^1 เป็น 0, ถ้า 1^0 เป็น 1, ถ้า 0^1 เป็น 1, ถ้า 0^0 เป็น 1
```dart
5 | 3  มีค่าเท่ากับ 6  เนื่องจาก
5 แปลงเป็นเลขฐานสองได้เป็น		0000 0101
3 แปลงเป็นเลขฐานสองได้เป็น		0000 0011
ผลลัพธ์เมื่อ XOR กันแต่ละบิต ได้	0000 0110 มีค่าเท่ากับ 6 (เลขฐานสิบ)
```
## ~ (NOT) เป็นการกลับค่าในแต่ละตำแหน่ง จาก 1 เป็น 0 และจาก 0 เป็น 1
```dart
~3  มีค่าเท่ากับ 4294967292  เนื่องจาก
3 แปลงเป็นเลขฐานสองได้เป็น		0000 0011
3 จะถูกกลับค่าได้เป็น		1111 1100 มีค่าเท่ากับ 4294967292 (เลขฐานสิบ)
```
## << (Left shift) หมายถึงการเลื่อนบิตไปทางซ้ายมือ เช่น
```dart
5<<2 มีค่าเท่ากับ 20 เนื่องจาก
5 แปลงเป็นเลขฐานสองได้เป็น       				0000 0101
เลื่อนบิตซ้ายสุดของตัวตั้งไปเป็นจำนวน 2 บิต ได้เป็น  		00 | 0001 0100
ผลลัพธ์ของการเลื่อนบิตทางขวาของ 5<<2 คือ 			0001 0100 มีค่าเท่ากับ 20
```
## >> (Right shift) หมายถึงการเลื่อนบิตไปทางขวามือ เช่น
```dart
5>>2 มีค่าเท่ากับ 1 เนื่องจาก
5 แปลงเป็นเลขฐานสองได้เป็น       				0000 0101
เลื่อนบิตขวาสุดของตัวตั้งไปเป็นจำนวน 2 บิต ได้เป็น  		0000 0001 | 01
ผลลัพธ์ของการเลื่อนบิตทางขวาของ 5>>2 คือ 			0000 0001 มีค่าเท่ากับ 1
(คือการตัดเลขทางขวาสุด แล้วเอา 0 มาต่อทางซ้ายสุดให้ครบ 8 bit นั่นแหละ)
```
# อ้างอิง
- https://dart-tutorial.com/introduction-and-basics/operators-in-dart/
- https://lungmaker.com/c-programming/operators-%E0%B8%95%E0%B8%B1%E0%B8%A7%E0%B8%94%E0%B8%B3%E0%B9%80%E0%B8%99%E0%B8%B4%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B8%A3-%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2-c/
- http://marcuscode.com/lang/c/operators
- https://toupawa.com/learn-dart-from-zero-to-standard/
- https://blog.intception.me/dev/flutter/dart-part-2.html#equality-and-relational-operators
- http://marcuscode.com/lang/python/operators
# File การนำเสนอ
[Operators in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12881234/Operators.in.Dart.pdf)
[Operators in Dart (3).pdf](https://github.com/soonklang/dart-tutorial/files/12882763/Operators.in.Dart.3.pdf)

# Video นำเสนอ
https://youtu.be/YUftb_KjFKE

