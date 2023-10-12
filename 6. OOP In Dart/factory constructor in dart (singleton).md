# Singleton in dart
ก่อนอื่นเลยต้องทำความเข้าใจก่อนว่า Singleton คืออะไร Singleton คือ pattern การออกแบบซอฟต์แวร์โปรแกรมเชิงวัตถุ โดยใน Singleton จะสามารถมีการสร้าง instance ได้แค่เพียงตัวเดียวเท่านั้น และถ้ามีความต้องการจะใช้ instance อีกก็ไม่จำเป็นต้องมีการสร้างเพิ่ม สามารถใช้ Instance ที่สร้างไว้ตั้งแต่แรกได้เลย  ซึ่งในภาษา dart คุณสามารถสร้าง Singleton ได้โดยง่ายด้วยการใช้ **factory constructor** 

"เปรียบเทียบ Singleton ให้เห็นภาพ เหมือนห้องเรียนแห่งหนึ่งจะสามารถมีกระดานไวท์บอร์ดไว้ภายในห้องเรียนเพียงได้แค่แผ่นเดียวเท่านั้น ซึ่งหากภายในห้องเรียนยังไม่มีกระดานไวท์บอร์ด และมีความต้องการจะใช้งานก็จะทำการซื้อมาใช้งาน และเมื่อมีความต้องการจะใช้งานอีกก็ไม่จำเป็นจะต้องซื้อมาเพิ่มอีก"

**รูปแบบการเขียน Singleton Using Factory Constructor**

   ```dart
	class Singleton {
	  static final Singleton _singleton = Singleton._internal();

	  factory Singleton() {
	    return _singleton;
	  }

	  Singleton._internal();
	}
```
  นอกจากนี้ยังมีรูปแบบการเขียนแบบอื่นอีก

 1. Factory constructor

```dart
class SingletonOne {

  SingletonOne._privateConstructor();

  static final SingletonOne _instance = SingletonOne._privateConstructor();

  factory SingletonOne() {
    return _instance;
  }

}
```

 2. Static field with getter
```dart
class SingletonTwo {

  SingletonTwo._privateConstructor();

  static final SingletonTwo _instance = SingletonTwo._privateConstructor();

  static SingletonTwo get instance => _instance;
  
}
```

 3. Static field 
```dart
class SingletonThree {

  SingletonThree._privateConstructor();

  static final SingletonThree instance = SingletonThree._privateConstructor();
  
}
```

 

**ตัวอย่างการใช้งาน**
   ```dart
    // Singleton using dart factory
	class Singleton {
	 // static variable
	 static final Singleton _instance = Singleton._internal();
 
	// factory constructor
	 factory Singleton() {
	   return _instance;
	 }
	 // private constructor 
	 Singleton._internal();
	}
 
	void main() {
	 Singleton obj1 = Singleton();
	 Singleton obj2 = Singleton();
	 print(obj1.hashCode);
	 print(obj2.hashCode);
	}
 ```
  จากโค้ดนี้คือได้มีการสร้าง object ขึ้นมาสองตัว และจะสังเกตว่าเมื่อพิมพ์ค่า hashcode ออกมาค่าทั้งสองก็เหมือนกัน



## Difference Between Dart with other
**รูปแบบการเขียน Singleton ใน java** 
```java
public class Singleton {

	private static Singleton instance;

	private Singleton() {

}

public static Singleton getInstance() {

	if (instance == null) {

	instance = new Singleton();

	}

	return instance;

	}

}
```
  ในภาษา java จะมีการรูปแบบการเขียนที่แตกต่างกันกับ dart แต่ก็มีการทำงานผลลัพท์ที่เหมือนกัน java ก็จะมีการเช็คก่อนว่ามีการ สร้าง object ยัง ถ้าไม่มีก็จะทำการสร้างขึ้นมา



**รูปแบบการเขียน Singleton ใน python** 
```python
 class GovtSingleton:
	__instance__ = None

	def __init__(self):
	# This is a Constructor
	if GovtSingleton.__instance__ is None:
		GovtSingleton.__instance__ = self
	else:
		1raise Exception("We can not creat another class")
```
  ในภาษา python ก็จะมีรูปแบบการเขียนคล้ายๆกับภาษา java ก็คือมีการเช็คก่อนค่าก่อนแล้วค่อนสร้าง
## **Advantages and Disadvantages of the Singleton**

**ข้อดี**

 - ลดการใช้งานของหน่วยความจำ
 - ง่ายต่อการควบคุมและใช้งาน
 
 **ข้อเสีย**
 
 - ลดประสิทธิภาพการเพิ่มลดขนาด และการทดสอบโปรแกรม
 - อาจจะเกิดความยุ่งยาก ถ้าไม่มีจัดการที่ดี




## Reference

 - [Factory Constructor in Dart :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://dart-tutorial.com/object-oriented-programming/factory-constructor-in-dart/)
 - [Singleton Design Pattern in Python - javatpoint](https://www.javatpoint.com/singleton-design-pattern-in-python)
 - [Singleton Design Pattern | Implementation - GeeksforGeeks](https://www.geeksforgeeks.org/singleton-design-pattern/)
 - [How do you build a Singleton in Dart? - Stack Overflow](https://stackoverflow.com/questions/12649573/how-do-you-build-a-singleton-in-dart)
## Video
-https://youtu.be/jdqeFUmnteA

## Slide

 -[pdf](https://drive.google.com/file/d/1mSNPw755RCxA4IBsEK5nawxxh_Im-oiW/view?usp=drive_link)
 -[Powerpoint](https://docs.google.com/presentation/d/1LnPVZ5FcOVgjTNYhDBmJgSr0gsBoN824/edit?usp=drive_link&ouid=109956211958922233250&rtpof=true&sd=true)

