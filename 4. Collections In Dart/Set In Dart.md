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
    
Finding --> ค้นหาค่าใร Set
    
    var gfg = <String>{'Hello Geek'};

    // Finding the element in the set
    bool check = gfg.contains("GeeksForGeeks");
   
    // Printing boolean value
    print("The value of check is: $check");
Output

    The value of check is: true
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

elementAt() --> แสดงค่าที่ระบุ  

    Set<String> days = {"Sunday", "Monday", "Tuesday"};

## การแปลง Set ให้เป็น List ในภาษา Dart

    void main()
    {
    // Declaring set with value
    var gfg = <String>{'Hello Geek',"GeeksForGeeks","Geek1","Geek2","Geek3"}; 
   
    // Printing values in set
    print("Values in set are:");
    print(gfg);
   
    print("");
   
    // Converting Set to List
    List<String> gfg_list = gfg.toList();
   
    // Printing values of list
    print("Values in the list are:");
    print(gfg_list);
    }
Output

    Values in set are:
    {Hello Geek, GeeksForGeeks, Geek1, Geek2, Geek3}

    Values in the list are:
    [Hello Geek, GeeksForGeeks, Geek1, Geek2, Geek3]
## การแปลง Set ให้เป็น map ในภาษา Dart

    void main()
    {
    // Declaring set 1 with value
    var gfg = <String>{"GeeksForGeeks","Geek1","Geek2","Geek3"};
   
    var geeksforgeeks = gfg.map((value) {
    return 'mapped $value';
    });
    print("Values in the map:");
    print(geeksforgeeks);
     }
Output

    Values in the map:
    (mapped GeeksForGeeks, mapped Geek1, mapped Geek2, mapped Geek3)

## Set Operations in Dart

    void main()
    {
    // Declaring set 1 with value
    var gfg1 = <String>{"GeeksForGeeks","Geek1","Geek2","Geek3"};
   
    // Printing values in set
    print("Values in set 1 are:");
    print(gfg1);
   
    print("");
     
    // Declaring set 2 with value
    var gfg2 = <String>{"GeeksForGeeks","Geek3","Geek4","Geek5"};
   
    // Printing values in set
    print("Values in set 2 are:");
    print(gfg2);
   
    print("");
   
   
    // Finding Union
    print("Union of two sets is ${gfg1.union(gfg2)} \n");
   
    // Finding Intersection
    print("Intersection of two sets is ${gfg1.intersection(gfg2)} \n");
   
    // Finding Difference
    print("Difference of two sets is ${gfg2.difference(gfg1)} \n");
     
    }
Output

    Values in set 1 are:
    {GeeksForGeeks, Geek1, Geek2, Geek3}

    Values in set 2 are:
    {GeeksForGeeks, Geek3, Geek4, Geek5}

    Union of two sets is {GeeksForGeeks, Geek1, Geek2, Geek3, Geek4, Geek5} 

    Intersection of two sets is {GeeksForGeeks, Geek3} 

    Difference of two sets is {Geek4, Geek5} 
สามารถใช้ Set Operations ได้กับหลาย Set
Example:

    void main()
    {
    // Declaring set 1 with value
    var gfg1 = <String>{"GeeksForGeeks","Geek1","Geek2","Geek3"};
   
    // Declaring set 2 with value
    var gfg2 = <String>{"GeeksForGeeks","Geek3","Geek4","Geek5"};
   
    // Declaring set 3 with value
    var gfg3 = <String>{"GeeksForGeeks","Geek5","Geek6","Geek7"};
   
    // Finding Union
    print("Union of two sets is ${gfg1.union(gfg2).union(gfg3)}\n");
   
    // Finding Intersection
    print("Intersection of two sets is ${gfg1.intersection(gfg2).intersection(gfg3)}\n");
   
    // Finding Difference
    print("Difference of two sets is ${gfg2.difference(gfg1).difference(gfg3)}\n");
    }
Output

    Union of two sets is {GeeksForGeeks, Geek1, Geek2, Geek3, Geek4, Geek5, Geek6, Geek7} 

    Intersection of two sets is {GeeksForGeeks} 

    Difference of two sets is {Geek4} 
อ้างอิง  
https://www.geeksforgeeks.org/dart-sets/  
https://dart-tutorial.com/collections/set-in-dart/  
https://www.darttutorial.org/dart-tutorial/dart-set/  
