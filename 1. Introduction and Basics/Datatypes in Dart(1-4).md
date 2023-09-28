# Datatypes in Dart(1-4)

ในหัวข้อนี้ เราจะพามารู้จักกับชนิดข้อมูลในภาษาDart ชนิดของตัวแปรถูกกำหนดค่าถูกโดยค่าของมันและประเภทข้อมูลระบุประเภทของค่าที่จะถูกจัดเก็บโดยตัวแปร ตัวแปรแต่ละตัวมีประเภทข้อมูลของตัวเอง Dart เป็นภาษาประเภทคงที่ ซึ่งหมายความว่าตัวแปรไม่สามารถแก้ไขได้
โดยชนิดข้อมูลในภาษาDartมีดังนี้

## 1.Number

  สามารถเขียนในภาษาDartได้ 3แบบ คือ int ,double , num   
  - int ใช้กับตัวเลขที่เป็นจำนวนเต็ม
  - double ใช้กับตัวเลขที่เป็นทศนิยม
  - num สามารถใช้แทนได้ int และ double
  - ตัวอย่างการใช้งาน:
  ```dart
   void main(){
    int a =500;
    double b = 108.56;
    num c = 208.0;
    num d = 78;
}
   ```

- ในNumber เราสามารถปัดตัวเลขเป็นค่าทศนิยมกี่ตำแหน่งก็ได้ โดยใช้คำสั่ง .toStringAsFixed()
   ```dart
   void main(){
   double haha = 5.456252466;
   print(haha.toStringAsFixed(3));
   }
   ```

## 2.String

  สตริงช่วยให้เราสามารถเก็บเป็นข้อความได้ โดยเราใช้เครื่องหมายคำพูดเดี่ยวหรือคู่ได้ เพื่อจัดเก็บเป็นสตริงได้

   - ตัวอย่างการใช้งาน:
   
   ```dart
   void main(){
    String Name ="Marry Christmas";
    String Days="25 December";
}
   ```

   - การสร้างสตริงหลายบรรทัด เราสามารถใช้เครื่องหมายคำพูดสามอัน ,คู่ หรือเดี่ยวได้
   ## อักขระพิเศษในสตริงมีดังนี้
   - /n   หมายถึง ขึ้นบรรทัดใหม่
   - /t   หมายถึง เว้นวรรค
     
  - ตัวอย่างการใช้งาน:
  
  ```dart
   void main(){
    print("I love \nYou");
    print("I love \tYou");
}
   ```

  ## การแปลงประเภทของDart
  เราสามารถแปลงข้อมูลได้มากกว่า 1 ประเภท เช่น แปลงจาก String เป็น int ,String เป็น Boolean
  
  - ตัวอย่างการใช้งาน:
  
   ```dart
  void main() {
String strvalue = "1";
print("Type of strvalue is ${strvalue.runtimeType}");   
int intvalue = int.parse(strvalue);
print("Value of intvalue is $intvalue");
print("Type of intvalue is ${intvalue.runtimeType}");
}
 ```

## 3.Boolean
   ในภาษาDart บูลีนถือเป็นค่าจริงหรือเท็จ โดยเราสามารถเขียนkeywordกำหนดได้ ขึ้นอยู่กับว่าเราจะกำหนดว่าสิ่งไหนเป็นจริงหรือเป็นเท็จ โดยสิ่งที่เป็นจริงต้องตรงกับคำตอบที่เราต้องการ
   
 - ตัวอย่างการใช้งาน:
   
 ```dart
   void main() {
  String str = 'Coding is ';
  String str1 = 'Fun';
   
  bool val = (str==str1);
  print (val); 
}
 ```

## 4.Lists

   เป็นการเก็บค่าหลายค่าไว้ในตัวแปรเดียว หรือที่เรียกว่า อาเรย์ ถ้าเราไม่ได้การสร้างค่าหลายค่าเราสามารถใช้Listsในการเก็บได้นั่นเอง  เป็นกลุ่มของวัตถุที่ได้รับการจัดลำดับ 
   
   - ตัวอย่างการใช้งาน:
   
   ```dart
   void main() {
List<String> Types = ["Bus", "Car", "Van"];
print("Value of Types is $Types");
print("Value of Types[0] is ${Types[0]}"); 
print("Value of Types[1] is ${Types[1]}"); 
print("Value of Types[2] is ${Types[2]}"); 
//finding Length of List
 int length =Types.length;  
print("The Length of Types is $length");
}
 ```

## เปรียบเทียบขนิดข้อมูลกับภาษาอื่นๆ

   ## ภาษาC
   
   ## ชนิดข้อมูลของภาษาC มีดังนี้
   - 1.int    ใช้กับตัวเลขจำนวนเต็ม
   - 2.float  ใช้กับตัวเลขที่มีทศนิยม 6-7ตตำแหน่ง
   - 3.double ใช้กับตัวเลขที่มีทศนิยมถึง 15 ตำแหน่ง
   - 4.char   ใช้เก็บตัวอักขระ,ตัวอักษร
     
   ## ตัวระบุพื้นฐาน
   - 1.%d ใช้กับ int
   - 2.%f ใช้กับ float
   - 3.%lf ใช้กับ double
   - 4.%c ใช้กับ char
   - 5.%s ใช้กับ string
     
  ## ภาษาJava 
   - ชนิดข้อมูลพื้นฐาน  ประกอบด้วย byte, short, int, long, float, double, booleanและchar
   - ชนิดข้อมูลที่ไม่ใช่ข้อมูลพื้นฐาน - เช่นString, อาร์เรย์และ คลาส
     
   - ตัวอย่างการใช้งาน:
     ```Java
     class Main{
      public static void main(String[] args) {
       int myNum = 5;             
       float myFloatNum = 5.99f;    
       char myLetter = 'D';        
       boolean myBool = true;       
       String myText = "Hello";
     }
     }
      ```
## ภาษาPyhon
   มีการใช้จำนวนชนิดข้อมูลที่เยอะและหลากหลาย และแยกประเภทการใช้งานได้ชัดเจน
 - Text Type:	str
 - Numeric Types:int, float, complex
 - Sequence Types:list, tuple, range
 - Mapping Type:dict
 - lists ภาษา Python สามารถเก็บข้อมูลชนิดที่เหมือนกันและต่างชนิดในlistได้ 
   - ตัวอย่างการใช้งาน
   ```Pyhton
       #list of having only integers
       a= [1,2,3,4,5,6]
       print(a)

       #list of having only strings
       b=["hello","john","reese"]
       print(b)

       #list of having both integers and strings
       c= ["hey","you",1,2,3,"go"]
       print(c)
   ``` 
## Reference
   - https://www.w3schools.com/java/java_data_types.asp
   - https://www.w3schools.com/c/c_data_types.php
   - https://www.digitalocean.com/community/tutorials/python-data-types
   - https://dart-tutorial.com/introduction-and-basics/datatypes-in-dart/

## file การนำเสนอ
  - [Datatypes in Dart(1-4).pdf](https://github.com/soonklang/dart-tutorial/files/12752008/Datatypes.in.Dart.1-4.pdf)

## Link Video
   - https://www.youtube.com/watch?v=fxsf0Uqh1bU
