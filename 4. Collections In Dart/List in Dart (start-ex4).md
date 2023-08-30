# List in Dart (start-ex4)
  List ในภาษา Dart ใช้ในการเก็บข้อมูลหลายๆประเภทในพื้นที่จัดเก็บที่สร้างขึ้น โดยจะเรียงลำดับของข้อมูลด้วย

โดย List จะคล้ายกับ Array ในภาษาโปรแกรมอืนๆ โดยขอยกตัวอย่างภาษา Java แต่จะแตกต่างกันในส่วนของ Array นั้นจำเป็นต้องจัดเก็บข้อมูลประเภทเดียวกัน ไม่สามารถเก็บข้อมูลหรือตัวแปรต่างประเภทกันได้

  *** เช่น เราสามารถเก็บตัวแปรประเภท Int (ซึ่งเป็นตัวเลข) ร่วมกับ String (ซึ่งเป็นตัวอักษร) ได้ใน List ของ Dart แต่ในภาษา Java จำเป็นต้องสร้าง Array แยกกัน เป็น Array ของ Int และ Array ของ String

# Logical ของ List

![image](https://github.com/soonklang/dart-tutorial/assets/141746029/e8eebce2-cf4f-4fc4-85b3-d6ec4319eb11)

อ้างอิง: https://www.geeksforgeeks.org/dart-programming-list/

จากภาพจะเห็นได้ว่าการเก็บข้อมูลนั้นจะเก็บเป็นส่วนๆ โดยจะมีเลข Index ของแต่ละตำแหน่งของข้อมูลที่เราทำการจัดเก็บ การที่จะนำข้อมูลมาแสดงผล จำเป็นต้องใช้เลขตำแหน่ง หรือ Index นั่นเอง

# วิธีการสร้าง List

การสร้าง List เราจะใช้ [] (วงเล็บก้ามปู) ในการ fill ข้อมูล และหากมีการ fill ข้อมูลพร้อมกันหลายๆตัว จำเป็นต้องใส่เครื่องหมาย , (comma) คั่นระหว่างข้อมูล

  // Integer List

    List<int> ages = [10, 30, 23];

  // String List

  การ  fill ข้อมูลประเภท String ต้องใส่เครื่องหมาย ' ' (Single qoute) หรือ " " (Double qoute) ด้วย

    List<String> names = ["Raj", "John", "Rocky"];

  // Mixed List
  
  Ex.1
  
    var mixed = [10, "John", 18.8];
    
   Ex.2
  
    var list = [
      'Car',
      'Boat',
      'Plane',
      ];

*** NOTE : สามารถสร้างเป็น List เปล่าๆขึ้นมาได้ด้วยเช่นกัน

      var scores = [];

# ประเภทของ List

  List ถูกแบ่งออกเป็น 2 ประเภท
  
  1.Fixed Length List (List ที่กำหนดขอบเขต)
  
  2.Growable List (List ที่ไม่มีการกำหนดขอบเขต)

# Fixed Length List

  การสร้าง List โดยกำหนดขอบเขตความยาวของพื้นที่จัดเก็บไว้ก่อน จะไม่สามารเปลี่ยนแปลงหรือเพิ่มความยาวของพื้นที่จัดเก็บได้อีกในภายหลัง

  // Ex

  โดยตัวอย่างนี้คือการประกาศตัวแปร list ที่มีข้อมูลด้านในเป็น 0 ทั้งหมด และมีความยาวที่ 5 (Index ที่ 0-4)
  
    void main() {  
     var list = List<int>.filled(5,0);  
     print(list);  
    }

  Output:

    [0, 0, 0, 0, 0]

  ตัวอย่างนี้จะประกาศตัวแปร gfg ซึ่งเป็น List ที่มีความยาวอยู่ที่ 5 และข้อมูลใน List เป็น null จากนั้นมีการเพิ่มข้อมูลลงใน List 3 ตัว

    void main()
    {
	    List? gfg = List.filled(5, null, growable: false);
	    gfg[0] = 'Geeks';
	    gfg[1] = 'For';
	    gfg[2] = 'Geeks';

	    // Printing all the values in List (แสดงค่าทั้งหมดใน List)
	    print(gfg);

	    // Printing value at specific position (แสดงเฉพาะค่าในตำแหน่งที่ 3 (Index = 2))
	    print(gfg[2]);
    }

Output:

    [Geeks, For, Geeks, null, null]
    Geeks

# Growable List

การสร้าง List โดยที่ไม่ได้มีการกำหนดขอบเขตความยาวของพื้นที่จัดเก็บไว้ก่อน ทำให้สามารเปลี่ยนแปลงหรือเพิ่มความยาวของพื้นที่จัดเก็บได้ และเป็นที่นิยมมากกว่า Fixed Length List

// Ex

    void main() {  
     var list1 = [210,21,22,33,44,55];  
     print(list1);  
    }  

Output:

    [210, 21, 22, 33, 44, 55]

/**/

    void main()
    {
      var gfg = [ 'Geeks', 'For' ];
 
      // Printing all the values in List (แสดงค่าทั้งหมดใน List)
      print(gfg);
 
      // Adding new value in List and printing it (เพิ่มข้อมูลใหม่ลงใน List และแสดงค่าทั้งหมดใน List)
      gfg.add('Geeks'); // list_name.add(value);
      print(gfg);
    }

Output:

    [Geeks, For]
    [Geeks, For, Geeks]

# การเข้าถึงข้อมูลภายใน List

เราสามารถเข้าถึงข้อมูลใน List โดยใช้ Index หรือเลขตำแหน่ง ซึ่งจะเริ่มต้นที่ 0

//EX

ตัวอย่างนี้จะแสดงข้อมูลออกมาทีละตำแหน่งตั้งแต่ 0 จนถึง 5

    void main() {
      var list = [210, 21, 22, 33, 44, 55];

      print(list[0]);
      print(list[1]);
      print(list[2]);
      print(list[3]);
      print(list[4]);
      print(list[5]);
    }

/**/

ตัวอย่างนี้จะแสดงการเข้าถึงข้อมูลในตำแหน่งที่ 3 (Index = 2)

    void main() {
      var scores = [1, 3, 4, 2];
      print(scores[2]);
    }

Output

    4

# การเข้าถึงโดยตำแหน่งใช้ค่าของข้อมูลภายใน List

เราสามารถเข้าถึงตำแหน่งข้อมูลได้เช่นกัน โดย:

    void main() {
      var list = [210, 21, 22, 33, 44, 55];

      print(list.indexOf(22));
      print(list.indexOf(33));
    }

Output:

    2
    3

# การหาความยาวของ List

