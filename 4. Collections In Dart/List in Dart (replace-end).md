# List in Dart (replace-end)
## การแทนที่ช่วงใน List
เราสามารถแทนที่ค่าในลิสในช่วงที่เราเลือกโดยใช้เม็ดตอด replaceRange() โดยเมดตอทจะทำการลบข้อมูลที่อยู่ในช่วงตำแหน่งเริ่มจนถึงตำแหน่งสิ้นสุดลบด้วยหนึ่งที่ตามเรากำหนด
>Ex
```
void main() {
 List<int> list = [5, 3, 1, 4, 5];
 print("ก่อนใช้ replaceRange ${list}");
 list.replaceRange(1, 4, [8, 2]);
 print("หลังใช้ replaceRange ${list}");
	}
```
>output
```
ก่อนใช้ replaceRange [5, 3, 1, 4, 5]
หลังใช้ replaceRange [5, 8, 2, 5]
```
ในตัวอย่าง เรากำหนดตำแหน่งเริ่มต้นคือตำแหน่งที่ 1 และตำแหน่งสิ้นสุดคือตำแหน่งที่ 4-1 และแทนที่ข้อมูลข้างในด้วยค่า 8,2 
## การลบข้อมูลใน list
การลบข้อมูลใน list มีอยู่สี่วิธี 
| Method | Description |
|:------------|:-------------|
|remove()     | ลบค่ากำหนดออกจาก list| 
|removeAt()   | ลบค่าในตำแหน่งที่กำหนด ออกจาก list| 
|removeLast() | ลบค่าสุดท้ายใน list ออก|
|removeRange()| ลบค่าตามช่วงที่กำหนด    |
#### ตัวอย่างที่1:remove()
วิธีนี้จะใช้เม็ดตอด remove() เป็นการกำหนดค่าที่ต้องการลบออกจาก list 
>Ex
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ : ${list}");
  list.remove(30);
  print("หลังใช้ : ${list}");
}
```
>output
```
ก่อนใช้ : [10, 20, 30, 40, 50]
หลังใช้ : [10, 20, 40, 50]
```
แต่วิธีนี้นั้นจะทำการลบค่าที่ตรงกับค่ากำหนดค่าแรกที่เจอเท่านั้น จะไม่ทำการลบค่าที่ตรงกับค่าที่กำหนดที่เหลือ
>Ex
```
void main() {
  var list = [10, 20, 30, 40, 50,20,60,20];
  print("ก่อนใช้ : ${list}");
  list.remove(20);
  print("หลังใช้ : ${list}");
}
```
เห็นได้ว่า ค่า20 ใน list ถูกลบไปเพียงแค่ค่าเดียวนั้นคือค่าแรกที่เจอแต่ค่า 20 ตำแหน่งอืนยังอยู่
>output
```
ก่อนใช้ : [10, 20, 30, 40, 50, 20, 60, 20]
หลังใช้ : [10, 30, 40, 50, 20, 60, 20]
```
#### ตัวอย่างที่2:removeAt()
วิธีนี้จะใช้เม็ดตอด removeAt() วิธีนี้จะเป็นการลบค่าตามตำแหน่งที่กำหนดและตำแหน่งแรกของ list ใน Dart คือ 0
>Ex 1.
```
void main() {
  var list = [10, 11, 12, 13, 14];
  print("ก่อนใช้ : ${list}");
  list.removeAt(3);
  print("หลังใช้ : ${list}");
}
```
>output
```
ก่อนใช้ : [10, 11, 12, 13, 14]
หลังใช้ : [10, 11, 12, 14]
```
ตำแหน่งที่กำหนดคือ ตำแหน่งที่3 นั้คือค่า13
>Ex 2.
```
 List<Map<String, dynamic>> people = [
  {'name': 'John', 'age': 30},
  {'name': 'Bob', 'age': 50},
  {'name': 'Tom', 'age': 14},
  {'name': 'Donald', 'age': 3}
];

