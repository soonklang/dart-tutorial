
# Super Keyword in Dart

**Super** Keyword คือการอ้างอิง Object คลาสแม่ (Parent Class) ใช้ในการเรียกคุณสมบัติหรือ method ของคลาสแม่ ซึ่ง **Super** Keyword มักถูกใช้เพื่อแก้ปัญหา method ของคลาสแม่และคลาสลูกมีชื่อเดียวกัน


## Syntax

```dart
// ใช้สำหรับเรียก Constructor ของคลาสแม่
child_name():super()

// ใช้สำหรับเรียก Variable ของคลาสแม่
super.variable_name;

// ใช้สำหรับเรียก Method ของคลาสแม่
super.method_name();
```


## การใช้ Super Keyword

- ใช้ในการเข้าถึงข้อมูลสมาชิกคลาสแม่กรณีที่ข้อมูลสมาชิกคลาสแม่และคลาสลูกมีชื่อเดียวกัน
- ใช้เรียก Constructor คลาสแม่ในคลาสลูก
- ใช้เรียก Method คลาสแม่ที่ถูก Override


### ตัวอย่าง 1 เรียก Constructor

```dart 
class Parent  
{   
    Parent()   
    {   
        print("This is the super class constructor");   
    }   
}   

class Child extends Parent   
{   
    //สร้าง Constructor ของ Child Class และเรียก Constructor ของ Parent Class
    Child():super()
    {                   
        print("This is the sub class constructor");   
    }   
}  
  
void main() {  
    Child c = new Child();   
}
```

Output

```
This is the super class constructor
This is the sub class constructor
```

### ตัวอย่าง 2 เรียก Variable

```dart
//Parent Class
class Car  
{   
    int speed = 180;   
}   
    
//Superclass
class Bike extends Car   
{   
    int speed = 110;   
    void display()   
    {   
        //print speed จาก Parent Class
        print("The speed of car: ${super.speed}");  
    }   
}   
void main() {  
    Bike b = new Bike();  
    b.display();  
}  
```

Output

```
The speed of car: 180
```

### ตัวอย่าง 3 เรียก Method

```dart
class Super   
{   
    void display()   
    {   
        print("This is the super class method");   
    }   
}   
  
class Child extends Super   
{   
    void display()   
    {   
        print("This is the child class");   
    }   
  
    void message()   
    {    
        //เรียก display() ใน Child เอง
        display();   
        //เรียก display() จาก Parent Class 
        super.display();   
    }   
}   
  
void main() {  
// สร้าง Child Class
Child c = new Child();   
// เรียก display() จาก Child
c.message();   
    }   
```

Output

```
This is the child class method
This is the super class method
```

## ความแตกต่างของ Super Keyword ในภาษา Dart กับภาษาอื่น

- Java
Super Keyword ในภาษา Java นั้นมีหลักการและวิธีใช้เหมือนกับ Dart จะมีความแตกต่างเล็กน้อยตอนประกาศ Constructor ดังนี้

```java
class Parent  
{   
    Parent()   
    {   
        System.out.println("This is the super class constructor");   
    }   
}   

class Child extends Parent   
{   
    Child()
    {
        //ใน java นั้นจะไม่สามาณนำคำสั่ง super() ไปรวมกับตัวประกาศ Constructor ด้านบนได้
        super();          
        System.out.println("This is the sub class constructor");   
    }   
}  
public class Test{
    public static void main(String[] args){  
        Child c = new Child();   
    }
}
```
- C
ในภาษา C นั้นจะไม่มีคำสั่งไหนเทียบกับ Super Keyword ใน Dart แต่ถ้าเป็น C# จะมีคำสั่งที่เทียบกับได้นั้นคือ base ซึ่งจะมีหลักการใช้และวิธีใช้ที่ใกล้เคียงกับ super() ใกล้เคียงกับ เช่น

```c#
public class Person
{
    protected string ssn = "444-55-6666";
    protected string name = "John L. Malgraine";

    public virtual void GetInfo()
    {
        Console.WriteLine("Name: {0}", name);
        Console.WriteLine("SSN: {0}", ssn);
    }
}
class Employee : Person
{
    public string id = "ABC567EFG";
    public override void GetInfo()
    {
        base.GetInfo();
        Console.WriteLine("Employee ID: {0}", id);
    }
}

class TestClass
{
    static void Main()
    {
        Employee E = new Employee();
        E.GetInfo();
    }
}
```

Output

```
Name: John L. Malgraine
SSN: 444-55-6666
Employee ID: ABC567EFG
```

- Python
ในภาษา Python มี Super Keyword อยู่เหมือนกันและมีจุดประสงค์ในการใช้งานเหมือนกับ Dart เช่น

```python
class Emp():
    def __init__(self, id, name, Add):
        self.id = id
        self.name = name
        self.Add = Add
 
class Freelance(Emp):
    def __init__(self, id, name, Add, Emails):
        super().__init__(id, name, Add)
        self.Emails = Emails
 
Emp_1 = Freelance(103, "Suraj kr gupta", "Noida" , "KKK@gmails")
print('The ID is:', Emp_1.id)
print('The Name is:', Emp_1.name)
print('The Address is:', Emp_1.Add)
print('The Emails is:', Emp_1.Emails)
```

Output

```
The ID is: 103
The Name is: Suraj kr gupta
The Address is: Noida
The Emails is: KKK@gmails
```
- สรุป
โดยรวมแล้ว Super Keyword ของ Java และ Python นั้นมีหลักการใช้และวิธีการใช้เหมือนกันจะมี C เท่านั้นที่หา Keyword ใกล้เคียงกับ Super ไม่ได้ ในที่นี่จึงนำ C# มาเปรียบเทียบแทนซึ่งมีวิธีใช้ที่เหมือนกันเช่นกันแตกต่างกันแค่ Syntax

## Reference
https://dart-tutorial.com/object-oriented-programming/super-in-dart/

https://www.javatpoint.com/dart-super-keyword

https://www.geeksforgeeks.org/dart-super-and-this-keyword/

https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/base

https://www.geeksforgeeks.org/python-super/

## Link Video & Slide

[Video](https://youtu.be/yBH5ggRjTfY)

Slide [PDF](https://drive.google.com/file/d/1i86EDA9wc1QV2CiRtW4gkQTmC18zeDm7/view?usp=sharing) [PowerPoint](https://docs.google.com/presentation/d/1cFvfXN0p57oSyobPVj6GEiaOk4tLrMUP/edit?usp=sharing&ouid=110310470817710773976&rtpof=true&sd=true)


