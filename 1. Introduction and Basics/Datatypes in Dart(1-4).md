# Datatypes in Dart(1-4)

ในหัวข้อนี้ เราจะพามารู้จักกับชนิดข้อมูลในภาษาDart โดยชนิดข้อมูลมีดังนี้

## 1.Number

  สามารถเขียนในภาษาDartได้ 3แบบ คือ int ,double , num   โดยตัวเลขที่จะแสดงในโปรแกรมสามรถเก็บตัวเลขได้ทั้ง int และ double  ทั้งint และ double เป็นชนิดย่อยของnum เราสามารถใช้numเพื่อเก็บค่าของint และdouble ในDartนั่นเอง 
  
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

  ```dart
   void main(){
    print("I love \nYou");
    print("I love \tYou");
}
   ```
  ## การแปลงประเภทของDart
  เราสามารถแปลงข้อมูลได้มากกว่า 1 ประเภท เช่น แปลงจาก String เป็น int ,String เป็น Boolean
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
 - เช่น คุณแต่งงานหรือยัง
 ```dart
    void main() {
bool isMarried = true;
print("Married Status: $isMarried");
}
 ```


## 4.Lists
   เป็นการเก็บค่าหลายค่าไว้ในตัวแปรเดียว หรือที่เรียกว่า อาเรย์ ถ้าเราไม่ได้การสร้างค่าหลายค่าเราสามารถใช้Listsในการเก็บได้นั่นเอง
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
   ชนิดของNumber มีการใช้float เข้ามาเพิ่ม โดย float ในภาษาC ใช้กับตัวเลขที่มีทศนิยมไม่เกิน 6 ตำแหน่ง 
   ชนิดของString ใช้คำว่าChar โดย Char จะแยกเป็นตัวอักษรออกมาจากประโยค
   ```C
    char letter ='c'; 
   ```
   ## ภาษาJava 
 จำนวนชนิดของข้อมูลที่มากกว่า 
 - long, short int เป็นต้น
## ภาษาPyhon
   มีการใช้จำนวนชนิดข้อมูลที่เยอะและหลากหลาย และแยกประเภทการใช้งานได้ชัดเจน
 - Text Type:	str
 - Numeric Types:int, float, complex
 - Sequence Types:list, tuple, range
 - Mapping Type:dict
   