void main() {
  print("ก่อนใช้: ${people}");
  people.removeAt(2);
  print("หลังใช้: ${people}");
}
```
>output
```
ก่อนใช้: [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}, {name: Donald, age: 3}]
หลังใช้: [{name: John, age: 30}, {name: Bob, age: 50}, {name: Donald, age: 3}]
```
#### ตัวอย่างที่3:removeLast()
วิธีนี้จะใช้เม็ดตอด removeLast() วิธีนี้จะลบค่าสุดท้ายออกจาก list
>Ex 1.
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ :${list}");
  list.removeLast();
  print("หลังใช้ :${list}");
}
```
>output
```
ก่อนใช้ :[10, 20, 30, 40, 50]
หลังใช้ :[10, 20, 30, 40]
```

>Ex 2.
```
final List<Map<String, dynamic>> people = [
  {'name': 'John', 'age': 30},
  {'name': 'Bob', 'age': 50},
  {'name': 'Tom', 'age': 14},
  {'name': 'Donald', 'age': 3}
];

void main() {
  print("ก่อนใช้ : ${people}");
  people.removeLast();
  print("หลังใช้ : ${people}");
}
```
>output
```
ก่อนใช้ : [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}, {name: Donald, age: 3}]
หลังใช้ : [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}]
```
#### ตัวอย่างที่4:removeRange()
วิธีนี้จะใช้เม็ดตอด removeRange() เป็นการลบข้อมูลในตำแหน่งที่กำหนดเป็นช่วงจนถึงตำแหน่งสุดท้ายที่กำหนด ตำแหน่งที่จะถูกลบนั้นคือตำแหน่งแรกที่กำหนดและ ตำแหน่งสุดท้ายที่กำหนด -1ตำแหน่ง
>Ex 1.
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ :${list}");
  list.removeRange(1, 3);
  print("หลังใช้ :${list}");
}
```
>output
```
ก่อนใช้ :[10, 20, 30, 40, 50]
หลังใช้ :[10, 40, 50]
```
ช่วงที่กำหนดคือตำแหน่งที่ 1และตำแหน่งสุดท้ายคือ ตำแหน่งที่ 3-1 นั้นคือค่า20 และ30 ถูกลบ
>Ex 2.
```
final myList = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'];

void main(){
  print("ก่อนใช้ : ${myList}");
  myList.removeRange(2, 6);
  print("หลังใช้ : ${myList}");
}
```
>output
```
ก่อนใช้ : [a, b, c, d, e, f, g, h]
หลังใช้ : [a, b, g, h]
```
#### การลบข้อมูลใน list ในภาษาอื่นๆ
ในภาษา Java นั้นสามารถใช้ วิธีการแบบภาษา Dart ได้แต่สามารถใช้ได้เพียงเม็ดตอด remove() เท่านั้น
และ C นั้นไม่สามารถทำได้
>Ex Java.
```
import java.util.*;
  
public class GFG {
    public static void main(String[] args)
    {
  
        // Declare an empty List of size 5
        List<String> list = new ArrayList<String>(5);
  
        // Add elements to the list
        list.add("Welcome");
        list.add("to");
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
  
        // Index from which you want
        // to remove element
        int index = 2;
  
        // Initial list
        System.out.println("Initial List: " + list);
  
        // remove element
        list.remove(index);
  
        // Final list
        System.out.println("Final List: " + list);
    }
}
```
>output
```
Initial List: [Welcome, to, Geeks, for, Geeks]
Final List: [Welcome, to, for, Geeks]
```
ส่วนใน Python นั้นมีคำสั่งที่ใช้งานคล้าย ภาษา Dart ได้
>EX 1 remove().
ใช้งานเหมืนกับ remove() ใน Dart 
```
myList = ["Bran",11,22,33,"Stark",22,33,11]
 
myList.remove(22)
 
