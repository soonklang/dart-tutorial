# Set In Dart
เซต (Set) เป็นโครงสรา้งข้อมูลเก็บค่าหรือข้อมูล ซึ่งไม่สามารถเก็บค่าที่ซ้ำกันได้ในเซต โดยไม่มีการเรียงลำดับของข้อมูลทำงานได้เร็วกว่า list เมือต้องใช้กับข้อมูลขนาดใหญ่
  เซตจะกำหนดด้วยปีกกาใหญ่ {}
    
## การสร้าง Set
```dart
    var variable_name = <variable_type>{};
```
หรือ
```dart
     Set <variable_type> variable_name = {};
```
Note : List สามารถเพิ่มค่าซ้ำกันได้แต่ Set ไม่สามารถทำได้  
Example 1 สร้าง Set จากสองวิธีที่ต่างกัน
```dart
    void main()
    {
    // Declaring set in First Way
    var gfg1 = <String>{'GeeksForGeeks'};
    print("Output of first set: $gfg1");
   
    // Declaring set in Second Way
    Set<String> gfg2 = {'GeeksForGeeks'}; 
    print("Output of second set: $gfg2");
    }
```
Output
```dart
    Output of first set: {GeeksForGeeks}
    Output of second set: {GeeksForGeeks}
```
Example 2 ลองสร้างและเรียกดูค่าทั้ง Set และ List
```dart
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
```
Output
```dart
    Output of the list is: [Geeks, For, Geeks]
    Output of the set is: {Geeks, For}
```
NOTE : ใน Set จะไม่แสดงข้อมูลที่ซ้ำกันอย่างใน List  
## Set ในภาษา  C

  ในโครงสร้างภาษา C ไม่มี Set อาจจะต้องใช้การเขียนฟังก์ชันเอง เพื่อสร้างเซตใน C ได้โดยใช้อาร์เรย์ข้อมูลเพื่อเก็บสมาชิกของเซตเอง  
## Set ในภาษา Java  

  เป็น Interface ที่ใช้จัดเก็บข้อมูลในรูปของการอ้างถึงสืบทอดมาจาก Collection จากชนิดต่าง ๆ HashSet ไม่อนุญาติใช้เก็บข้อมูลที่ซ้ำกันได้ถ้า Add ข้อมูลลงไปมันจะทับตัวเดิม และลำดับของข้อมูลจะไม่มีความสำคัญ  
  การประกาศและใช้งาน HashSet  

  ในการใช้งาน HashSet เพื่อเก็บข้อมูลที่ไม่ซ้ำกันเราจะต้องประกาศมันก่อน นี่เป็นรูปแบบที่ง่ายที่สุดในการประกาศออบเจ็ค HashSet ในภาษา Java  
```java
    HashSet<E> set = new HashSet<E>();
```
  ในรูปแบบการใช้งานเป็นการประกาศออบเจ็ค HashSet สำหรับเก็บข้อมูลประเภท E โดยที่ E นั้นสามารถเป็นคลาสใดๆ ในภาษา Java  
  เนื่องจาก HashSet นั้นเป็นคลาสที่ Implement มาจากอินเตอร์เฟซ Set<E> ดังนั้นในการประกาศออบเจ็ค เราสามารถใช้อินเตอร์เฟซ Set เป็นประเภทของออบเจ็คได้ดังนี้  
```java
    Set<E> set = new HashSet<E>();
```
  สำหรับตัวอย่างแรกในการใช้งาน HashSet เรามาใช้มันเก็บชื่อของสีซึ่งมีค่าเป็น String และเราจะแนะนำให้คุณรู้กับเมธอดพื้นฐานของ Set นี่เป็นตัวอย่าง  
  ```java
    import java.util.HashSet;
    public class HashSetEx1 {
    public static void main(String[] args) {
        HashSet<String> names = new HashSet<String>();

        // Add three names to set
        names.add("Metin");
        names.add("Jacob");
        names.add("Chris");

        // Count values in set
        System.out.println("Size: " + names.size());

        // Add same value in set
        names.add("Metin");
        System.out.println("Size: " + names.size());

        // Check if values are in the set
        System.out.println("Contain Metin?: " + names.contains("Metin"));
        System.out.println("Contain Foo?: " + names.contains("Foo"));

        // Remove item from the set
        names.remove("Chris");
        System.out.println("Size: " + names.size());

        // Remove all values from set
        names.clear();
        System.out.println("Is the set empty?: " + names.isEmpty());
        System.out.println("Size: " + names.size());
    }}
```
Output
```java
    Size: 3
    Size: 3
    Contain Metin?: true
    Contain Foo?: false
    Size: 2
    Is the set empty?: true
    Size: 0
```
## Set ในภาษา Python

  Set เป็นออบเจ็คจากคลาส set เราสามารถใช้มันเพื่อสร้างออบเจ็คของ Set สำหรับเก็บข้อมูลที่ไม่ซ้ำกัน ในภาษา Python เราสามารถสร้างเซ็ตได้หลายวิธี นี่เป็นตัวอย่างการประกาศ Set ในภาษา Python โดยวิธีต่างๆ  
