# Constructor in Dart (Part 2)
## ตัวอย่างที่ 5 : การเขียน Constructor แบบย่อ
- ในตัวอย่างก่อนหน้านี้คุณจำเป็นต้องเขียน Constructor แบบเต็ม เเต่คุณสามารถเขียนแบบย่อให้สั้นลงเหลือเพียงบรรทัดเดียวได้ โดยการ Assign ค่าลงไปในพารามิเตอร์ได้เลย

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
- Optional Parameters คือ Parameters ที่เราจะสามารถส่งหรือไม่ส่งค่ามาก็ได้ Constructor ก็ยังสามารถทำงานได้ตามปกติ ถ้าไม่ได้กำหนดค่า  Defalut จะมีค่าเป็น NULL
- ในตัวอย่างด้านล่าง เราได้ทำการสร้าง Class Person มี Property คือ **name**,**lastName** เเละ **age** จากนั้นสร้าง Constructor เพื่อ initialize ค่าของ Property ทุกตัว เเต่สำหรับ **age** เเละ **lastName** เราจะรับค่าแบบ Optional Parameters 

 ```dart
class Person {
  String? name;
  String? lastName
  int? age;
  
  // Constructor
  Person(this.name, [this.lastName, this.age=0]);

  // Method
  void display() {
    print("Name: ${this.name}");
    print("Last Name: ${this.age}");
    print("Age: ${this.subject}");
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
- ตัวอย่าง Optional Parameters ในภาษา Java
> หมายเหตุ ภาษา Java นั้นไม่มี Optional Parameters เป็นการประยุกต์ใช้จาก Parameters แบบปกติ
```java
Class Person{
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
    Person person = new Person("David","Carter")
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
## ตัวอย่างที่ 7 : Constructor แบบมีการตั้งชื่อ Parameters (Named Parameters)
* การตั้งชื่อ Parameters ทำให้สามารถส่งค่าได้ผ่านชื่อของ Parameters โดยไม่ต้องคำนึงถึงลำดับของ Parameters ที่เขียนไว้ใน Constroctor ก็ได้
* ตัวอย่างด้านล่างเราได้สร้าง Class ShowMyDetails มี Property คือ **name**,**lastName** เเละ **age**
 สำหรับ **lastName** เเละ **age** จะถูกกำหนดเป็น Parameters ที่มีชื่อโดยครอบด้วยเครื่องหมาย {} (ปีกกา)
**Syntax**
```dart
class ShowMyDeails{
  String? name;
  String? lastName
  int? age;

  ShowMyDetails(String name, {String lastName, int age});

  void display(){
    print("Name: ${this.name}");
    print("Last Name: ${this.age}");
    print("Age: ${this.subject}");
  }
    
  void main() {
    ShowMyDetails smd = ShowMyDetails("Jay", age: 24 ,lastName: "Tillu",);
    smd.display();
  }
}
```
- Output
>สังเกตที่ฟังก์ชัน Main() ตรงบรรทัดการสร้าง Object ใช้การส่งค่าผ่านชื่อของ Parameters ถึงเเม้ว่าลำดับจะไม่ถูกต้อง Constructor ก็ยังทำงานได้ตามปกติ
```
Name : Jay
Last Name : Tillu
Age : 24
```


