# Exception Handling in Dart
   ## Exception Handler คือ
   เป็นสิ่งที่ช่วยดักจับข้อผิดผลาดในโปรแกรม โดยนำไปใส่ครอบโค๊ดที่มีโอกาสจะเกิดError เมื่อเกิด Error ขึ้นจะสามารถเขียนโค๊ดที่จะแก้ไขต่อไป
  ### Dart มีวิธีที่จะจัดการ Error เหล่านั้นดังนี้
  * Catch/On
  * Finlly
  * Throw
 
 ## Try Catch/On Block
   Try Block จะใช้สำหรับดักโค็ดที่มีโอกาส Error, Block จะใช้ได้ก็ต่อเมื่อเราระบุประเภทของ Exception และใส่วิธีจัดการลงไปใน OnหรือCatch
 >## Syntax
   ``` Dart
   try {
    //   โค๊ดที่มีโอกาส Error
    }
on Exception1 {
    // ระบุประเภท Exception
              }
Catch Exception2  {
     // โค๊ดที่ใช้จัดการ Exception
  }
   ```
* เราสามารถจัดการ Exceptionหลายอันได้โดยใช้Catchมากกว่าหนึ่ง Block
* Catch กับ On มีความคล้ายคลึงกัน สามารถใช้แทนกันได้
## ตัวอย่างการใช้งาน Try-On Block
```Dart 
void main() {
  String a = "B";
  try{
    var C = a ~/ 0;
    print(C);
  }
  on FormatException{
    print("Error!!");
  }
}
```
###  Output :
```
Error!!
```
## ตัวอย่างการใช้งาน Try-Catch Block
```Dart
void main() {
  String A = "Test";
  try{
    var B = A ~/ 0;
    print(B);
  }
  catch(e){
    print(e);
  }
}
```
### Output:
```
Class 'String' has no instance method '~/'.

NoSuchMethodError: method not found: '~/'
Receiver: "Test"
Arguments: [0]
```
## Final Block
เป็น Block ที่จะระบุว่าถ้าไม่ทำแล้วจะเกิดErrorขึ้นหรือไม่ หลังจากที่ทำTry/on/Catchแล้ว ก็จะมาทำในส่วนของ Final

>## Syntax
```Dart
try {   
   // โค๊ดที่มีโอกาส Error   
}    
on Exception1 {   
   // โค๊ดจัดการ Exception หรือ ระบุประเภท  Exception  
}    
catch Exception2 {   
   //  โค๊ดจัดการ Exception
}    
finally {   
   // โค๊ดที่จะรันเสมอไม่ว่าจะมี Exception หรือไม่  
}  
```
## ตัวอย่างการใช้งาน Final Block
```Dart
void main() {
  int A = 10;
  try{
    var B = A ~/ 0;
    print(B);
  }
  catch(e){
    print(e);
  }
  finally {
    print("Final Test");
  }
}
```
### Output:
```
Unsupported operation: Result of truncating division is Infinity: 10 ~/ 0
Final Test
```

## Throw Exception
เป็นการส่ง Exception ไปให้กับโค๊ดที่เรียก Exceptionมาทำหน้าที่ต่อ
>## Syntax
```Dart
try
{
   // โค้ดที่มีโอกาสเกิด Error
}
catch (Exception e)
{
   throw e;
}
```
## ตัวอย่างการใช้งาน Throw Exception
```Dart
main() {   
   try {   
      test_Weight(-50);   
   }   
   catch(e) {   
      print('Weight cannot be negative');   
   }   
}    
void test_Weight(int Weight) {   
   if(Dee<0) {   
      throw new FormatException(); 
   }   
}  
```
### Output:
```
Weight cannot be negative
```
# Reference
* https://www.javatpoint.com/dart-exceptions
* https://www.geeksforgeeks.org/exception-handling-in-dart/
* https://dart.dev/language/error-handling#exceptions
* https://www.tutorialspoint.com/dart_programming/dart_programming_exceptions.htm

## Slides & Clips
Vdo link : https://youtu.be/s0UPdajVGjE

Slide Files : [Exception Handling In Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12774188/Exception.Handling.In.Dart.pptx)
PDF: [Exception Handling In Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12887830/Exception.Handling.In.Dart.pdf)
