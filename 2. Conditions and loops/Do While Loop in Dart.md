# Do While Loop in Dart

Do while loop รันบล็อกของคำสั่งก่อน จากนั้นจะทดสอบเงื่อนไข หากเงื่อนไขคืนค่าเป็นจริง การวนซ้ำจะทำต่อไป มันคล้ายกับ while loop แต่ข้อแตกต่างเพียงข้อเดียว ใน Do While Loop บล็อกของคำสั่งภายในตัว body ของ loop จะทำงานอย่างน้อยหนึ่งครั้ง

 ```dart
do{
    statement1;
    statement2;
    .
    .
    .
    statementN;
}while(condition);
```

* ขั้นแรก เริ่มรันคำสั่ง และสุดท้าย จะทำการทดสอบเงื่อนไข
* ถ้าเงื่อนไขเป็นจริง โค้ดภายใน {} จะถูกทำงาน
* เงื่อนไขจะถูกตรวจสอบเรื่อยๆ จนกว่าเงื่อนไขจะเป็นเท็จ
* ถ้าเงื่อนไขเป็นเท็จเมื่อไหร่ การทำงานของ Loop จะหยุดทำงานทันที

> **Note:  ใน Do-While loop คำสั่งจะถูกดำเนินการอย่างน้อยหนึ่งครั้ง แม้ว่าเงื่อนไขจะเป็นเท็จ เป็นเพราะว่าคำสั่งถูกดำเนินการก่อนที่จะตรวจสอบเงื่อนไข**


# Do While Loop Flowchart

![dart-for-loop](https://static.javatpoint.com/tutorial/dart/images/dart-do-while-loop.png)


# ***ตัวอย่างที่  1 : พิมพ์ 1 - 10 โดยใช้ Do While Loop***

**ตัวอย่างภาษา DART**
 ```dart
void main() {
  int i = 1;
  do {
    print(i);
    i++;
  } while (i <= 10);
}
```
***Output***
 ```dart
1
2
3
4
5
6
7
8
9
10
```

**ตัวอย่างภาษา JAVA**
 ```Java
public class Main {    
public static void main(String[] args) {    
    int i=1;    
    do{    
        System.out.println(i);    
    i++;    
    }while(i<=10);    
}    
}    
 ```

**ตัวอย่างภาษา C**
 ```C
#include <stdio.h>
int main () {

   int i = 1;

   do {
      printf("%d\n", i);
      i++;
   }while( i <= 10 );
 
   return 0;
}
 ```

# ***ตัวอย่างที่  2 : พิมพ์ 10 - 1 โดยใช้ Do While Loop***

**ตัวอย่างภาษา DART**
 ```dart
void main() {
  int i = 10;
  do {
    print(i);
    i--;
  } while (i >=1);
}
```
***Output***
 ```dart
10
9
8
7
6
5
4
3
2
1
```

**ตัวอย่างภาษา JAVA**
 ```Java
public class Main {    
public static void main(String[] args) {    
    int i=10;    
    do{    
        System.out.println(i);    
    i--;    
    }while(i>=1);    
}    
}    
 ```

**ตัวอย่างภาษา C**
 ```C
#include <stdio.h>
int main () {

   int i = 1;

   do {
      printf("%d\n", i);
      i--;
   }while( i >= 10 );
 
   return 0;
}
 ```

# ***ตัวอย่างที่  3 : แสดงผลรวมของจำนวน n โดยใช้ Do While Loop***

> ตรงนี้ค่าเริ่มต้นของ total คือ 0 จากนั้น Do While Loop จะวนซ้ำจาก i = 1 จนถึง 100 ในแต่ละการวนซ้ำ i จะถูกบวกเข้ากับ total และค่าของ i จะเพิ่มขึ้น 1
> ผลลัพธ์ คือ 1+2+3+...+99+100.

**ตัวอย่างภาษา DART**
 ```dart
void main(){

  int total = 0;
  int n = 100; // เปลี่ยนตามความต้องการ
  int i =1;
  
  do{
  total = total + i;
    i++;
  }while(i<=n);
  
  print("Total is $total");
  
}
```

***Output***
 ```dart
Total is 5050
```

**ตัวอย่างภาษา JAVA**
 ```Java
public class Main {    
public static void main(String[] args) {    
    int total = 0;
    int n = 100;
    int i =1;    
    do{
        total = total +i;      
        i++;    
    }while(i<=n);
 System.out.println("Total is " + total);      
}    
}    
 ```
**ตัวอย่างภาษา C**
 ```C
#include <stdio.h>
int main () {
   int total = 0;
   int n = 100;
   int i = 1;

   do {
      total = total + i;
      i++;
   }while( i <= n );
   printf("Total is %d\n", total);
   return 0;
}
 ```

# **เมื่อเงื่อนไขเป็นเท็จ**

> มาทำให้เงื่อนไขหนึ่งเป็นเท็จและดู demo ด้านล่าง Hello จะถูกแสดงผลออกมา ถ้าเงื่อนไขเป็นเท็จ

 ```dart
void main(){

  int number = 0;
  
  do{
  print("Hello");
  number--;
  }while(number >1);
  
}
```

***Output***
 ```dart
Hello
```

# เพิ่มเติม

* ตัวอย่างเพิ่มเติม การใช้คำสั่ง Do While ในการแสดงผลเลขคี่
  
**ตัวอย่างภาษา DART**
 ```dart
void main() {
  int number = 0;
  do {
    if (number % 2 == 1) {
      print(number);
    }
    number++;
  } while (number < 10);
}
*
```

* ขั้นแรก ประกาศตัวแปร number และกำหนดค่าเริ่มต้นให้เป็น 0
* ขั้นที่สอง ใช้ do while loop เพื่อวนซ้ำจาก 1 ถึง 10 และแสดงเฉพาะเลขคี่ เลขคี่คือตัวเลขที่มีเศษ 1 เมื่อหารด้วย 2 (number % 2 == 1)

***Output***
 ```dart
1
3
5
7
9
```

**ตัวอย่างภาษา JAVA**
 ```Java
public class Main {    
public static void main(String[] args) {    
    int number = 0;    
    do{
      if(number % 2 == 1){
          System.out.println(number);
      }
      number++;            
    }while(number < 10);      
}    
}    
 ```

**ตัวอย่างภาษา C**
 ```C
#include <stdio.h>
int main () {
   int number = 0;
   do {
      if(number % 2 == 1){
        printf("%d\n", number);
      }
      number++;
   }while(number < 10);
   return 0;
}
 ```

# Summary
* ใช้คำสั่ง Do While Loop เพื่อ run บล็อกโค้ดซ้ำๆ ตราบใดที่เงื่อนไขเป็นจริง

# Reference
* https://www.javatpoint.com/dart-do-while-loop
* https://dart-tutorial.com/conditions-and-loops/do-while-loop-in-dart/
* https://www.darttutorial.org/dart-tutorial/dart-do-while/


# **VIDEO**
* https://www.youtube.com/watch?v=rYP6R_3CqVE&t=2s
* https://www.youtube.com/watch?v=0-I3fQO7ECs

# **SLIDE**
* [DO WHILE LOOP IN DART.pptx](https://github.com/soonklang/dart-tutorial/files/12780154/DO.WHILE.LOOP.IN.DART.pptx)
* [DO WHILE LOOP IN DART.pdf](https://github.com/soonklang/dart-tutorial/files/12886395/DO.WHILE.LOOP.IN.DART.pdf)
