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
- output
     ```dart
     5.456
     ```
## 2.String

  สตริงช่วยให้เราสามารถเก็บเป็นข้อความได้ โดยเราใช้เครื่องหมายคำพูดเดี่ยวหรือคู่ได้ เพื่อจัดเก็บเป็นสตริงได้

   - ตัวอย่างการใช้งาน:
   
   ```dart
   void main(){
    String Name ="Marry Christmas";
    String Days="25 December";
    print(”$Name+on+$Days ”);

}
   ```
- output
     ```dart
     Marry Christmas on 25 December
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

    - output:
     ```dart
     Type of strvalue is String
     Value is intvalue is 1
     Type of intvalue is int
     ```

## 3.Boolean
   ในภาษาDart บูลีนถือเป็นค่าจริงหรือเท็จ โดยเราสามารถเขียนkeywordกำหนดได้ ขึ้นอยู่กับว่าเราจะกำหนดว่าสิ่งไหนเป็นจริงหรือเป็นเท็จ โดยสิ่งที่เป็นจริงต้องตรงกับคำตอบที่เราต้องการ
   
 - ตัวอย่างการใช้งาน:
   
 ```dart
   void main() {
      bool check;
      int a=5;
     int b=4;
        if(a>b){
          check=true;
      }  else{
         check = false;
     }
      print(check);
 } 
 ```
- output:
  ```dart
   true
  ```
## 4.Lists

   เป็นการเก็บค่าหลายค่าไว้ในตัวแปรเดียว หรือที่เรียกว่า อาเรย์ ถ้าเราไม่ได้การสร้างค่าหลายค่าเราสามารถใช้Listsในการเก็บได้นั่นเอง  เป็นกลุ่มของวัตถุที่ได้รับการจัดลำดับ และต้องเป็นชนิดข้อมูลเดียวกันไม่สามารถต่างชนิดกันได้
   
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
- output:
    ```dart
   Value of Types is Bus, Car, Van
   Value of Types[0] is Bus
   Value of Types[1] is Car
   Value of Types[2] is Van
   The Length of Types is 3
    ```

## เปรียบเทียบขนิดข้อมูลกับภาษาอื่นๆ

   ## ภาษาC ,ภาษา Java และ ภาษา Python
  - ชนิดข้อมูลในภาษา C, Java,Python  ส่วนใหญ่มีการใช้งานคล้ายๆกับในภาษา Dart แต่บางชนิดข้อมูลก็ไม่ได้ใช้ในภาษาDart เลย โดยเราจะยกตัวอย่างให้เห็นความแตกต่างกันดังนี้
   ## ภาษา C
     ในภาษา C มีการใช้double และ floatที่แยกการใช้งานของตัวเลขที่มีทศนิยมที่ชัดเจน
   - float ใช้เก็บตัวเลขที่มีทศนิยมถึง6ตำแหน่งเท่านั้น ด้วยควมแม่นยำเดียว
   - double ใช้เก็บตัวเลขที่มีทศนิยมโดยเก็บได้มากสุดถึง17ตำแหน่ง โดยทีความแม่นยำ 
       มากกว่า float
     ```C
        float a = 9.0;
        double b=11.0;
        printf("%f", a);
        printf("%lf", b);
     ```
  - output
      ```C
           9.000000
           11.000000000
      ```
    - แต่ในภาษา Dart ไม่มีการใช้ชนิดข้อมูล float นั่นเอง
  ## ภาษา Java
  - ชนิดข้อมูล long สามารถตัวเลขจำนวนเต็มได้ตั้งแต่ -32768 ถึง 32767 
        แต่ในภาษา Dart เราจะใช้ intหรือ num ไม่มีตัวอื่นในการใช้ตัวเลขจำนวนเต็ม
      
  ## ภาษาPyhon
  - lists ภาษา Python สามารถเก็บข้อมูลชนิดที่เหมือนกันและต่างชนิดในlistได้ 
        แต่ในDart จะเก็บชนิดข้อมูลที่เหมือนกันได้เท่านั้น 
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
   - แต่ใน Dart
      - ตัวอย่างการใช้งาน:
      ```Dart
        name =["John","Ann","Byran"];
       ```
      - ถ้าเป็นแบบนี้
      ```Dart
        name =["John", "8","Byran"];
       ```
      จะเกิดอาการerror ได้

 ## Reference
   - https://www.w3schools.com/java/java_data_types.asp
   - https://www.w3schools.com/c/c_data_types.php
   - https://www.digitalocean.com/community/tutorials/python-data-types
   - https://dart-tutorial.com/introduction-and-basics/datatypes-in-dart/
   - https://www.geeksforgeeks.org/data-types-in-c/

## file การนำเสนอ
  - [Datatypes in Dart(1-4).pdf](https://github.com/soonklang/dart-tutorial/files/12752008/Datatypes.in.Dart.1-4.pdf)
  - [Datatypes in Dart(1-4) v.2.pdf](https://github.com/soonklang/dart-tutorial/files/13053803/Datatypes.in.Dart.1-4.v.2.pdf)


## Link Video
   - https://www.youtube.com/watch?v=fxsf0Uqh1bU
