# Constructor in Dart (Part 2)
## ตัวอย่างที่ 5 : การเขียน Constructor แบบย่อ
- ในตัวอย่างก่อนหน้านี้คุณจำเป็นต้องเขียน Constructor แบบเต็ม เเต่คุณสามารถเขียนแบบย่อให้สั้นลงเหลือเพียงบรรทัดเดียวได้ โดยการ Assign ค่าลงไปใด้โดยตรงได้เลยตามตัวอย่างด้านล่าง

 ```dart
class Person{
  String? name;
  int? age;
  String? subject;
  double? salary;

  // Constructor in short form
  Person(this.name, this.age, this.subject, this.salary);

  // display method
  void display(){
    print("Name: ${this.name}");
    print("Age: ${this.age}");
    print("Subject: ${this.subject}");
    print("Salary: ${this.salary}");
    }
}

  void main(){
    Person person = Person("John", 30, "Maths", 50000.0);
    person.display();
}
```

## ตัวอย่างที่ 6 : Constructor แบบมี Optional Parameters
- Optional Parameters คือ Parameters ที่เราจะสามารถส่งหรือไม่ส่งค่ามาก็ได้ Constructor ก็ยังสามารถทำงานได้ตามปกติ ถ้าไม่ได้กำหนดค่า  default จะมีค่าเป็น NULL
- ในตัวอย่างด้านล่าง เราได้ทำการสร้าง Class Person มี Property คือ **name**,**lastName** เเละ **age** จากนั้นสร้าง Constructor เพื่อ initialize ค่าของ Property ทุกตัว เเต่สำหรับ **age** เเละ **lastName** เราจะรับค่าแบบ Optional Parameters 

 ```dart
class Person {
  String? name;
  String? lastName;
  int? age;
  
  // Constructor
  Person([this.name, this.lastName, this.age]);

  // Method
  void display() {
    print("Name: ${this.name}");
    print("Last Name: ${this.lastName}");
    print("Age: ${this.age}");
  }
}

void main(){
  Person person = Person("David", "Carter");
  person.display();
}
```
- Output
```
Name: David
Last Name: Carter
Age: 0
```
### ตัวอย่าง Optional Parameters ในภาษา Java
> หมายเหตุ ภาษา Java นั้นไม่มี Optional Parameters เป็นการประยุกต์ใช้จากวิธี Constructor Overloading
```java
class Person{
  String name;
  String lastName;
  int age;

  Person(String name,String lastName,int age){
    this.name = name;
    this.lastName = lastName;
    this.age = age;
  }
  Person(String name,String lastName){
    this.name = name;
    this.lastName = lastName;
    this.age = 0;
  }
  Person(String name){
    this.name = name;
    this.lastName = null;
    this.age = 0;
  }
  void display(){
    System.out.println("Name : "+this.name);
    System.out.println("Last Name : "+this.lastName);
    System.out.println("Age : "+age);
  }

  public static void main(String arg[]){
    Person person = new Person("David","Carter");
    person.display();
  }
}
```
* Output
```
Name: David
Last Name: Carter
Age: 0
```
## ตัวอย่างที่ 7 :  Parameters ที่มีชื่อ (Named Parameters)
* Parameters ที่มีชื่อทำให้สามารถส่งค่าโดยการเรียกชื่อของ Parameters โดยไม่ต้องคำนึงถึงลำดับของ Parameters ที่เขียนไว้ใน Constroctor ก็ได้
* ตัวอย่างด้านล่างเราได้สร้าง Class ShowMyDetails มี Property คือ **name**,**lastName** เเละ **age**
 สำหรับ **lastName** เเละ **age** จะถูกกำหนดเป็น Parameters ที่มีชื่อโดยครอบด้วยเครื่องหมาย {} (ปีกกา)
```dart
class ShowMyDetails{
  String? name;
  String? lastName;
  int? age;

  ShowMyDetails({this.name,this.lastName,this.age});

  void display(){
    print("Name: ${this.name}");
    print("Last Name: ${this.lastName}");
    print("Age: ${this.age}");
  }  
}

void main(){
    ShowMyDetails smd = ShowMyDetails(name: "Jay", age: 24 ,lastName: "Tillu",);
    smd.display();
  }
```
- Output
>สังเกตที่ฟังก์ชัน Main() ตรงบรรทัดการสร้าง Object ใช้การส่งค่าผ่านชื่อของ Parameters ถึงเเม้ว่าลำดับจะไม่ถูกต้อง Constructor ก็ยังทำงานได้ตามปกติ
```
Name : Jay
Last Name : Tillu
Age : 24
```
> หมายเหตุ ภาษา Java ไม่มีการ Support การตั้งชื่อ Parameters

## ตัวอย่างที่ 8 : การกำหนด Default Values ใน Constructor
- เป็นการกำหนดค่าเริ่มต้นหากไม่มีการส่งค่าผ่านการเรียกใช้ Constructor ตอนสร้าง Object
- ตัวอย่างด้านล่างนี้ เราได้ทำการสร้าง Class Square มี Property คือ **height** เเละ **width** จากนั้นสร้าง Constructor เพื่อ initialize ค่าของ Property ทั้งสองตัว เเละกำหนด Default Values ให้กับ **height** เเละ **width** ใน Constructor
```dart
class Square {
  int? height;
  int? width;

  // Assign Default Values in Constructor
  Square({this.height = 2, this.width = 2});

  // Method
  void display() {
    print("Square height: ${this.height}");
    print("Square width: ${this.width}");
    
  }
}

void main(){
  Square sq1 = Square();
  sq1.display();
}
```
- Output
> เมื่อไม่มีการส่งค่าผ่านการเรียนใช้ Constructor ค่าของ Property จะเป็นไปตามค่าที่กำหนดเป็น Default Values ไว้
```
Square height: 2
Square width: 2
 ```
### ตัวอย่างการกำหนด Default Values ใน Constructor ในภาษา java
- เป็นการกำหนดค่าลงไปใน Constructor โดยตรงเเละไม่มีพารามิเตอร์ใดๆ
 ```java
public class MyClass {
   private int x;
   private String y;

   public MyClass() {
      //Assign Default Values
      this.x = 5;
      this.y = "Educative";
      
   }
   public int getX(){return x;}
   public String getY(){return y;}

   public static void main(String[] args) {
     MyClass myClass = new MyClass();
     System.out.println(myClass.getX());
     System.out.println(myClass.getY()); 
   }
}
 ```
- Output
```
5
Educative
```
## Key Points
- Constructor ต้องมีชื่อเดียวกับ Class
- Constructor ไม่มี return type
- Constructor ถูกเรียกใช้เพียงครั้งเดียว ณ เวลาสร้าง Object
- Constructor ถูกเรียกใช้งานอย่างอัตโนมัติ ณ เวลาสร้าง Object
- Constructor ถูกใช้เพื่อ initialize ค่าของ Properties ของ Class

## reference(s)
- https://dart-tutorial.com
- https://dart.dev
- https://www.educative.io

## วิดีโอนำเสนอ
- [Google Drive](https://drive.google.com/file/d/1SGjWTSb65Rp_0Dy2itYXcIJk0b5c2GLj/view?usp=drive_link)
- [Youtube](https://www.youtube.com/watch?v=GpzJq3lpHew)
## สไลด์นำเสนอ
- [Constructor in Dart Part2.pptx](https://github.com/soonklang/dart-tutorial/raw/main/6.%20OOP%20In%20Dart/Constructor%20in%20Dart%20Part2.pptx)
- [Constructor in Dart Part2.pdf](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Constructor%20in%20Dart%20Part2.pdf)
