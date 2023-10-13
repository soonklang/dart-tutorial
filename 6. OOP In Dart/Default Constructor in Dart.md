# Default Constructor in Dart
Default Constructor คือ contructor ที่ถูกสร้างขึ้นอัตโนมัติจาก compiler ของ Dart โดยจะไม่มีการใส่ parameter จะเป็นการเรียกใช้ default contructor โดยอัตโนมัติ
## ตัวอย่าง
```dart
class Laptop {
  String? brand;
  int? prize;

  //default constructor
  Laptop() {
    print("This is a default constructor");
  }
}

void main() {
  // Here laptop is object of class Laptop.
  Laptop laptop = Laptop();
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>This is a default constructor</code></pre>
</details>

## ตัวอย่างที่2
```dart
class Student {
  String? name;
  int? age;
  String? schoolname;
  String? grade;

  // Default Constructor
  Student() {
    print(
        "Constructor called"); // this is for checking the constructor is called or not.
    schoolname = "ABC School";
  }
}
void main() {
  // Here student is object of class Student.
  Student student = Student();
  student.name = "John";
  student.age = 10;
  student.grade = "A";
  print("Name: ${student.name}");
  print("Age: ${student.age}");
  print("School Name: ${student.schoolname}");
  print("Grade: ${student.grade}");
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Constructor called
Name: John
Age: 10
School Name: ABC School
Grade: A</code></pre>
</details>

# Default Constructor in Dart กับ ภาษาอื่นๆ
## python
```python
Class Default():
  def _init_(self):
    self.var1='This is default Constructor'
    self.var2=1
  def prinfSelf:
    printf(self.var1)
    printf(self.var2)
obj= Default()
obj.prinfSelf()
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>This is default Constructor
    1</code></pre></details>

## java
```java
class Laptop{
  String brand;
  int prize;
  Laptop(){//default constructor
    System.out.println("This is default Constructor")
  }
  public static void main(String[] args){
       Laptop obj = new Laptop();
       System.out.println(obj.prize);
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>This is default Constructor
    0</code></pre></details>

## C++
```c++
#include <iostream>
using namespace std;
 
class Base {
public:
    // compiler "declares" constructor
};
 
class A {
public:
    // User defined constructor
    A() { cout << "A Constructor" << endl; }
 
    // uninitialized
    int size;
};
 
class B : public A {
    // compiler defines default constructor of B, and
    // inserts stub to call A constructor
 
    // compiler won't initialize any data of A
};
 
class C : public A {
public:
    C()
    {
        // User defined default constructor of C
        // Compiler inserts stub to call A's constructor
        cout << "C Constructor" << endl;
 
        // compiler won't initialize any data of A
    }
};
 
class D {
public:
    D()
    {
        // User defined default constructor of D
        // a - constructor to be called, compiler inserts
        // stub to call A constructor
        cout << "D Constructor" << endl;
 
        // compiler won't initialize any data of 'a'
    }
 
private:
    A a;
};
 
// Driver Code
int main()
{
    Base base;
 
    B b;
    C c;
    D d;
 
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>A Constructor
A Constructor
C Constructor
A Constructor
D Constructor</code></pre></details>

# ข้อเปรียบเทียบกับภาษาอื่นๆ
## ภาษา C
C ไม่มี default contrutor เพราะ C ไม่มีconceptของcontructor ในภาษานี้แต่จะมีการใช้ struct ที่ใกล้เคียงแทน
## ภาษา python
Python จะรับparameterเป็นselfเท่านั้นซึ่งselfจะ reference ถึง object ของ class นั้น
## ภาษา java
Java มีความใกล้เคียงกับ Dart มีความแตกต่างตรงที่ java จะมีการ initializes fields เป็น default value นั่นคือ 0 ส่วน Dart จะไม่มีการ initializes fields ทำให้ค่าที่ default value เป็น null
## ภาษา C++
C++ จะมีการ initializes fields เป็น default value นั่นคือ 0 ส่วน Dart จะไม่มีการ initializes fields ทำให้ค่าที่ default value เป็น null
# Reference
## Dart :
- https://dart-tutorial.com/object-oriented-programming/default-constructor-in-dart
- https://www.javatpoint.com/dart-constructor
- https://www.geeksforgeeks.org/constructors-in-dart
## Java :
- https://www.geeksforgeeks.org/constructors-in-python
- https://beginnersbook.com/2018/03/python-constructors-default-and-parameterized
- https://tutorial.eyehunts.com/python/default-constructor-in-python-with-example
## Python :
- https://www.geeksforgeeks.org/constructors-in-python
- https://beginnersbook.com/2018/03/python-constructors-default-and-parameterized
- https://tutorial.eyehunts.com/python/default-constructor-in-python-with-example
## C :
- https://www.educba.com/constructor-in-c/
## อื่นๆ :
- https://www.sciencedirect.com/topics/computer-science/default-constructor
- https://www.geeksforgeeks.org/default-constructors-in-cpp/

## Video
- https://youtu.be/U1IMsBtooyE
## Slide
- v1  [640710051 Default Contructor in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12765100/640710051.Default.Contructor.in.Dart.pdf)
- v2  [640710051DefaultContructor.pdf](https://github.com/soonklang/dart-tutorial/files/12889492/640710051DefaultContructor.pdf)

640710051 ธนธรณ์ ยุวรรณศิริ





