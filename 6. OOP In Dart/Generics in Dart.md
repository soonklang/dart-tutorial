# *Generics in Dart*
Generics เป็นวิธีการสร้าง Class, Function หรือ Method ที่สามารถทำงานได้กับข้อมูล (Objects)
ประเภทต่างๆ ให้มีลักษณะ Dynamic ตามการเรียกใช้งาน โดยหลักการคือ ให้ผู้เรียกใช้เป็นคนกำหนดเองว่าdata type ที่จะทำงานด้วยคืออะไร

## *Syntax*

     class ClassName<T> {
          // code
     }
 < > เรียก ตัวดำเนินการ diamond

> T ภายในเครื่องหมาย `< >` จะอธิบายในหัวข้อ Generics Type Variable

## *Example1* : Without Using Generics

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

## *Example2* : Using Generics

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

## *Example 3*: Generic Method With Multiple Parameters
หากต้องการ Generics Type มากกว่า1ตัว ให้คั่น generic แต่ละตัวด้วย comma (,)
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
ขณะที่ใช้งาน Generics สามารถจำกัดประเภทของชนิดข้อมูลที่ใช้งานกับ class หรือ method ได้โดยใช้คีย์เวิร์ด extends

## Example 4: Generic Class With Restriction
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
    Output => IntData: 10
    	DoubleData: 10.5
`<T extends num>` ทำให้     `Class Data()`  ใช้ได้กับ `int` และ `double` เท่านั้น จะใช้กับประเภทอื่นไม่ได้

## *Example 5*: Generic Method With Restriction
```  dart
		T getVal<T extends String>(T value1, T value2) {
		  return (value1);
		}
		
		void main() {
		  // เรียกใช้ generic method
		  //print("int: ${getAverage<int>(10, 20)}");			// error
		  //print("double: ${getAverage<double>(10.5, 20.5)}");		// error
		  print("getString: ${getVal<String>("ten point five", "twenty point five")}");
		}
```

    Output => getString: ten point five
`<T extends String>` ทำให้ `Method getVal()` ใช้ได้กับ `String` เท่านั้น จะใช้กับประเภทอื่นไม่ได้

## *Using Generics with Dart Collections*
Collections เป็นการเรียกกลุ่มของประเภทตัวแปรที่เก็บข้อมูลหลายๆตัวไว้ด้วยกัน ในที่นี้จะยกตัวอย่าง การใช้งาน Generics กับ Collections in Dart อยู่ 2 ชนิด คือ Map และ List 

 - Generic Map
			 

> Map Syntax: `Map <Key_type, value_type>`

			 

```  dart
	     main() { 
		//Map <String,int> mp={'Ankur':'one','Arnav':002,'Shivam':003};    // error
		Map <String,int> mp={'Ankur':1,'Arnav':002,'Shivam':003}; 
		print('Map :${mp}'); 
             }
   ```

    Output => Map :{Ankur: 1, Arnav: 2, Shivam: 3}
เกิด error เนื่องจากไม่สามารถกำหนดค่า value_type 'one' ของ key_type 'Ankur' ที่เป็นประเภท `String` ให้กับตัวแปรประเภท `int` ได้

 - Generic List

>  List Syntax: `var list_name = List(initial_size)`
```  dart
	main() { 
	  List<int> listEx = []; 
	  listEx.add(341); 
	  listEx.add(1); 
	  // listEx.add('Three');  // error
	    
	  // วนลูปพิมพ์ค่าใน list listEx 
	  for (int element in listEx) { 
	     print(element); 
	  } 
	}
   ```

    Output => 341
    	   1
เกิด error เนื่องจากไม่สามารถกำหนดค่า 'Three' ที่เป็นประเภท `String` ให้กับตัวแปรประเภท `int` ได้

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
		// สร้าง list ของ Shape objects
		var region = Region(shapes: [circle, square]);
		print(region.area);
	}
   ```

 
    Output => 714
 

กำหนด `<T extends Shape>` T เป็น subtype ของ `Shape` class คือ Circle และ Square นั่นเอง
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
   /* Dart มี Type Inference ที่ช่วยในการระบุประเภทข้อมูลอัตโนมัติ จึงสามารถเขียนโดยการละ <> ได้ คือ
	  Data  intData = Data(10);
   */
      Data<double> doubleData = Data<double>(10.5);
   /*     Data  DoubleData = Data(10.5); */
	  
	  print("IntData: ${intData.data}");
	  print("DoubleData: ${doubleData.data}");
	}

   ```
Output => IntData: 10
    	  DoubleData: 10.5
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
	        Data<Double> doubleData = new Data<>(10.5);
	
	        System.out.println("IntData: " + intData.getData());
	        System.out.println("DoubleData: " + doubleData.getData());
	    }
	}
   ```
Output => IntData: 10
    	  DoubleData: 10.5
Dart และ Java มีการประกาศใช้ Generics โดยใช้เครื่องหมาย  `<T>` เช่นเดียวกัน แต่การสร้าง object นั้น Java สร้างโดยใช้คำสั่ง new ซึ่ง Dart สามารถละ new ได้
ทั้ง Dart และ Java มีคุณสมบัติ Type Inference แต่แตกต่างกันเล็กน้อยในวิธีการเขียน โดย Dart สามารถนำ `<>` ออกได้ท้งหมด แต่ใน Java ยังคงต้องมี `<>` ไว้ แต่สามารถละการระบุ type ใน `<>` หน้า `(parameter)` ได้

 - Dart VS Python

Python
```  Python
	class  Data:
		def  __init__(self,  data):
			self.data  = data
	def  generic_method(value):
		return value
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
Output => IntData: 10
    	  DoubleData: 10.5
ใน Python การใช้งาน generics การประกาศ object การใช้งาน function/method ต่าง ๆ ไม่ต้องระบุประเภทข้อมูลอย่างในภาษา Dart 

 - Dart VS C
 

 C
 ```  C
	#include <stdio.h>
	// macro
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
ในภาษา C ไม่มี Generics สามารถใช้ Macro เพื่อสร้างโค้ดที่เป็น Generics ได้ ดังนั้น ความแตกต่างระหว่าง Dart กับ C คือ Dart มี Generics ใช้ แต่ C ต้องใช้ Macro แทน

## References
