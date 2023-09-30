# Inheritance in Dart cont.

##  *ประเภทของ Inheritance* : 
- _Single Inheritance_
- _Multiple Inheritance_ 
- _MultiLevel Inheritance_
- _Hierarchical Inheritance_


## 3.  Multilevel Inheritance  

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
      ทำให้ Class Bird ตอนนี้กล้ายเป็น Parent Class ของ Class Parrot สุดท้ายเราได้สร้าง class Eagle ที่จะสืบทอดต่อมาจาก Class Parrot อีกที 
      Class Eagle ตอนนีี้มีทั้งคุณสมบัติของ Class Bird และ Class Parrot
      
      ในตัว Main เราจะทดลองด้วยการสร้าง Object ของ Eagle มีชื่อว่า e ขึ้นมาและให้ทดลองเรียกใช้ทั้ง Method speak() ที่เป็นของ Parrot  
      fly() ที่เป็นของ Bird และ vision() ที่เป็นของEagleเองด้วย

      สุดท้ายผลลัพธ์ดังใน Output แสดงว่า Eagle ได้สืบทอดคุณสมบัติมาจากทั้ง Parrot และ Bird ได้สำเร็จ  

        

  
*ต่อไปนี้เราจะลองเขียนScenarioเดียวกันนี้อยู่ในบริบทภาษาอื่นเช่นภาษา Python , Java , และ C++* 

<details> 
   <summary><strong>Python Code</strong></summary>

   ```python
   class Bird:
      def fly(self) :
         print("The bird can fly")
   
   
   #inherit from SuperClass Bird
   class Parrot(Bird):
      def speak(self) :
         print("The parrot can speak")
   
   
   #inherit from Parrot intermediate class
   class Eagle(Parrot) :
      def vision(self):
         print("The eagle has a sharp vision")
   
   e = Eagle()
   e.fly()
   e.speak()
   e.vision()
   ```
   output
   ```
   The bird can fly
   The parrot can speak
   The eagle has a sharp vision
   ```
</details>

<details> 
   <summary><strong>Java code</strong></summary>
   
   ```java
      class Bird {
          void fly(){
              System.out.println("The bird can fly");
          }
      }
      class Parrot extends Bird {
          void speak(){
              System.out.println("The parrot can speak");
          }
      }
      class Eagle extends Parrot {
          void vision(){
              System.out.println("The Eagle has a sharp vision");
          }
      }


      public class Main {
          public static void main(String[] args) {
              Eagle e = new Eagle();
              e.vision();
              e.fly();
              e.speak();
          }
      }
   ```
   output
   ```
   The Eagle has a sharp vision
   The bird can fly
   The parrot can speak
   ```
</details>

<details>
   <summary><strong>C++ code</strong></summary>

   ```c++
      #include <iostream>
      
      class Bird {
      public:
          void fly() {
              std::cout << "The bird can fly" << std::endl;
          }
      };
      
      class Parrot : public Bird {
      public:
          void speak() {
              std::cout << "The parrot can speak" << std::endl;
          }
      };
      
      class Eagle : public Parrot {
      public:
          void vision() {
              std::cout << "The Eagle has a sharp vision" << std::endl;
          }
      };
      
      int main() {
          Eagle e;
          e.vision();
          e.fly();
          e.speak();
          return 0;
      }
   ```
   output
   ```
   The Eagle has a sharp vision
   The bird can fly
   The parrot can speak
   ```
</details>
      
   _สังเกตเห็นว่า Syntax ของ Dart กับ Java มีลักษณะคล้ายคลึงกัน_   

### Conclusion
   
      Multilevel inheritance เกิดมาจากหลาย classes inherit ต่อๆกันในรูบแบบเป็น Chain วิธีนี้เหมาะสำหรับการที่เราอยากจะนำเสนอ
      ให้เห็นว่าแต่ละLevel of hierarchy มีคุณสมบติส่วนตัวอะไร้บางที่เพิ่มขึ้นไป ต่อจากClassที่ถัดมา 
      มันทำให้ง่ายขึ้นต่อการควบคุม Application ที่ซับซ้อน เนืองจาก Developer สามารถ Focus กับส่วนของ Program โดยเฉพาะ
      โดยไม่จำเป็นต้องกังวลกับ Program ทั้งหมดทั้งมวลที่มีขนาดอันแสนใหญ่

      นอกจากนี้มันก็ช่วย Improve Readability กับ Reusability ของ Program อีกเช่นกัน ถถถ

      อย่างไรก็ตามบางทีมันจะก่อให้เกิดปัญหา unexpected result ในเมื่อ 2 Levels of class หรือมากกว่านี้ มี Method ที่มีลักษณะเหมือนกัน
      มันจะทำให้มีความลำบากต่อการตัดสินใจว่าต้อง Execute Method ตัวไหน

