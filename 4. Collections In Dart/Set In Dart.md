# Set In Dart
เซต (Set) เป็นโครงสรา้งข้อมูลเก็บค่าหรือข้อมูล ซึ่งไม่สามารถเก็บค่าที่ซ้ำกันได้ในเซต โดยไม่มีการเรียงลำดับของข้อมูลทำงานได้เร็วกว่า list เมือต้องใช้กับข้อมูลขนาดใหญ่
  เซตจะกำหนดด้วยปีกกาใหญ่ {}
  
**List สามารถเพิ่มค่าซ้ำกันได้แต่ Set ไม่สามารถทำได้  
## การสร้างเซต

    var variable_name = <variable_type>{};
หรือ

     Set <variable_type> variable_name = {};
Example 1 สร้างเซตจากสองวิธีที่ต่างกัน

    void main()
    {
    // Declaring set in First Way
    var gfg1 = <String>{'GeeksForGeeks'};
    print("Output of first set: $gfg1");
   
    // Declaring set in Second Way
    Set<String> gfg2 = {'GeeksForGeeks'}; 
    print("Output of second set: $gfg2");
    }
Output

    Output of first set: {GeeksForGeeks}
    Output of second set: {GeeksForGeeks}
Example 2 ลองสร้างและเรียกดูค่าทั้ง Set และ List

    void main()
    {
    // Declaring list with repeated value
    var gfg = ['Geeks','For','Geeks'];
   
    // Printing List
    print("Output of the list is: $gfg");
     
    // Declaring set with repeated value
    var gfg1 = <String>{'Geeks','For','Geeks'}; 
   
    // Printing Set
    print("Output of the set is: $gfg1");
    }
Output

    Output of the list is: [Geeks, For, Geeks]
    Output of the set is: {Geeks, For}
NOTE : ใน Set จะไม่แสดงข้อมูลที่ซ้ำกันอย่างใน List  
## คุณสมบัติของ Dart
first --> แสดงค่าตัวแรกในเซต  
last --> แสดงค่าตัวสุดท้ายในเซต  
isEmpty --> ตรวจว่าใรเซตว่างเปล่าหรือไม่ เป็น True หรือ False  
isNotEmpty --> ตรวจว่าใรเซตว่ามีข้อมูลหรือไม่ เป็น True หรือ False  
length --> แสดง จำนวนของข้อมูลในเซต  
contains --> เช็คข้อมูลในเซตเป็น True หรือ False

    void main(){
    Set<String> fruits = {"Apple", "Orange", "Mango"};
    print(fruits);
    }
    
    print("First Value is ${fruits.first}");
    print("Last Value is ${fruits.last}");
    print("Is fruits empty? ${fruits.isEmpty}");
    print("Is fruits not empty? ${fruits.isNotEmpty}");
    print("The length of fruits is ${fruits.length}");
    print(fruits.contains("Mango"));
Output

    First Value is Apple
    Last Value is Banana
    Is fruits empty? false
    Is fruits not empty? true
    The length of fruits is 4
    true
union --> แสดงค่าทั้งหมดระหว่างสองเซต

    void main() {
      var a = {1, 2, 3};
      var b = {2, 3, 4};
      var c = a.union(b);
      print(c);}
Output

    {1,2,3,4}
## แสดงค่าในเซต
แสดงค่าในเซตด้วยการใช้ loop

    void main(){
     Set<String> fruits = {"Apple", "Orange", "Mango"};
  
     for(String fruit in fruits){
      print(fruit);
     }
      }

## Methods in Set
add() --> เพิ่มค่า  
remove() --> ลบค่า  
addAll() --> เพิ่มค่าหลายตัว


    Set<String> fruits = {"Apple", "Orange", "Mango"};
    fruits.add("Lemon");
    fruits.remove("Apple");
    
    fruit.addAll([strawberry, melon]);}

clear() --> ลบค่าในเซตทั้งหมด  

    fruits.clear();
difference() --> สร้างเซตใหม่ที่ใส่ค่าที่ต่างกันกับอีกเซต  

    Set<String> fruits1 = {"Apple", "Orange", "Mango"};
    Set<String> fruits2 = {"Apple", "Grapes", "Banana"};

    final differenceSet = fruits1.difference(fruits2);
elementAt() --> แสดงค่าที่ระบุ  

    Set<String> days = {"Sunday", "Monday", "Tuesday"};
intersection --> สร้างเซตที่มีค่าซ้ำกัน  

    Set<String> fruits1 = {"Apple", "Orange", "Mango"};
    Set<String> fruits2 = {"Apple", "Grapes", "Banana"};

    final intersectionSet = fruits1.intersection(fruits2);

อ้างอิง  
https://www.geeksforgeeks.org/dart-sets/  
https://dart-tutorial.com/collections/set-in-dart/  
https://www.darttutorial.org/dart-tutorial/dart-set/  
