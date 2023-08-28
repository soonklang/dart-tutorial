# Set In Dart
เซต (Set) เป็นโครงสรา้งข้อมูลเก็บค่าหรือข้อมูล ซึ่งไม่สามารถเก็บค่าที่ซ้ำกันได้ในเซต โดยไม่มีการเรียงลำดับของข้อมูลทำงานได้เร็วกว่า list เมือต้องใช้กับข้อมูลขนาดใหญ่
  เซตจะกำหนดด้วยปีกกาใหญ่ {}
  
**List สามารถเพิ่มค่าซ้ำกันได้แต่ Set ไม่สามารถทำได้
## คุณสมบัติของ Dart
first --> แสดงค่าตัวแรกในเซต  
last --> แสดงค่าตัวสุดท้ายในเซต  
isEmpty --> ตรวจว่าใรเซตว่างเปล่าหรือไม่ เป็น True หรือ False  
isNotEmpty --> ตรวจว่าใรเซตว่ามีข้อมูลหรือไม่ เป็น True หรือ False  
length --> แสดง จำนวนของข้อมูลในเซต  
contains --> เช็คข้อมูลในเซตเป็น True หรือ False

    Set<String> fruits = {"Apple", "Orange", "Mango", "Banana"};
    
    print("First Value is ${fruits.first}");
    print("Last Value is ${fruits.last}");
    print("Is fruits empty? ${fruits.isEmpty}");
    print("Is fruits not empty? ${fruits.isNotEmpty}");
    print("The length of fruits is ${fruits.length}");
    print(fruits.contains("Mango"));

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