## 4.  Hierarchical Inheritance
![image](https://github.com/soonklang/dart-tutorial/assets/141731788/c85e6699-feb7-4be4-96e8-3d4de6edb8ed)

      การสืบทอดแบบ Hierarchical เกิดขึ้นตอนทีมี 2 Classes หรือมากกว่า 2 Classes ทำการถ่ายทอดมาจาก Class อันหนึ่งเดียวกัน

      ในภาษา Dart นี้ก็เช่นกัน ก็ถูกพัฒนาขึ้นมาให้ perform การสืบทอดแบบ Multilevel ได้โดยดี เราจะไปดูตัวอย่างต่อไปนี้
#### Hierarchical Inheritance in Dart :
      
```dart
class Person {  
  void dispName(String name) {  
    print(name);  
  }  
  
  void dispAge(int age) {  
    print(age);  
  }  
}  
  
class Peter extends Person {  
   
  void dispBranch(String nationality) {  
    print(nationality);  
  }  
}  
//Derived class created from another derived class.  
class James extends Person {  
          void result(String result){  
              print(result);  
}  
}  
void main() {  
      // Creating Object of James class  
      James j = new James();  
      j.dispName("James");  
      j.dispAge(24);  
      j.result("Passed");  
  
    // Creating Object of Peter class  
      Peter p = new Peter();  
      p.dispName("Peter");  
      p.dispAge(21);  
      p.dispBranch("Computer Science");  
  
}
```
output
```
James
24
Passed
Peter
21
Computer Science
```
      สังเกตในตัวอย่าง Code เราได้สร้าง Class James กับ Class Peter ขึ้นมาโดยให้ทั้งสองอันทำการสืบทอดมาจาก Class Person เหมือนกัน
      ต่อมาเป็นการทดลองโดยสร้าง Instance ของ Class James กับ Class Peter ในตัว Main ละลองให้ทั้งสอง Object j กับ p เรียกใช้ method 
      dispName() กับ dispAge() และจะได้ผลลัพธ์ในตัว Output
      
      ผลลัพธ์ในตัว Output นี้แสดงให้เห็นว่า Class Peter กับ Class Jame ได้ทำการสืบทอดคุณสมบัติมาจาก Class Person ได้สำเร็จ และถูกต้อง

_ต่อไปนี้ เหมือนที่เช่นเคยเราจะไปทดลองเขียน Scenario เดียวกันนี้ให้อยู่ในรูบแบบภาษาอื่นอีกที_

<details> 
   <summary><strong>Python Code</strong></summary>

   ```python
   class Person:
    def dispName(self, name):
        print(name)

    def dispAge(self, age):
        print(age)

    # inherit from parent class Person


class James(Person):
    def dispBranch(self, nationality):
        print(nationality)

    # inherit from parent class Person


class Peter(Person):
    def result(self, result):
        print(result)

    # Creating Object of James class


j = James()
j.dispName(name="James")
j.dispAge(age=24)
j.dispBranch(nationality="Computer Science")

# Creating Object of Peter class
p = Peter()
p.dispName(name="Peter")
p.dispAge(age=21)
p.result(result="Passed")
   ```
</details>
<details> 
   <summary><strong>Java Code</strong></summary>

   ```java
   class Person {
    void dispName(String name) {
        System.out.println(name);
    }

    void dispAge(int age) {
        System.out.println(age);
    }
}

class Peter extends Person {
    void dispBranch(String branch) {
        System.out.println(branch);
    }
}

class James extends Person {
    void result(String result) {
        System.out.println(result);
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating an object of James class
        James j = new James();
        j.dispName("James");
        j.dispAge(24);
        j.result("Passed");

        // Creating an object of Peter class
        Peter p = new Peter();
        p.dispName("Peter");
        p.dispAge(21);
        p.dispBranch("Computer Science");
    }
}
```
</details>
<details> 
   <summary><strong>C++ Code</strong></summary>

   ```c++
   #include <iostream>
using namespace std;

class Person {
public:
    void dispName(string name) {
        cout << name << endl;
    }

    void dispAge(int age) {
        cout << age << endl;
    }
};

class Peter : public Person {
public:
    void dispBranch(string branch) {
        cout << branch << endl;
    }
};

class James : public Person {
public:
    void result(string result) {
        cout << result << endl;
    }
};

int main() {
    // Creating an object of James class
    James j;
    j.dispName("James");
    j.dispAge(24);
    j.result("Passed");

    // Creating an object of Peter class
    Peter p;
    p.dispName("Peter");
    p.dispAge(21);
    p.dispBranch("Computer Science");

    return 0;
}
```
</details>

### Conclusion :
      งานนี้เหมาะสำหรับการที่เราอยากสร้างกลุ่มของClasses ที่มีควาทสัมพันกัน ที่มีคุณสมบัติคลายๆกัน

      ช่วยให้โปรแกรมของเราเป็นระเบียบเรียบร้อยและมีประสิทธิภาพดีขึ้น เนื่องจากสมาชิกของ base classes ทั้งหมด available 
      สำหรับ derived classes


## Video Link 
https://youtu.be/H1vG-EsnUw4

## Slide link
https://drive.google.com/file/d/18-KzZVMCf_Ofc58J_YlUuVXuiiRfvOv1/view?usp=share_link)
## References :
https://www.javatpoint.com/dart-inheritance

https://www.darttutorial.org/dart-tutorial/dart-inheritance/

https://www.geeksforgeeks.org/dart-concept-of-inheritance/?ref=lbp

https://www.w3schools.com/cpp/cpp_inheritance.asp

https://www.w3schools.com/java/java_inheritance.asp

https://www.w3schools.com/python/python_inheritance.asp

https://datatrained.com/post/multilevel-inheritance/#:~:text=Advantages%20of%20Multilevel%20Inheritance&text=By%20using%20multilevel%2C%20the%20same,and%20modified%20in%20various%20ways.

https://www.shiksha.com/online-courses/articles/hierarchical-inheritance-in-c-with-real-life-analogy/#



