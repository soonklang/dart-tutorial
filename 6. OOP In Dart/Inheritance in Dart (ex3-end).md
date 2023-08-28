# Inheritance in Dart cont.

##  *ประเภทของ Inheritance* : 
- _Single Inheritance_
- _Multiple Inheritance_ 
- _MultiLevel Inheritance_
- _Hierarchical Inheritance_


## 3. Multilevel Inheritance  

   ![image](https://github.com/soonklang/dart-tutorial/assets/141731788/840d3601-c5f0-4fe1-9f3b-00866a95c2ef)

      การสืบทอดแบบ Multilevel เป็นกระบวนการอันหนึ่งที่เกิดขึ้นระหว่างที Subclass อันหนึ่งถูกสืบทอดโดยSubclassอื่นอีกที 
      และมันสามาถรเกิดขึ้นไปได้เรื่อยๆในรูบแบบเป็น chain of inheritance
      
      เหมือนกับภาษาส่วนใหญ่ทัวไป ภาษา Dart ก็ถูกพัฒนาขึ้นมาให้ Support การสืบทอดแบบ Multilevel เหมือนกัน

   #### Multilevel inheritane example in Dart :

   ```dart
class Bird{    
      void fly()  
         {  
            print("The bird can fly");  
          }  
   }    
      // Inherits the super class  
class Parrot extends Bird{    
         void speak(){  
             print("The parrot can speak");  
                 }  
             
}  
   
// Inherits the Parrot base class  
class Eagle extends Parrot {  
          void vision(){  
             print("The eagle has a sharp vision");  
                 }  
}  
void main() {  
      // Creating object of the child class  
      Eagle e=new Eagle();    
      e.speak();    
      e.fly();    
      e.vision();  
} 
```
output
```
The parrot can speak
The bird can fly
The eagle has a sharp vision
```
      ตัวอย่างCodeข้างบน เป็นการสร้าง Class Bird ขึ้นมา และตามมาด้วย Class Parrot ที่ได้รับการถ่ายทอด method มาจาก Class Bird 
      ทำให้ Class Bird ตอนนี้กล้ายเป็น Parent Class ของ Class Parrot สุดท้ายเราได้สร้าง class Eagle ที่จะสืบทอดต่อมาจาก Class Bird อีกที 
      Class Eagle ตอนนีี้มีทั้งคุณสมบัติของ Class Bird และ Class Parrot
      
      ในตัว Main เราจะทอดลองด้วยการสร้าง Object ของ Eagle มีชื่อว่า e ขึ้นมาและให้ทดลองเรียกใช้ ทั้ง Method speak() ที่เป็นของ Parrot  
      fly() ที่เป็นของ Bird และ vision() ที่เป็นของต้นเองด้วย

      สุดท้ายผลลัพธ์ดังใน Output แสดงว่า Eagle ได้สืบทอดคุณสมบัติมาจากทั้ง Parrot และ Bird ได้สำเร็จ