```Python
    mySet1 = {"value1", "value2", "value3"}
    mySet2 = set(["value1", "value2", "value3"])
    mySet3 = set("value1")
    mySet4 = set()

    print(mySet1)
    print(mySet2)
    print(mySet3)
    print(mySet4)
```
Output
```Python
    {'value3', 'value1', 'value2'}
    {'value3', 'value1', 'value2'}
    {'1', 'a', 'v', 'u', 'l', 'e'}
    set()
```
NOTE : Set ไม่ได้เก็บข้อมูลในรูปแบบของลำดับ ลำดับที่ได้จากการแสดงผลหรือการวนรอบค่าจะไม่เหมือนกับตอนที่เราเพิ่มเข้าไปยัง Set ดังนั้นคุณไม่ควรยึดติดกับลำดับของข้อมูลใน Set ในการเขียนโปรแกรม  

## คุณสมบัติของ Dart
first --> แสดงค่าตัวแรกในเซต  
last --> แสดงค่าตัวสุดท้ายในเซต  
isEmpty --> ตรวจว่าใรเซตว่างเปล่าหรือไม่ เป็น True หรือ False  
isNotEmpty --> ตรวจว่าใรเซตว่ามีข้อมูลหรือไม่ เป็น True หรือ False  
length --> แสดง จำนวนของข้อมูลในเซต  
contains --> เช็คข้อมูลในเซตเป็น True หรือ False
```dart
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
```
Output
```dart
    First Value is Apple
    Last Value is Banana
    Is fruits empty? false
    Is fruits not empty? true
    The length of fruits is 3
    true
```
Finding --> ค้นหาค่าใน Set
  ```dart
    var gfg = <String>{'Hello Geek'};

    // Finding the element in the set
    bool check = gfg.contains("GeeksForGeeks");
   
    // Printing boolean value
    print("The value of check is: $check");
```
Output
```dart
    The value of check is: false
```
## แสดงค่าใน Set
แสดงค่าใน Set ด้วยการใช้ loop
```dart
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

clear() --> ลบค่าใน Set ทั้งหมด  

    fruits.clear();

elementAt() --> แสดงค่าที่ระบุ  

    Set<String> days = {"Sunday", "Monday", "Tuesday"};
```
## การแปลง Set ให้เป็น List ในภาษา Dart
```dart
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
```
## การแปลง Set ให้เป็น map ในภาษา Dart
```dart
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
```
Output
```dart
    Values in the map:
    (mapped GeeksForGeeks, mapped Geek1, mapped Geek2, mapped Geek3)
```
## Set Operations in Dart  
- Union  
- Intersection  
- Difference  
```dart
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
```
Output
```dart
    Values in set 1 are:
    {GeeksForGeeks, Geek1, Geek2, Geek3}

    Values in set 2 are:
    {GeeksForGeeks, Geek3, Geek4, Geek5}

    Union of two sets is {GeeksForGeeks, Geek1, Geek2, Geek3, Geek4, Geek5} 

    Intersection of two sets is {GeeksForGeeks, Geek3} 

    Difference of two sets is {Geek4, Geek5}
```
สามารถใช้ Set Operations ได้กับหลาย Set
Example:
```dart
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
```
Output
```dart
    Union of two sets is {GeeksForGeeks, Geek1, Geek2, Geek3, Geek4, Geek5, Geek6, Geek7} 

    Intersection of two sets is {GeeksForGeeks} 

    Difference of two sets is {Geek4}
```
อ้างอิง  
https://www.geeksforgeeks.org/dart-sets/  
https://dart-tutorial.com/collections/set-in-dart/  
https://www.darttutorial.org/dart-tutorial/dart-set/  
http://marcuscode.com/lang/java/hashset  
http://marcuscode.com/lang/python/set


## Link VDO
https://youtu.be/f_2FvIE9828
## power point
[set in Dart slide](https://github.com/korapan/Set_in_Dart/raw/main/Set%20in%20Dart.pptx)

