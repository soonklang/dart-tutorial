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

    Output : Int: 10
    
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

    Output: 10
			Hello

## *Restricting the Type of Data*
ขณะที่ใช้งาน Generics สามารถจำกัดประเภทของชนิดข้อมูลที่ใช้งานกับ Class หรือ Method ได้โดยใช้คีย์เวิร์ด extends

## Example 4: Generic Class With Restriction
```  dart
// ประกาศ generic class โดยจำกัดประเภทของชนิดข้อมูล
class Data<T extends num> {
  T data;
  Data(this.data);
}

void main() {
  // สร้าง object และกำหนด data type ที่ต้องการ
  Data<int> intData = Data<int>(10);				/* ต้องการทำงานกับ int */
  Data<double> doubleData = Data<double>(10.5);		/* ต้องการทำงานกับ double */

  print("IntData: ${intData.data}");
  print("DoubleData: ${doubleData.data}");

  // Data<String> stringData = Data<String>("Hello");  // error
}
   ```
`<T extends num>` ทำให้     `Class Data()`  ใช้ได้กับ `int` และ `double` เท่านั้น จะใช้กับประเภทอื่นไม่ได้

## *Example 5*: Generic Method With Restriction
```  dart
T getVal<T extends String>(T value1, T value2) {
  return (value1);
}

void main() {
  // เรียกใช้ generic method
  //print("int: ${getAverage<int>(10, 20)}");				// error
  //print("double: ${getAverage<double>(10.5, 20.5)}");		// error
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
	     main() { 
			     //Map <String,int> mp={'Ankur':"one",'Arnav':002,'Shivam':003};    // error
				Map <String,int> mp={'Ankur':1,'Arnav':002,'Shivam':003}; 
			   print('Map :${mp}'); 
		}
   ```

    Output => Map :{Ankur: 1, Arnav: 2, Shivam: 3}
เกิด error เนื่องจากไม่สามารถกำหนดค่าประเภท `String` ให้กับตัวแปรประเภท `int` ได้
 - Generic List

>  List Syntax: `var list_name = List(initial_size)`
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
เกิด error เนื่องจากไม่สามารถกำหนดค่าประเภท `String` ให้กับตัวแปรประเภท `int` ได้
