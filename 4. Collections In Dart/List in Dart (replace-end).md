# List in Dart (replace-end)
# การแทนที่ช่วงใน List
เราสามารถแทนที่ค่าในลิสในช่วงที่เราเลือกโดยใช้เม็ดตอด replaceRange() โดยเมดตอทจะทำการลบข้อมูลที่อยู่ในช่วงตำแหน่งเริ่มจนถึงตำแหน่งสิ้นสุดที่ตามเรากำหนด
#### Ex
```
void main() {
 List<int> list = [5, 3, 1, 4, 5];
 print("ก่อนใช้ replaceRange ${list}");
 list.replaceRange(1, 4, [8, 2]);
 print("หลังใช้ replaceRange ${list}");
	}
```
#### output
```
ก่อนใช้ replaceRange [5, 3, 1, 4, 5]
หลังใช้ replaceRange [5, 8, 2, 5]
```
ในตัวอย่าง เรากำหนดตำแหน่งเริ่มต้นคือตำแหน่งที่ 1 และตำแหน่งสิ้นสุดคือตำแหน่งที่ 4 และแทนที่ข้อมูลข้างในด้วยค่า 8,2 
# การลบข้อมูลใน list
การลบข้อมูลใน list มีอยู่สี่วิธี 
| Method | Description |
|:------------|:-------------|
|remove()     | ลบค่ากำหนดออกจาก list| 
|removeAt()   | ลบค่าในตำแหน่งที่กำหนด ออกจาก list| 
|removeLast() | ลบค่าสุดท้ายใน list ออก|
|removeRange()| ลบค่าตามช่วงที่กำหนด    |
### ตัวอย่างที่1:remove()
วิธีนี้จะใช้เม็ดตอด remove() เป็นการกำหนดค่าที่ต้องการลบออกจาก list 
#### Ex
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ : ${list}");
  list.remove(30);
  print("หลังใช้ : ${list}");
}
```
#### output
```
ก่อนใช้ : [10, 20, 30, 40, 50]
หลังใช้ : [10, 20, 40, 50]
```
แต่วิธีนี้นั้นจะทำการลบค่าที่ตรงกับค่ากำหนดค่าแรกที่เจอเท่านั้น จะไม่ทำการลบค่าที่ตรงกับค่าที่กำหนดที่เหลือ
#### Ex
```
void main() {
  var list = [10, 20, 30, 40, 50,20,60,20];
  print("ก่อนใช้ : ${list}");
  list.remove(20);
  print("หลังใช้ : ${list}");
}
```
#### output
```
ก่อนใช้ : [10, 20, 30, 40, 50, 20, 60, 20]
หลังใช้ : [10, 30, 40, 50, 20, 60, 20]
```
### ตัวอย่างที่2:removeAt()
วิธีนี้จะใช้เม็ดตอด removeAt() วิธีนี้จะเป็นการลบค่าตามตำแหน่งที่กำหนดและตำแหน่งแรกของ list ใน Dart คือ 0
#### Ex 1.
```
void main() {
  var list = [10, 11, 12, 13, 14];
  print("ก่อนใช้ : ${list}");
  list.removeAt(3);
  print("หลังใช้ : ${list}");
}
```
#### output
```
ก่อนใช้ : [10, 11, 12, 13, 14]
หลังใช้ : [10, 11, 12, 14]
```
#### Ex 2.
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
### output
```
ก่อนใช้: [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}, {name: Donald, age: 3}]
หลังใช้: [{name: John, age: 30}, {name: Bob, age: 50}, {name: Donald, age: 3}]
```
### ตัวอย่างที่3:removeLast()
วิธีนี้จะใช้เม็ดตอด removeLast() วิธีนี้จะลบค่าสุดท้ายออกจาก list
#### Ex 1.
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ :${list}");
  list.removeLast();
  print("หลังใช้ :${list}");
}
```
#### output
```
ก่อนใช้ :[10, 20, 30, 40, 50]
หลังใช้ :[10, 20, 30, 40]
```
#### Ex 2.
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
#### output
```
ก่อนใช้ : [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}, {name: Donald, age: 3}]
หลังใช้ : [{name: John, age: 30}, {name: Bob, age: 50}, {name: Tom, age: 14}]
```
### ตัวอย่างที่4:removeRange()
วิธีนี้จะใช้เม็ดตอด removeLast() เป็นการลบข้อมูลในตำแหน่งที่กำหนดเป็นช่วงจนถึงตำแหน่งสุดท้ายที่กำหนด
#### Ex 1.
```
void main() {
  var list = [10, 20, 30, 40, 50];
  print("ก่อนใช้ :${list}");
  list.removeRange(1, 3);
  print("หลังใช้ :${list}");
}
```
#### output
```
ก่อนใช้ :[10, 20, 30, 40, 50]
หลังใช้ :[10, 40, 50]
```
#### Ex 2.
```
final myList = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'];

void main(){
  print("ก่อนใช้ : ${myList}");
  myList.removeRange(2, 6);
  print("หลังใช้ : ${myList}");
}
```
#### output
```
ก่อนใช้ : [a, b, c, d, e, f, g, h]
หลังใช้ : [a, b, g, h]
```
### การลบข้อมูลใน list ใน Java และ C
ในภาษา Java นั้นสามารถใช้ วิธีการแบบภาษา Dart ได้แต่สามารถใช้ได้เพียงเม็ดตอด remove() เท่านั้น
และ C นั้นไม่สามารถทำได้
#### Ex Java.
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
#### output
```
Initial List: [Welcome, to, Geeks, for, Geeks]
Final List: [Welcome, to, for, Geeks]
```
