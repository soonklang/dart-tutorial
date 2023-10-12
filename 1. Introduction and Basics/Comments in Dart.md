# Comments in dart
  ในทุกภาษาการเขียนโปรแกรม comments มีบทบาทสำคัญในการทำความเข้าใจโค้ดให้ดีขึ้นในอนาคต หรือโดยโปรแกรมเมอร์คนอื่นๆ<br>
  comment เป็นชุดคำสั่งที่ถูกละเว้นโดย dart compiler ระหว่างการทำงานของโปรแกรม ใช้เพื่ออธิบายโค้ด
เพื่อให้ผู้อื่นสามารถเข้าใจได้ง่าย

## Advantages Of Comments (ข้อดีของ Comments)
  * สามารถอธิบายโค้ดของคุณได้
  * ผู้อื่นจะเข้าใจโค้ดของคุณชัดเจนยิ่งขึ้น

## Types Of Comments (ชนิดของ Comments)
  * Single-Line Comments: สำหรับการแสดงความคิดเห็นในโค้ดบรรทัดเดียว 
  * Multi-line comments: สำหรับการแสดงความคิดเห็นในโค้ดหลายบรรทัด 
  * Documentation Comments In Dart: สำหรับสร้างเอกสารหรืออ้างอิงสำหรับโครงการ/ แพ็คเกจซอฟต์แวร์ <br>