myList
```
>output
```
[‘Bran’, 11, 33, ‘Stark’, 22, 33, 11]
```
>EX 2 pop().
ใช้งานเหมืนกับ removeAt() ใน Dart 
```
myList = ["Bran",11,22,33,"Stark",22,33,11]
 
myList.pop(1)
myList
```
>output
```
 [‘Bran’, 22, 33, ‘Stark’, 22, 33, 11]
```
>EX 3 del.
ใช้งานเหมืนกับ removeRange() ใน Dart 
```
myList = ["Bran",11,22,33,"Stark",22,33,11]
 
del myList[1:4]
 
myList
```
>output
```
[‘Bran’,"Stark",22, 33, 11]
```
## Loops In List
การพิมพ์ค่าใน list โดยใช้ loop สามารถใช้ for loop ,for each loop หรื่อloop อื่นๆ ได้
>Ex.
```
void main() {
  List<int> list = [10, 20, 30, 40, 50];
  list.forEach((n) => print(n));
}
```
>output
```
10
20
30
40
50
```
#### Loops In List ใน Java และ Python
ใน java และ python ก็สามารถใช้ loop ในการพิมพ์ค่าใน list ได้เช่นกัน
>Ex Java
```
import java.util.*;
 
class GFG {
 
    public static void main(String args[])
    {
        List<String> myList = new ArrayList<String>();
        myList.add("A");
        myList.add("B");
        myList.add("C");
        myList.add("D");
        for (int i = 0; i < myList.size(); i++) {
            System.out.println(myList.get(i));
        }
    }
}
```
>output
```
A
B
C
D
```
>Ex Python
```
thislist = ["apple", "banana", "cherry"]
[print(x) for x in thislist]
```
>output
```
apple
banana
cherry
```
## การเปลี่ยนค่าทั้งหมดใน list โดยการใช้โอเปอร์เรเตอร์ต่างๆ
เราสามารถเพิ่มลดค่าใน list ทั้งหมดพร้อมกันได้ เช่นการเพิ่มค่าทั้งหมดในลิสโดยการคูณสอง
>Ex 1.
```
void main() {
  List<int> list = [10, 20, 30, 40, 50];
  var douledList = list.map((n) => n * 2);

  print((douledList));
}
```
>output
```
(20, 40, 60, 80, 100)
```
หรือลดค่าทั้งหมดลงไป 4
>Ex 2.
```
void main() {
  List<int> list = [10, 20, 30, 40, 50];
  var douledList = list.map((n) => n - 4);

  print((douledList));
}
```
>output
```
(6, 16, 26, 36, 46)
```
## รวม list เข้าด้วยกัน ใน Drat
การนำ list มารวมเข้าด้วยกัน ใน Dart สามารถทำได้ หลายวิธี
#### ตัวอย่างที่1 :ใช้เม็ดตอด addAll() 
>Ex.
```
// Main function
main() {
    
  // Creating lists
  List gfg1 = ['Welcome','to'];
  List gfg2 = ['GeeksForGeeks'];
    
  // Combining lists
  gfg1.addAll(gfg2);
    
  // Printing combined list
  print(gfg1);
}
```
>output
```
[Welcome, to, GeeksForGeeks]
```
#### ตัวอย่างที่2 :ใช้เม็ดตอด expand() 
>Ex.
```
// Main function
main() {
    
  // Creating lists
  List gfg1 = ['Welcome'];
  List gfg2 = ['to'];
  List gfg3 = ['GeeksForGeeks'];
    
  // Combining lists
  var newgfgList = [gfg1, gfg2, gfg3].expand((x) => x).toList();
    
  // Printing combined list
  print(newgfgList);
}
```
>output
```
[Welcome, to, GeeksForGeeks]
```
#### ตัวอย่างที่3 :ใช้โอเปอร์เรเตอร์ +
วิธีนี้ถูกอัพเดทเข้ามา ใน Dart 2.0
>Ex.
```
// Main function
main() {
    
  // Creating lists
  List gfg1 = ['Welcome'];
  List gfg2 = ['to'];
  List gfg3 = ['GeeksForGeeks'];
    
  // Combining lists
  var newgfgList = gfg1 + gfg2 + gfg3;
    
  // Printing combined list
  print(newgfgList);
}
```
>output
```
[Welcome, to, GeeksForGeeks]
```
#### ตัวอย่างที่3 :ใช้  spread operator
วิธีนี้ถูกอัพเดทเข้ามา ใน Dart 2.3
>Ex.
```
// Main function
main() {
    
  // Creating lists
  List gfg1 = ['Welcome'];
  List gfg2 = ['to'];
  List gfg3 = ['GeeksForGeeks'];
    
  // Combining lists
  var newgfgList = [...gfg1, ...gfg2, ...gfg3];
    
  // Printing combined list
  print(newgfgList);
}
```
>output
```
[Welcome, to, GeeksForGeeks]
```
#### ตัวอย่างการรวม list เข้าด้วยกัน ในภาษาอื่นๆ
ในภาษา Python สามารถใช้โอเปอร์เรเตอร์ + ได้เช่นกันกับภาษา Dart และยังมีวิธีอื่นเช่นการใช้ลูปหรือเม็ดตอด extend()
>Ex การรวม list ใน Python.
```
test_list3 = [1, 4, 5, 6, 5]
test_list4 = [3, 5, 7, 2, 5]
 
