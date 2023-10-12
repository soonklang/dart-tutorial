# *Generics in Dart*
Generics เป็นวิธีการสร้าง Class, Function หรือ Method ที่สามารถทำงานได้กับข้อมูล
ประเภทต่างๆ ในลักษณะ Dynamic ตามการเรียกใช้งาน โดยหลักการคือ ให้ผู้เรียกใช้เป็นคนกำหนดเองว่าdata type ที่จะทำงานด้วยคืออะไร
 ## *Content*
 - [Syntax](#syntax)
 - [Example 1 Without Using Generics](#example-1-without-using-generics)
 - [Dart Generics Class](#dart-generics-class)
 - [Example 2 Using Generics](#example-2-using-generics)
 - [Generics Type Variable](#generics-type-variable)
 - [Generics Methods](#generics-methods)
 - [Example 3 Generic Method With Multiple Parameters](#example-3-generic-method-with-multiple-parameters)
 - [Restricting the Type of Data](#restricting-the-type-of-data)
 - [Example 4 Generic Class With Restriction](#example-4-generic-class-with-restriction)
 - [Example 5 Generic Method With
   Restriction](#example-5-generic-method-with-restriction)
 - [Using Generics with Dart
   Collections](#using-generics-with-dart-collections)
 - [Example6](#example-6)
 - [Generics in Java Python and C](#generics-in-java-python-and-c)
 - [Advantages of Dart Generics](#advantages-of-dart-generics)
 - [Slide](#slide)
 - [Video](#video)
 - [References](#references)

## *Syntax*

     class ClassName<T> {
          // code
     }
 < > เรียก ตัวดำเนินการ diamond

> T ภายในเครื่องหมาย `< >` จะอธิบายในหัวข้อ Generics Type Variable

## *Example 1* Without Using Generics

   ```dart  
    // สร้าง class สำหรับ int
    class IntData {
      int data;
      IntData(this.data);
    }
    // สร้าง class สำหรับ double
    class DoubleData {
      double data;
      DoubleData(this.data);
    }
    
    void main() {
      // สร้าง object ของ IntData class
      IntData intData = IntData(10);
      DoubleData doubleData = DoubleData(10.5);
      
      print("IntData: ${intData.data}");
      print("DoubleData: ${doubleData.data}");
    }
 ```

	Output => IntData: 10
		DoubleData: 10.5

หากต้องการ class ที่สามารถทำงานร่วมกับข้อมูลชนิดอื่นๆ ก็สร้าง `class XXXData` ขึ้นมา 
เช่นเดียวกับ class ที่ใช้งานกับ `int` และ `double`

แต่เนื่องจากภายใน `class IntData` และ `class DoubleData` มีโค้ดการทำงานเหมือนกัน 
วิธีการที่ดีกว่าการสร้าง `class XXXData` 
ขึ้นใหม่ตามชนิดข้อมูลที่ต้องการทำงานด้วย คือ การนำ Generics มาใช้งาน


## *Dart Generics Class*
ประกาศในรูปแบบ
 
 ```dart
    class GenericsType<T> {
	  /* การประกาศ field แบบไม่ระบุชนิดของข้อมูล */
	  private T t
      // code
    }
 ```
พารามิเตอร์ T หมายถึงการไม่ได้ระบุชนิดของข้อมูลที่คลาสจะรับมาดำเนินการ(จะเป็นชนิดใดก็ได้) และ field ใน class ก็ถูกประกาศโดยอ้างอิงพารามิเตอร์ T เช่นเดียวกัน

## *Example 2* Using Generics

   ```  dart
    class Data<T> {
      T data;
      Data(this.data);
    }
    
    void main() {
      // สร้าง object และกำหนด data type ที่ต้องการ
      Data<int> intData = Data<int>(10);			/* ต้องการทำงานกับ int */
      Data<double> doubleData = Data<double>(10.5); /* ต้องการทำงานกับ double */
    
      print("IntData: ${intData.data}");
      print("DoubleData: ${doubleData.data}");
    }
 ```

     Output => IntData: 10
    	    DoubleData: 10.5


เวลาใช้งาน Generics Class จะระบุชนิดของข้อมูลที่ต้องการในขั้นตอนการสร้าง object จะเห็นว่า สามารถส่ง data type ชนิดใดก็ได้ไปยัง `class Data()` โดยทุกจุดที่ใช้ตัว T จะถูกเปลี่ยนไปตามชนิดที่ส่งมาโดยอัตโนมัติ 

## *Generics Type Variable*

ตัวแปรภายใน `< >` ใช้เพื่อกำหนดประเภทของข้อมูล  ซึ่งสามารถแทนด้วยตัวแปรอะไรก็ได้ โดยตัวแปรที่นิยม คือ E, K, T และ V

E - Element

K - Key

T - Type

V – Value
```  dart
    /* สามารถใช้ตัวแปรอะไรแทน type ก็ได้ ในที่นี้ใช้ X */
    class Data<X> {
      X data;
      Data(this.data);
    }
   ```

## *Generics Methods*
ประกาศในรูปแบบ


    ReturnType MethodName<TypeParameter>(ParameterType parameter) {
    
	    // Implementation
    
    }
สามารถกำหนด generics ไว้กับ method ได้ดังนี้
```  dart
// สร้าง generic method
T genericMethod<T>(T value) {
  return value;
}

void main() {
  // เรียกใช้ generic method
  print("Int: ${genericMethod<int>(10)}");
  print("Double: ${genericMethod<double>(10.5)}");
  print("String: ${genericMethod<String>("Hello")}");
}
   ```     

    Output => Int: 10
    
	    Double: 10.5
    
	    String: Hello

## *Example 3* Generic Method With Multiple Parameters
หากต้องการระบุ Generics Type มากกว่า1ตัว ให้คั่น generic แต่ละตัวด้วย comma (,)
```  dart
// สร้าง generic method
T genericMethod<T, U>(T value1, U value2) {
  return value1;
}

void main() {
  // เรียกใช้ generic method
  print(genericMethod<int, String>(10, "Hello"));
  print(genericMethod<String, int>("Hello", 10));
}
   ```    

    Output => 10
	       Hello

## *Restricting the Type of Data*
ขณะที่ใช้งาน Generics สามารถจำกัดประเภทของชนิดข้อมูลที่ใช้งานกับ Class หรือ Method ได้โดยใช้คีย์เวิร์ด extends

## Example 4 Generic Class With Restriction
```  dart
	// ประกาศ generic class โดยจำกัดประเภทของชนิดข้อมูล
	class Data<T extends num> {
	  	T data;
	  	Data(this.data);
	}

	void main() {
 		// สร้าง object และกำหนด data type ที่ต้องการ
	  	Data<int> intData = Data<int>(10);			/* ต้องการทำงานกับ int */
	  	Data<double> doubleData = Data<double>(10.5);		/* ต้องการทำงานกับ double */
	
	  	print("IntData: ${intData.data}");
	  	print("DoubleData: ${doubleData.data}");
	
	  	// Data<String> stringData = Data<String>("Hello");  // error
	}
   ```
`<T extends num>` ทำให้     `Class Data()`  ใช้ได้กับ `int` และ `double` เท่านั้น จะใช้กับประเภทอื่นไม่ได้

## *Example 5* Generic Method With Restriction
```  dart
	T getVal<T extends String>(T value1, T value2) {
	  	return (value1);
	}

	void main() {
	  	// เรียกใช้ generic method
	  	//print("int: ${getVal<int>(10, 20)}");			// error
	  	//print("double: ${getVal<double>(10.5, 20.5)}");		// error
	  	print("getString: ${getVal<String>("ten point five", "twenty point five")}");
	}
   ```

    Output => getString: ten point five
`<T extends String>` ทำให้ `Method getVal()` ใช้ได้กับ `String` เท่านั้น จะใช้กับประเภทอื่นไม่ได้

## *Using Generics with Dart Collections*
Collections เป็นการเรียกกลุ่มของประเภทตัวแปรที่เก็บข้อมูลหลายๆตัวไว้ด้วยกัน ในที่นี้จะยกตัวอย่าง การใช้งาน Generics กับ Collections in Dart อยู่ 2 ชนิด คือ Map และ List 

> Collection Syntax: `Collection_name <data_type> identifier= new
> Collection_name<data_type>`

 - Generic Map
			 

> Map Syntax: `Map <Key_type, value_type>`

			 

```  dart
	    Map <String,int> mp={'Ankur':1,'Arnav':2,'Shivam':3}; 
		
	 // Map <String,int> mp2={'Ankur':1,'Arnav':2,'Shivam':'Three'};    // error
	    Map  mp2={'Ankur':1,'Arnav':2,'Shivam':'Three'};
		
            print('Map :$mp'); 
            print('Map2 :$mp2');
   ```

    Output => Map :{Ankur: 1, Arnav: 2, Shivam: 3}
		Map2 :{Ankur: 1, Arnav: 2, Shivam: Three}
เกิด error เนื่องจากไม่สามารถกำหนดค่าประเภท `String` ให้กับตัวแปรประเภท `int` ได้
 - Generic List

>  List Syntax: `var list_name = List(initial_size)`
>
> 
```  dart
	main() { 
	  	List<int> listEx = []; 
	  	listEx.add(341); 
	  	listEx.add(1); 
	  	// listEx.add("Three");  // error
	    
	  	// วนลูปพิมพ์ค่าใน list listEx 
	  	for (int element in listEx) { 
	     	print(element); 
	  	} 
	}
   ```

    Output => 341
    		1
เมื่อเพิ่ม 'Three' เข้าไปใน List จะเกิด error เนื่องจากไม่สามารถกำหนดค่าประเภท `String` ให้กับตัวแปรประเภท `int` ได้
```  dart
	void main() { 
	   	List <String> logTypes = []; 
	   	logTypes.add("WARNING"); 
	   	logTypes.add("ERROR"); 
	   	// logTypes.add(1); // error  
	   
	   	// วนลูปพิมพ์ค่าใน list 
	   	for (String type in logTypes) { 
	      	print(type); 
	  	} 
	}
   ```

      Output => WARNING
    	    ERROR
เมื่อเพิ่ม 1 เข้าไปใน List จะเกิด error เนื่องจากไม่สามารถกำหนดค่าประเภท `int` ให้กับตัวแปรประเภท `String` ได้

## *Example 6*
```  dart
	abstract class Shape {
 		 double get area;
	}

	class Circle extends Shape {
	  	double radius;
	
	  	Circle({required this.radius});
	
	  	@override
	  	double get area => 3.14 * radius * radius;
	}
	
	class Square extends Shape {
	  	double length;
		Square({required this.length});
	
	  	@override
	  	double get area => length * length;
	}
	
	class Region<T extends Shape> {
	  	List<T> shapes;
	  	Region({required this.shapes});
	
	  	double get area {
	    	double totalArea = 0;
	    	for (var shape in shapes) {
	      		totalArea += shape.area;
	    	}
	    	return totalArea;
	  	}
	}
	
	void main() {
	  	var circle = Circle(radius: 10);
	  	var square = Square(length: 20);
	  	// create a list of Shape objects
	  	var region = Region(shapes: [circle, square]);
	  	print(region.area);
	}
   ```

    Output => 714

กำหนด `class Region<T extends Shape>` หมายความว่า ตัวแปรที่ส่งให้ Class Region ต้องเป็นประเภท Shape นั่นคือ Circle และ Square

## Generics in Java Python and C
										

Dart

```  dart
	 class Data<T> {
	  	T data;
	  	Data(this.data);
	}
	void main() {
	  	// create an object of type int and double
	  	Data<int> intData = Data<int>(10);
   /* Dart มี Type Inference ที่ช่วยในการระบุประเภทข้อมูลอัตโนมัติ สามารถเขียนได้อีกแบบ คือ
	  	Data  intData = Data(10);
   */
      		Data<double> doubleData = Data<double>(10.5);
   /* 		Data  DoubleData = Data(10.5); */
	 
	  	print("IntData: ${intData.data}");
		print("DoubleData: ${doubleData.data}");
	}

   ```

 - Dart VS Java
 
Java
```  java
	class Data<T> {
	    	private T data;
	    	public Data(T data) {
	        	this.data = data;
	    	}
	    	public T getData() {
	        	return data;
	    	}
	}
	
	 public class Main {
	    	public static void main(String[] args) {
	        // create an object of type Integer and Double
	        
	        // Type Inference
	        Data<Integer> intData = new Data<>(10); 
	        // Data<int> intData = new Data<>(10);       	// error
	        Data<Double> doubleData = new Data<>(10.5);
	        // Data<double> doubleData = new Data<>(10.5);  // error
	
	        // print the data
	        System.out.println("IntData: " + intData.getData());
	        System.out.println("DoubleData: " + doubleData.getData());
	    	}
	}
   ```

Dart และ Java มีคุณสมบัติ Type Inference คือ สามารถละการเขียน `<>` ได้ทั้งหมด 
สิ่งที่แตกต่าง คือ ชนิดของข้อมูลที่ใช้กับ generic ใน Java ต้องเป็น object reference type เท่านั้น ชนิดข้อมูล primitive data type ใน Java ใช้กับ generic ไม่ได้
 - Dart VS Python

Python
```  Python
	class  Data:
		def  __init__(self,  data):
			self.data  = data
	def  main():
	#create an object of type int and double
		int_data =  Data(10)
		double_data =  Data(10.5)
	# print the data
		print("IntData:", int_data.data)
		print("DoubleData:", double_data.data)

	if __name__ ==  "__main__":
		main()
```  
ใน Python การใช้งานไม่ต้องระบุ generics เนื่องจาก Python ให้ความยืดหยุ่นกับชนิดข้อมูลอยู่แล้ว function สามารถรับค่าที่ชนิดข้อมูลต่างกันได้เลย
 - Dart VS C
 
 Dart
 ```  Dart
		 class ClassGenerics<T> {
		  T data;
		  ClassGenerics(this.data);
		}

		void main() {
		  ClassGenerics int_ = ClassGenerics(42);
		  print('Integer: ${int_.data}');

		  ClassGenerics float_ = ClassGenerics(3.14);
		  print('Float: ${float_.data}');
		}
```  

    Output => Integer: 42
    	    Float: 3.14

 C
 ```  C
	 #include <stdio.h>
	// macros
	#define GENERIC(type) type
	
	int main() {
	    GENERIC(int) integer = 42;
	    GENERIC(float) floatingPoint = 3.14;
	
	    printf("Integer: %d\n", integer);
	    printf("Float: %f\n", floatingPoint);
	
	    return 0;
	}
``` 

    Output => Integer: 42
            Float: 3.14

ในภาษา C ไม่มี Generics แต่สามารถใช้ macro ที่สร้างด้วย #define GENERIC เพื่อสร้างโค้ดที่เหมือนกับเป็น Generics ได้

## Advantages of Dart Generics
ความสามารถของ generic ช่วยให้ คนที่เรียกใช้งานเป็นคนกำหนดเองได้ว่า อยากทำงานกับ data type อะไร ช่วยทำให้โค้ดมีความยืดหยุ่น และนำกลับมาใช้ใหม่ได้มากขึ้น

## Slide
- [GenericsinDart.pdf](https://github.com/soonklang/dart-tutorial/files/12774187/GenericsinDart.pdf)
- [GenericsinDart_new.pdf](https://github.com/soonklang/dart-tutorial/files/12883356/GenericsinDart_new.pdf)
- https://drive.google.com/file/d/1Yb91CGyULmnZ1agOMFNe1pB6BKO_wrbB/view?usp=sharing
- https://drive.google.com/file/d/1XzDVM3t6prc_DVQBXWsxIUCHeNhGHNxf/view?usp=sharing
## Video
- [Generics in Dart](https://www.youtube.com/watch?v=I044098K6Fk)
## References

https://dart-tutorial.com/object-oriented-programming/generics-in-dart/

https://dart.dev/guides/language/numbers

https://www.geeksforgeeks.org/dart-collections/

https://www.geeksforgeeks.org/dart-generics/

https://www.tutorialspoint.com/dart_programming/dart_programming_generics.htm

https://www.darttutorial.org/dart-tutorial/dart-generics/

https://www.slingacademy.com/article/python-generic-types-tutorial-examples/

https://www.programiz.com/java-programming/generics#google_vignette

https://docs.oracle.com/javase/tutorial/java/generics/restrictions.html

https://www.geeksforgeeks.org/macros-and-its-types-in-c-cpp/
