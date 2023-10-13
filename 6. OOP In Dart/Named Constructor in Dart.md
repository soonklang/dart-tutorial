[![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20210317130050/Dart-Tutorial.png)](https://dart.dev/language/constructors)


# Named constructors in dart   🐦 
____________________________


> ### 📌Named constructors เป็นเอกลักษณ์ในภาษา Dart ในภาษาอื่น ๆ หลายภาษาก็มีความสามารถในการสร้าง constructors ที่คล้ายคลึงกับ Named constructors ใน Dart

------------


ภาษา **Dart** ไม่สามารถทำ **Method Overloading** หรือการสร้าง **Method** ชื่อเดียวกันรับ **Parameter** หลายแบบ จะไม่สามารถทําได้ (ตัวอย่างภาษาที่ทำได้คือ **Java**)  เพราะ Dart มี  **Optional Parameter** ให้ใช้งานแทน

------------
สำหรับคนที่ศึกษาเรื่อง **Class** มาเเล้ว จะเข้าใจว่า เราสามารถ สร้าง **Function** ที่เรียกอีกชื่อว่า **Constructor methob** ได้
### Syntax default Constructor ⌨️
```dart
class ClassName {																							 
  // default constructor
  ClassName(parameters) {
    // Initialization logic
  }

}

```

------------
#### แต่ Dart สามารถสร้าง Constructors หลายๆตัวได้ ซึ่งมีไว้เพื่อสร้าง Object หลายๆแบบ โดยเรียกว่า
#### Named constructors

###  Syntax Name Constructors in dart
```dart
class ClassName {																							
  // default constructor
  ClassName(parameters) {
    // Initialization logic
  }

  // Named constructor
  ClassName.namedConstructor(parameters) {
    // Initialization logic
  }
}

```

------------
### Using Named Constructors
```dart
ClassName instance1 = ClassName(parameters);  // default constructor
ClassName instance2 = ClassName.namedConstructor(parameters);   // named constructor
```
## Example

### Example 1
##### ตัวอย่างเเรก จะเป็นตัวอย่างเเบบง่ายๆ เพื่อความเข้าใจของผู้อ่าน
```dart
class Point {																								
    int x, y;
		//Default Constructor
    Point(this.x, this.y);
		//Named Constructor
    Point.origin() {
        x = 0;
        y = 0;
    }
}

var point1 = Point(10, 20);
var point0 = Point.origin();
```
##### คำอธิบาย:

- คลาส **Point** มี **Default constructor** ที่รับพารามิเตอร์ **x** และ **y** เพื่อกำหนดค่าพิกัดของจุด
มี **Named constructor** ชื่อ **origin** ที่กำหนดค่าพิกัด **x**และ **y** ให้เป็น **0** โดยเรียกใช้งานโดยไม่ต้องระบุพารามิเตอร์
- การสร้าง **instance** ของ **Point**ใน **main()** ฟังก์ชันเป็นการสร้างอ็อบเจกต์ **point1** โดยใช้ **Default constructor** และสร้างอ็อบเจกต์ **point0** โดยใช้ **Named constructor origin** เพื่อสร้างจุดที่ตั้งอยู่ที่จุดกำเนิด **(0, 0)**


------------


### Example 2
##### ตัวอย่าง โปรเเกรมคำนวนพื้นที่วงกลม
```dart
class Circle {																								
  double radius;
  const double pi = 3.1415926535897932;
  
  // Default constructor
  Circle(this.radius);

  // Named constructor for creating a unit circle
  Circle.unit()
      : radius = 1.0;

  // Named constructor for creating a scaled circle
  Circle.scaled(double scale)
      : radius = scale;
	  
    double areaCircle(){
		return pi*radius*radius;
	}
}

void main() {
  Circle circle1 = Circle(5.0);      // Using the default constructor
  Circle unitCircle = Circle.unit(); // Using the named constructor for a unit circle
  Circle scaledCircle = Circle.scaled(2.0); // Using the named constructor for a scaled circle
  
  print(circle1.areaCircle());
  print(unitCircle.areaCircle());
  print(scaledCircle.areaCircle());
}
```
1. **Class Circle** มี **properties** คือ **radius** ที่เก็บค่ารัศมีของวงกลม และ **pi** ที่เก็บค่าคงที่ **π (pi)** 

2. มี **default constructor** ที่รับพารามิเตอร์ **radius**เพื่อกำหนดค่ารัศมีของวงกลม

3. มี **named constructor** ชื่อ **unit**ที่กำหนดค่ารัศมีให้เป็น 1.0 เพื่อสร้างวงกลมหน่วย **(unit circle)**
4. มี **named constructor** ชื่อ **scaled** ที่ใช้สร้างวงกลมโดยกำหนดรัศมีด้วยพารามิเตอร์ **scale**

5. ฟังก์ชัน **areaCircle()** ที่ใช้คำนวณพื้นที่ของวงกลมด้วยสูตร **πr² (π times radius squared)**

6. ใน **main()** สร้าง **instances** ของ **Class Circle** ด้วยการใช้งานทั้ง **default constructor** และ **named constructors** ที่ได้กำหนดไว้

7. ใช้เมธอด **areaCircle()** เพื่อคำนวณและพิมพ์ผลลัพธ์ของพื้นที่วงกลม


### Output
```sh
78.53981633974483
3.141592653589793
12.566370614359172
```

------------


## Differences Named Constructors in other languages
![](https://scontent.fbkk4-4.fna.fbcdn.net/v/t1.15752-9/370567382_631034772181519_3993493830743264420_n.jpg?_nc_cat=109&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeHLAkaxUI6O_gDFsYGEOkQulBd9InIH5k6UF30icgfmTmcIwbK1k9yLEql3y7Cb3jkpFl2Wbe3m1ON-qFwl78Jk&_nc_ohc=PLq_rA3c3YUAX8Ldg-3&_nc_ht=scontent.fbkk4-4.fna&oh=03_AdRNFtxxUYG0r-IKQANfitB9ybUMzWw39bED2L8q_R6GEw&oe=654F9839)
**"Named constructor"** หรือ **"Alternative constructor"** เป็นแนวคิดในการสร้าง **Object** ใน **Programming language** โดยทั่วไปแล้วแนวคิดนี้เป็นเกี่ยวกับการสร้าง **Object** โดยใช้ **Methob** หรือ **Function** ที่มีชื่อเฉพาะเพื่อสร้าง **Object** ที่ต้องการ 

------------

#### เราจะนำ Code Dart ใน Example 1 มาเปรียบเทียบ

------------


## Java
![](https://scontent.fbkk3-4.fna.fbcdn.net/v/t1.15752-9/278848980_679598269819945_7666123435917040814_n.png?_nc_cat=108&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeF5PWsiOVgnDcGgO03cTeMjdr-EkcPc62N2v4SRw9zrY4DDd38HCEHrCgHuQuGB6NpngJB9wKPpYukVXRAxa9Da&_nc_ohc=dSdRJ8zLFHcAX8cLX0E&_nc_ht=scontent.fbkk3-4.fna&oh=03_AdTMsVXoMy2RgfDr1xDAjJV8oyjZezLbbzQFjTHzO4S31Q&oe=654F9D33)

ใน Java เนื่องจากไม่มี **named constructors** เหมือนกับ Dart แต่สามารถใช้ **static factory methods** ในการทำแนวคิดที่คล้ายกัน

**นี่คือตัวอย่างของการใช้ static factory methods ในภาษา Java:**


```java
public class MyClass {    
	private int x;
	private int y;

	private MyClass(int x, int y) {			//default constructor
		this.x = x;
 		this.y = y;
	}

	public static MyClass createFromCoordinates(int x, int y) {
	return new MyClass(x, y);										//factory constructor
	}

	public static MyClass createOrigin() {
	return new MyClass(0, 0);										//factory constructor
	}

	public static void main(String[] args) {
	MyClass point1 = MyClass.createFromCoordinates(10, 20);
	MyClass point0 = MyClass.createOrigin();
	}
	}
```



หรือ สามารถใช้วิธี **Overload** ในการเขียนก็ได้
```java
class Point {       
    int x, y;
     
	 Point() {
        this(0, 0);		//default constructor
    }
	
    Point(int x, int y) {			overload 
        this.x = x;
        this.y = y;
    }


    public static void main(String[] args) {
        Point point1 = new Point(10, 20);
        Point point0 = new Point();

    }
}
```

------------


## C
![](https://scontent.fbkk4-1.fna.fbcdn.net/v/t1.15752-9/371892639_204081532671915_311293905671308031_n.png?_nc_cat=107&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeFmYnG7iIcIW35zy42UZIBSgd3Gt40fSgqB3ca3jR9KCpKmeByYKXs2J0xO0Sz2BKElSYQDFXk7wHNbBojP_vsz&_nc_ohc=0Pxnxm9-IPUAX8XZdgx&_nc_ht=scontent.fbkk4-1.fna&oh=03_AdRDIyQgEAAA_hjD4Yz7znMtWFSBejPdGZFR6hzdQEaj_Q&oe=654F9509)

ในภาษา C , ไม่มี named constructors ในแบบเดียวกับ Dart  แต่สามารถใช้ **function** เพื่อสร้างตัวอย่างที่คล้ายคลึงกับ **named constructors** โดยใช้มาตรฐานไลบรารี **stdlib.h** ในการจองหน่วยความจำและกำหนดค่าสมาชิกของอ็อบเจกต์นั้น ๆ

**C ที่มีลักษณะคล้ายใน Dart ได้ดังนี้**
```c
#include <stdio.h>   
#include <stdlib.h>

// Declare the Point structure
struct Point {
    int x, y;
};

// Constructor for Point
struct Point createPoint(int x, int y) {
    struct Point point;
    point.x = x;
    point.y = y;
    return point;
}

// Named constructor equivalent for origin
struct Point createOrigin() {
    struct Point point;
    point.x = 0;
    point.y = 0;
    return point;
}

int main() {
    struct Point point1 = createPoint(10, 20);
    struct Point point0 = createOrigin();


    return 0;
}

```
> 📌*เมื่อเปรียบเทียบกับโค้ดใน **Dart** จะเห็นว่าการใช้งานโครงสร้างและฟังก์ชันใน **C** สามารถทำงานคล้ายกันกับการใช้งานคลาสและ **named constructors**ใน **Dart** แม้ว่าจะไม่เป็นเอกลักษณ์เดียวกัน*


------------

## Python
![](https://scontent.fbkk4-4.fna.fbcdn.net/v/t1.15752-9/327698238_913606733001601_7466354205277653364_n.png?_nc_cat=109&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeHrDDqU4tWqOzaG_-kc86aagjnCBXOG87-COcIFc4bzvzC0JWDaTZZBl6kvNyhsDn-bqCt5x2iFjjA6hLJ61OFT&_nc_ohc=yqY6gwXXRW4AX_GACRW&_nc_ht=scontent.fbkk4-4.fna&oh=03_AdSusMofq15LQjx05tWlL9ap7PkUlampbpqUd63EmovOqQ&oe=654F8C00)

เนื่องจาก **Python**ไม่มีเนื้อหาเกี่ยวกับ **constructor** หรือการสร้าง **Object** เหมือนกับภาษาอื่น ๆ สามารถใช้ **class methods** ในการทำ **Named constructors**

**นี่คือตัวอย่างของการใช้ class methods ในภาษา Python:**
```python
class MyClass:  
    def __init__(self, x, y):
        self.x = x
        self.y = y

    @classmethod
    def create_from_coordinates(cls, x, y):
        return cls(x, y)

    @classmethod
    def create_origin(cls):
        return cls(0, 0)

point1 = MyClass.create_from_coordinates(10, 20)
point0 = MyClass.create_origin()

```

------------

## Kotlin
![](https://scontent.fbkk4-2.fna.fbcdn.net/v/t1.15752-9/371073470_1471538273613032_6524486673642902331_n.png?_nc_cat=102&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeGwUIIwyDU7rrQ4tRrcouyqTYWz8FVQyPtNhbPwVVDI--2wu4_81pTdJWFXS_I8st0E5ObbteIIfD2ExwSppIvO&_nc_ohc=-zGRlMdBGB0AX_ZBPE5&_nc_ht=scontent.fbkk4-2.fna&oh=03_AdRf22fzchd5VBvBVBEC_9wxgq_85qzWP_FTXjXDZlTA1Q&oe=654FA2D0)

ในภาษา **Kotlin**การใช้งาน **Named Constructors** มีลักษณะคล้ายกับภาษา **Dart**และภาษาอื่น ๆ ในแนวคิดที่เรียกว่า **"Static Factory Methods"** ที่ใช้สร้าง **Object** จากชื่อ Methobเฉพาะ แต่ Kotlin จะมีลักษณะเฉพาะของภาษาที่ทำให้ Named Constructors มีรูปแบบที่แตกต่าง:

**นี่คือตัวอย่างของการใช้ Named Constructors ในภาษา Kotlin:**
```kotlin
class Point(private val x: Int, private val y: Int) {            

    companion object {
        fun origin(): Point {
            return Point(0, 0)
        }
    }
}

fun main() {
    val point1 = Point(10, 20)
    val point0 = Point.origin()

}

```
> 📌*ใน Kotlin, การใช้งาน Named Constructors มีความเด่นชัดในเรื่องของระเบียบและความกระชับของรหัส และสามารถเขียนได้ในแบบที่มีความอ่านง่าย แม้ว่าจะมีแนวคิดที่คล้ายกับภาษาอื่น ๆ การอ่านรหัสและการจัดการกับ Object ใน Kotlin จะมีความเป็นเอกลักษณ์ของภาษาเอง*


------------

### Summary of differences in each programming language.📚

ในทุกภาษา, แนวคิดของ **"Named constructor"** หรือ **"Alternative constructor"** เป็นวิธีที่คล้ายกันในการสร้าง **Object** ที่มีการกำหนดค่า **Parametor** ที่ต่างกันสามารถทำหน้าที่เหมือนกันได้ แต่มีไวยากรณ์ ภาษาที่แตกต่างกันบ้าง การเลือกใช้วิธีที่เหมาะสมกับภาษาและการทำงานเป็นสิ่งสำคัญที่สุด

------------
## Veido
[Named Constructor in dart Youtube](https://youtu.be/jOeYV6uZhvA "Named Constructor in dart Youtube")
------------

## Slide
## [PDF](https://github.com/soonklang/dart-tutorial/files/12888782/640710056.Named.Constructor.in.dart.pdf.pdf)
------------
## Presentation


## [Power Point](https://github.com/soonklang/dart-tutorial/files/12889357/640710056.Named.Constructor.in.dart.pre.pptx)



![](https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/50cd3144-a4f0-43a8-b464-78a1714e8628/dchoqoo-c9cb91ac-14cc-49da-9ac1-5786676e8893.gif?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzUwY2QzMTQ0LWE0ZjAtNDNhOC1iNDY0LTc4YTE3MTRlODYyOFwvZGNob3Fvby1jOWNiOTFhYy0xNGNjLTQ5ZGEtOWFjMS01Nzg2Njc2ZTg4OTMuZ2lmIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.nNAiX6RCm94AEDVNp0-2AOI8d2xo_8TmFxcIn1Kmt0M)


------------

# Reference
#### เว็บหลัก - [dart.dev/language/constructors](https://dart.dev/language/constructors "dart.dev/language/constructors")
- [nextflow.in.th/2020/dart-named-constructor-method/ "nextflow.in.th](https://nextflow.in.th/2020/dart-named-constructor-method/ "nextflow.in.th "nextflow.in.th/2020/dart-named-constructor-method/ "nextflow.in.th")
- [thiti.dev/blog/37/ "thiti.dev](https://thiti.dev/blog/37/ "thiti.dev")
- [tamemo.com/dart-103-oop](https://www.tamemo.com/post/174/dart-103-oop/ "tamemo.com/dart-103-oop")
- [toupawa.com/learn-dart-from-zero-to-standard-part-2](https://toupawa.com/learn-dart-from-zero-to-standard-part-2/ "toupawa.com/learn-dart-from-zero-to-standard-part-2")
- [chat gpt](https://openai.com/blog/chatgpt "chat gpt")

------------

## Contect
ชื่อ-นามสกุล : นายพงศกร ยิ้มสุขอนันต์
Student ID: 640710056
E-mail : phobos24137@gmail.com
### GitHub
[![](https://scontent.fbkk17-1.fna.fbcdn.net/v/t1.15752-9/370604935_672468984760511_1293788593002803048_n.png?_nc_cat=103&ccb=1-7&_nc_sid=8cd0a2&_nc_eui2=AeGzccAgcUSVimPhAAQS56zfvigywmYWkde-KDLCZhaR1_EP-o_cDRQA5KKt_SwqZnB2QIgHYBiiLtHmS2_oN2YM&_nc_ohc=pLZxFwVsC9IAX-1Y33N&_nc_ht=scontent.fbkk17-1.fna&oh=03_AdT1YRLrCSqoPeNS-9KfifeyBdKsn9kuB0SbBsT6K0X4ZQ&oe=65502A1E)](https://github.com/yimsukananP)
2023-08-31 04:34:43 Thursday