# using list.extend() to concat
test_list3.extend(test_list4)
 
# Printing concatenated list
print ("Concatenated list using list.extend() : "
                            + str(test_list3))
```
>output
```
Concatenated list using list.extend() : [1, 4, 5, 6, 5, 3, 5, 7, 2, 5]
```
ในภาษา Java สามารถใช้เม็ดตอด addAll() เดียวกับ Dart หรือใช้ loop ในการรวม  list
## การใส่เงื่อนไขใน list
ในภาษา Dart เราสามารถตั้งเงื่อนไขไว้ภายใน list ซึ่ง ในภาษา Java,C หรือ Python ไม่สามารถทำได้
>Ex
```
void main() {
  bool sad = false;
  var cart = ['milk', 'ghee', if (sad) 'Beer'];
  print(cart);
}
 
```
>Output
```
[milk, ghee]
```
จากในตัวอย่างหาก ```bool sad = true```output ที่ได้จะเท่ากับ ```[milk, ghee ,Beer]```
## ตำแหน่งใน list ของ Drat
ในภาษา Dart เราสามารถใช้ตำแหน่งในการเป็นฟิวเตอร์ ในการหาข้อมูลที่ต้องการได้ ในตัวอย่างต่อไปนี้เลขคู่เท่านั้นที่จะถูกกรอง
>Ex
```
void main(){
List<int> numbers = [2,4,6,8,10,11,12,13,14];

List<int> even = numbers.where((number)=> number.isEven).toList(); 
print(even);
}
```
>output
```
[2, 4, 6, 8, 10, 12, 14]
```
## อ้างอิง
https://dart-tutorial.com/collections/list-in-dart/
https://api.dart.dev/stable/1.20.0/dart-core/List/replaceRange.html
https://www.kindacode.com/article/how-to-remove-items-from-a-list-in-dart/
https://www.geeksforgeeks.org/list-removeint-index-method-in-java-with-examples/
https://www.edureka.co/blog/python-list-remove/
https://www.w3schools.com/python/python_lists_loop.asp
https://www.geeksforgeeks.org/iterate-through-list-in-java/
https://www.geeksforgeeks.org/how-to-combine-lists-in-dart/
https://www.geeksforgeeks.org/python-ways-to-concatenate-two-lists/
https://www.digitalocean.com/community/tutorials/merge-two-lists-in-jav
## Link VDO :[List in Dart (replace-end)](https://www.youtube.com/watch?v=2eN2VNHVvsc)
## Link Slide : [List in Dart (replace-end)](https://github.com/SuwatchaChaikamhang/Slidepl/raw/main/List-in-Dart-replace-end%20(2).pptx)