## **Single-Line Comments** ##  
  ใช้เพื่อแสดงความคิดเห็นในบรรทัดจนกว่าตัวแบ่งบรรทัดจะเกิดขึ้น ทำได้โดยใช้เครื่องหมายทับคู่ (//)
* Syntax
```
  // This is a single line comment. 
```

ตัวอย่าง:  
```dart
  int main()
{
  double area = 3.14 * 4 * 4;
  // It prints the area
  // of a circle of radius = 4
  print(area);
 
return 0;
}
```
>หลัง // บอกว่ามันจะพิมพ์พื้นที่,และบอกว่าค่ารัศมีวงกลม = 4
<details open>
<summary><b>output</b></summary>
 <pre>
50.24
</pre>
</details>


## **Multi-line comments** ##
  ใช้เพื่อแสดงความคิดเห็นในส่วนของโค้ดทั้งทั้งหมด ใช้ /* และ */ เพื่อเริ่มต้นและสิ้นสุดความคิดเห็นแบบหลายบรรทัดตามลำดับ
* Syntax
```
  /* 

  These are 

  multiple line 

  of comments 

  */ 
```

ตัวอย่าง:
```dart
  int main()
{
  var lst = [1, 2, 3];
   
  /*
  It prints
  the whole list
  at once
  */
  print(lst);
   
return 0; }
```
>ในระหว่าง /* และ */ บอกว่ามันจะพิมพ์รายการทั้งหมดในครั้งเดียว
<details open>
<summary><b>output</b></summary>
 <pre>
[1, 2, 3]
</pre>
</details>


## **Documentation Comments** ## 
  เป็นความคิดเห็นประเภทพิเศษที่ใช้เพื่อให้การอ้างอิงแพ็คเกจ ซอฟต์แวร์ หรือโปรเจ็กต์.Dart รองรับความคิดเห็นเกี่ยวกับเอกสารสองประเภท "///"(C# Style) และ "/**.....*/"(JavaDoc) แต่ขอแนะนำให้ใช้ "///" สำหรับความคิดเห็นเกี่ยวกับเอกสาร
  หลายครั้งที่ * ใช้เพื่อทำเครื่องหมายรายการในรายการสัญลักษณ์แสดงหัวข้อย่อยซึ่งทำให้อ่านความคิดเห็นได้ยาก แนะนำให้ใช้ความคิดเห็นของเอกสารสำหรับการเขียน API สาธารณะ
* Syntax
```
  /// This is 

  /// a documentation 

  /// comment
```

ตัวอย่าง:
```dart
bool checkEven(n){
  /// Returns true
  /// if n is even
  if(n%2==0)
 
      return true;
  /// Returns false if n is odd
  else
 
      return false; }
 
int main()
{
  int n = 43;
  print(checkEven(n));
  return 0;
}
```
>หลัง /// บอกว่า คืนค่า true ถ้า n เป็นเลขคู่, คืนค่า false ถ้า n เป็นเลขคี่
<details open>
<summary><b>output</b></summary>
 <pre>
[false]
</pre>
</details> 

# ตัวอย่าง comments ในภาษาอื่นๆ

  ## single-line comment 
   * C
```
#include <studio.h>

Int main()

{
// print Hello world to the screen

print(“Hello world”);

Return 0;

}
```
<details open>
<summary><b>output</b></summary>
 <pre>
Hello world
</pre>
</details>
   
   * Java
```
    public class JavaCommentsExample {
  // This is a single-line Java comment

  public static void main(String[] args) {

    System.out.println("This line will run.");
    //System.out.println("This line will not run.");

  }
}
```

  * Python
```
  # create a variable
name = 'Eric Cartman'

  # print the value
print(name)
```
>ที่นี่ได้สร้างความคิดเห็นบรรทัดเดียวทั้งหมดสองรายการ คือ # create a variable และ # print the value
<details open>
<summary><b>output</b></summary>
 <pre>
Eric Cartman
</pre>
</details>


  ## multi-line comments
  * C
```
  /* This program takes age input from the user
It stores it in the age variable
And, Print the value using printf()*/

#include <stdio.h>
int main()
{
int age;
printf(“Enter the age: ”);
scanf("%d", &age);
printf("Age= %d", age);

return 0;
}
```
<details open>
<summary><b>output</b></summary>
 <pre>
Enter the age: 24
Age= 24
</pre>
</details>

  * Java
```
  public class JavaCommentsExample {
  /* This block comment spans only one line. */
  public static void main(String[] args) {
    System.out.println("This line will run.");

    /* This block comment spans multiple lines.
       System.out.println("This line will not run.");
       System.out.println("This line will not run.");
       None of the code in this Java block comment will run.
    */

  }
}
```
  * Python
    ใช้ได้ทั้งสองแบบ คือ #, ''' หรือ """
```  
  # This is a long comment
  # and it extends
  # to multiple lines
```
```
  ''' This is also a
  perfect example of
  multi-line comments '''
```
  ## Documentation Comments
  * Java
```
  /** This JavaDoc comment should describe the class. */
public class JavaCommentsExample {

  /** This JavaDoc comment should describe the method. */
  public static void main(String[] args) {

    System.out.println("This line will run.");  // Java comment
    /* System.out.println("This is in a Java block comment."); */

  }
}
```
> [!NOTE]
> ใช้ comments เสมอเพื่ออธิบายว่าทำไมเราถึงต้องทำอะไรบางอย่าง comments ไม่ควรทดแทนการอธิบายโค้ดที่เขียนไม่ดี<br>

## สรุปเปรียบเทียบในภาษาต่างๆ
  * Dart และ Java มี comments ที่เหมือนกันอยู่ทั้งหมด 3 ประเภท
  * แต่C และ Python ไม่มี Documentation Comments 
  * Python มีการใช้ Syntax ไม่เหมือนภาษาอื่น โดยมีการใช้ #, ''' หรือ """
  
     
     




## อ้างอิง
https://www.geeksforgeeks.org/dart-comments/<br>
https://dart-tutorial.com/introduction-and-basics/comments-in-dart/<br>
https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Java-Comment-Types-Example-Best-Practices-Block-Inline-JavaDoc<br>
https://www.programiz.com/python-programming/comments<br>
https://unstop.com/blog/comments-in-c


## Link Video
https://youtu.be/nBpeLYa4Xno?feature=shared

## Slide
[Comments in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12884850/Comments.in.Dart.pdf)

[Comments in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12884874/Comments.in.Dart.pptx)

  

