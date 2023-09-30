
# Parameterized Constructor in Dart
**Parameterized Constructor** เป็น **constructor** ที่มีการกำหนด **parameters** และ ค่าที่รับมาจะถูกส่งไปใน **constructor** ขณะที่กำลังมีการสร้าง **object** อาจเพื่อใช้กำหนดค่าให้  **instance variables** หรือ **ตัวแปร** ของ **class**


## Syntax
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(this.number, this.name);
    }
```
หรือจะเขียนแบบนี้ก็ได้
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(int number, String name){
	      this.number = number;
	      this.name = name;
      }
    }
```
### Example 1: Parameterized Constructor In Dart
ในตัวอย่างที่ 1 มี **class Student** ที่มี ตัวแปร 3 ตัว คือ **name** , **age** และ **rollNumber**
ใน **class Student** มี **constructor** ตัวเดียว ที่มีการรับ **parameters** มากำหนดค่าให้**ตัวแปร**ใน class ทั้ง 3 ตัว
ใน **main()** จะมีการสร้าง **object** ของ **class Student** โดยส่งค่า **"John"** , **20** , และ **1**
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
      // Constructor
      Student(this.name, this.age, this.rollNumber);
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student("John", 20, 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
ในภาษา **Dart** สามารถกำหนดค่าตัวแปรของ **Class** ใน **parameters** ของ **constructor** ได้เลย โดยใช้ ***this*.*ชื่อตัวแปร*** ของ **class** เช่นในตัวอย่าง ***this*.*name*** 

> Output
> 
```dart
    Name: John
    Age: 20
    Roll Number: 1
```
## 

### Example 2: Parameterized Constructor With Named Parameters In Dart
ในตัวอย่างที่ 2 ใช้ **class** เดียวกับตัวอย่างที่ 1 แต่มีการใช้ **name parameters** ใน **constructor**แทน 
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      }
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student(name: "John", age: 20, rollNumber: 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
สังเกตจากการใส่ **{ }** ครอบ **parameter**  ทำให้การสร้าง **object** ง่ายขึ้น เพราะ ไม่จำเป็นต้อง เรียง **argument** ที่จะส่งไปให้ตรงกับ **parameter** ของ **constructor** เช่น **constructor** ของ **Class Student** มี **parameters** เป็น **name** , **age** และ **rollNumber** ตามลำดับ

```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      } 
    }
```
เราสามารถสร้าง **object** โดยส่ง **argument** ไม่ตรงกับ **parameters** ได้ เพระ มี **name parameters** คอยกำกับอยู่ เช่น
```dart
    void main(){
        Student student = Student(rollNumber: 1, age: 20, name: "John" );
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```

> Output
> 
```dart
	Name: John
	Age: 20
	Roll Number: 1
```
## 
### Example 3: Parameterized Constructor With Default Values In Dart
ในตัวอย่างที่ 3 มี **class Student** ที่มี ตัวแปร 2 ตัว คือ **name** และ **age**
ใน **class Student** มี **constructor** ตัวเดียวและมีการกำหนดค่าให้ตัว **parameters** เพื่อใช้กำหนดค่าให้ตัวแปรใน **class**

จะสังเกตได้ว่าเป็น Named Parameter เหมือนตัวอย่างที่ 2 แต่จะมีการกำหนดค่าให้ **parameters** ถ้าไม่ต้องการให้เป็น Named Parameter สามารถนำ { } ออก และใช้ [ ] ครอบ parameter ที่จะกำหนดค่าได้

ใน **main()** จะมีการสร้าง **object** ของ **class Student** แต่จะไม่มีการส่งค่า
```dart
    class Student {
      String? name;
      int? age;
    
      // Constructor
      Student({String? name = "John", int? age = 0}) {
        this.name = name;
        this.age = age;
      }
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student();
        print("Name: ${student.name}");
        print("Age: ${student.age}");
    }
```
จาก code จะมีการกำหนดค่าให้ **parameters** name = "John" และ age = 0
```dart
      Student({String? name = "John", int? age = 0}) {
        this.name = name;
        this.age = age;
      }
```
> Output
> 
```dart
	Name: John
	Age: 0
```
## 
> **Note** : ใน Dart ไม่สามารถสร้าง constructor ที่มีชื่อเดียวกันได้แม้ว่าจะมี parameter ต่างกันก็ตาม ( แต่สามารถสร้าง constructor หลายๆตัวได้ เรียกว่า Named Constructor )

# Parameterized Constructor in Other languages
## C++
การสร้าง **constructor** แบบ **Parameterized** **Constructor** ใน **c++** เพียงเพิ่ม **parameter** ในลักษณะเดียวกับที่เพิ่มให้กับ **functions**
```c++
	// CPP program to illustrate
	// parameterized constructors
	#include <iostream>
	using namespace std;

	class Point {
	private:
		int x, y;

	public:
		// Parameterized Constructor
		Point(int x1, int y1)
		{
			x = x1;
			y = y1;
		}

		int getX() { return x; }
		int getY() { return y; }
	};

	int main()
	{
		// Constructor called
		Point p1(10, 15);

		// Access values assigned by constructor
		cout << "p1.x = " << p1.getX()
			<< ", p1.y = " << p1.getY();

		return 0;
	}
```
คำอธิบาย

 1. **class Point** มีตัวแปร 2 ตัว คือ **x** และ **y** ทั้งคู่เป็นชนิด **int**
 2. มี **constuctor** 1 ตัว ที่มีการรับ **parameters** 2 ตัวเป็นชนิด **int** เพื่อมากำหนดค่าให้ **x** และ **y**
 3. มี **method** 2 ตัวชื่อ **getX( )** และ **getY( )** ทำหน้าที่ return ค่า **x** และ **y**
 4. ใน **main( )** มีการสร้าง **object class Point** ชื่อ **p1** โดยส่งค่า **10** และ **15** แล้วเรียกใช้ **method getX( )** และ **getY( )**
> Output
> 
```c++
	p1.x = 10, p1.y = 15
```

## Java
ในภาษา **Java** สามารถมี **constructor** ที่มีชื่อเดียวกันแต่ **parameter** ต่างกันได้ เรียกว่า **constructor** **overloading**
**compiler** สามารถแยกความแตกต่างของ **constructor** ได้จาก จำนวน **parameter** , **data** **type** ของ **parameter** และ ลำดับของ **parameter**
```java
	// Java Program to illustrate constructor overloading
	// using same task (addition operation ) for different
	// types of arguments.

	import java.io.*;

	class Geek {
		// constructor with one argument
		Geek(String name)
		{
			System.out.println("Constructor with one "
							+ "argument - String : " + name);
		}

		// constructor with two arguments
		Geek(String name, int age)
		{

			System.out.println(
				"Constructor with two arguments : "
				+ " String and Integer : " + name + " " + age);
		}

		// Constructor with one argument but with different
		// type than previous..
		Geek(long id)
		{
			System.out.println(
				"Constructor with one argument : "
				+ "Long : " + id);
		}
	}

	class GFG {
		public static void main(String[] args)
		{
			// Creating the objects of the class named 'Geek'
			// by passing different arguments

			// Invoke the constructor with one argument of
			// type 'String'.
			Geek geek2 = new Geek("Shikhar");

			// Invoke the constructor with two arguments
			Geek geek3 = new Geek("Dharmesh", 26);

			// Invoke the constructor with one argument of
			// type 'Long'.
			Geek geek4 = new Geek(325614567);
		}
	}
```
คำอธิบาย

 1. **class** **Geek** มี **constructor** ตัว
 2. **constructor** ตัวที่ 1 มี **parameter** ชนิด **String** ชื่อ **name** เมื่อเรียกใช้ constructor ตัวนี้ จะทำการ **print** "Constructor with one argument - String : " ตามด้วยค่า **name** ที่รับมา
 3. **constructor** ตัวที่ 2 มี **parameter** 2 ตัว เป็น **String** ชื่อ **name** และ **int** ชื่อ **age** เมื่อเรียกใช้ **constructor** ตัวนี้ จะทำการ **print** "Constructor with two arguments :  String and Integer : " ตามด้วยค่า **name** และ **age** ที่รับมา
 4. **constructor** ตัวที่ 3 มี **parameter** 1 ตัว เป็น **long** ชื่อ **id** เมื่อเรียกใช้ **constructor** ตัวนี้ จะทำการ **print** "Constructor with one argument : Long : " ตามด้วยค่า **id** ที่รับมา
 5. **main( )** ใน **class** **GFG** จะทำการสร้าง **object** ของ **class** **Geek** 3 ตัว ชื่อ **geek2** , **geek3** , **geek4**
 6. **geek2** สร้างโดยการส่งค่า **"**Shikhar**"**
 7. **geek4** สร้างโดยการส่งค่า **"**Dharmesh**"** , **26**
 8. **geek4** สร้างโดยการส่งค่า **325614567**
> Output
> 
```c++
	Constructor with one argument - String : Shikhar
	Constructor with two arguments :  String and Integer : Dharmesh 26
	Constructor with one argument : Long : 325614567
```

## Python
**Parameterized Constructor** ใน **python constructor** จะมี **parameter** **self** ที่จะ **reference** ถึง **object** ของ **class** นั้นๆที่ถูกสร้าง และ **parameter** อื่นๆ จะเป็น **parameter** ที่ **programmer** เป็นคนเขียนขึ้นมาเพิ่ม
```python
	class Addition:
		first = 0
		second = 0
		answer = 0

		# parameterized constructor
		def __init__(self, f, s):
			self.first = f
			self.second = s

		def display(self):
			print("First number = " + str(self.first))
			print("Second number = " + str(self.second))
			print("Addition of two numbers = " + str(self.answer))

		def calculate(self):
			self.answer = self.first + self.second


	# creating object of the class
	# this will invoke parameterized constructor
	obj1 = Addition(1000, 2000)

	# creating second object of same class
	obj2 = Addition(10, 20)

	# perform Addition on obj1
	obj1.calculate()

	# perform Addition on obj2
	obj2.calculate()

	# display result of obj1
	obj1.display()

	# display result of obj2
	obj2.display()
```
คำอธิบาย

 1. **class** **Addition** มี ตัวแปร 3 ตัว ชื่อ **first** , **second** และ **answer** 
 2. มี **constructor** ที่รับ **parameter** เพิ่มจาก **self** อีก 2 ตัว คือ **f** และ **s** เพื่อ กำหนดค่าให้ตัวแปร **first** และ **second**
 3. ใน **class** มี **method** 2  ตัว
 4. **method display( )** ทำหน้าที่ print ค่าของตัวแปรใน class
 5. **method calculate( )** ทำหน้าที่ นำค่า **first** + **second** ไปเก็บใน **answer**
 6. มีการสร้าง **object** **class Addition** 2 ตัว ชื่อ **obj1** และ **obj2**
 7. **obj1** สร้างโดยการส่งค่า 1000 และ 2000
 8. **obj2** สร้างโดยการส่งค่า 10 และ 20
 9. **object** ทั้งสองเรียกใช้ **method** **calculate( )** และ **display( )**
 > Output
> 
```python
	First number = 1000
	Second number = 2000
	Addition of two numbers = 3000
	First number = 10
	Second number = 20
	Addition of two numbers = 30
```
# Video
- https://www.youtube.com/watch?v=AU5Yyw5erNI

# Slied
- [Parameterized Constructor in Dart.pdf](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Parameterized%20Constructor%20in%20Dart.pdf)

# Reference

 - https://dart-tutorial.com/object-oriented-programming/parameterized-constructor-in-dart/
 - https://dart.dev/language/constructors#initializing-formal-parameters
 - https://www.geeksforgeeks.org/constructors-in-dart/
 - https://toupawa.com/learn-dart-from-zero-to-standard-part-2/
 - https://www.geeksforgeeks.org/constructors-c/
 - https://www.geeksforgeeks.org/constructors-in-java/
 - https://www.geeksforgeeks.org/constructors-in-python/

640710052 ธนาดล ชีวโรจน์ณรงค์
