# **For Each Loop in dart**

### **บทนำ**

For each loop ในภาษา Dart เป็นวิธีการวนลูปผ่านสมาชิกในคอลเลกชัน (collection) หรือ Iterable โดยไม่จำเป็นต้องใช้ดัชนี (index) ในกระบวนการวนลูป มันช่วยให้คุณสามารถดำเนินการกับแต่ละสมาชิกในคอลเลกชันอย่างง่ายดาย โดยใช้ฟังก์ชันสำหรับการดำเนินการกับแต่ละสมาชิก

### **วิธีวนซ้ำองค์ประกอบด้วย forEach ใน Dart**

ในภาษาการเขียนโปรแกรม Dart เมธอด forEach เป็นวิธีหนึ่งในการวนซ้ำองค์ประกอบในคอลเลกชันที่ทำซ้ำได้ เช่น รายการ แผนที่ หรือชุด วิธีการนี้ช่วยให้สามารถดำเนินการฟังก์ชันที่กำหนดกับแต่ละองค์ประกอบในคอลเลกชันได้โดยไม่จำเป็นต้องวนซ้ำอย่างชัดเจน

ความสำคัญของการเขียนโปรแกรม forEach ใน Dart นั้นอยู่ที่ความเรียบง่ายและความสามารถรอบด้าน เป็นวิธีที่กระชับและตรงไปตรงมาซึ่งสามารถใช้เพื่อดำเนินการต่างๆ กับองค์ประกอบในคอลเลกชันได้

เมธอด forEach รับพารามิเตอร์ตัวเดียว ซึ่งเป็นฟังก์ชันที่ใช้กับแต่ละองค์ประกอบในคอลเลกชัน ฟังก์ชันรับหนึ่งอาร์กิวเมนต์ซึ่งเป็นองค์ประกอบปัจจุบันที่กำลังประมวลผล ไวยากรณ์สำหรับวิธี forEach เป็นดังนี้:

 ```dart
 iterable.forEach((element) { ... });
```

 * วิธีการ forEach ใช้ในการวนซ้ำองค์ประกอบในคอลเลกชัน (แสดงโดยความสามารถในการวนซ้ำ)

 * วิธีการนี้ใช้ฟังก์ชันที่ไม่ระบุชื่อเป็น argument ซึ่งถูกกำหนดไว้ที่ point of call

 * ฟังก์ชั่นที่ไม่ระบุชื่อรับหนึ่งองค์ประกอบของ argument ซึ่งแสดงถึงองค์ประกอบปัจจุบันที่กำลังประมวลผลจากวัตถุที่ทำซ้ำได้

 * เนื้อความของฟังก์ชันที่ไม่ระบุชื่อ ซึ่งกำหนดไว้ในเครื่องหมายปีกกา { ... } ประกอบด้วยการดำเนินการที่จะดำเนินการกับแต่ละองค์ประกอบในขณะที่ประมวลผลจาก object ที่ทำซ้ำได้

### **กรณีการใช้งานของ for each loop**

1.วนลูปผ่านสมาชิกใน List: การใช้งาน for each loop เพื่อวนลูปผ่านสมาชิกแต่ละตัวใน List เพื่อดำเนินการตามที่ต้องการ เช่นการแสดงข้อมูลทั้งหมดใน List
```dart
List<int> numbers = [1, 2, 3, 4, 5];

numbers.forEach((number) {
  print(number);
});
```
<details open>
<summary><b>output</b></summary>
 <pre>
1
2
3
4
5</pre>
</details>

2.การประมวลผลทั้งหมดใน Collection: ถ้าคุณมี Collection อื่น ๆ เช่น Set, Map, หรือ Iterable อื่น ๆ การใช้ for each loop จะช่วยในการประมวลผลทั้งหมดหรือดำเนินการกับสมาชิกทั้งหมดใน Collection นั้น ๆ
```dart
Set<String> names = {'Alice', 'Bob', 'Charlie'};

names.forEach((name) {
  print("Hello, $name!");
});
```
<details open>
<summary><b>output</b></summary>
 <pre>
Hello, Alice!
Hello, Bob!
Hello, Charlie!
</pre>
</details>

3.การแปลงและปรับแต่งข้อมูล: for each loop สามารถใช้ในการแปลงหรือปรับแต่งข้อมูลของแต่ละสมาชิก โดยการปรับเปลี่ยนค่าของสมาชิกแต่ละตัวให้เข้ากับการประมวลผลที่ต้องการ
```dart
List<int> originalList = [1, 2, 3, 4, 5];
List<int> squaredList = [];

originalList.forEach((number) {
  squaredList.add(number * number);
});

print(squaredList);
```
<details open>
<summary><b>output</b></summary>
 <pre>
[1, 4, 9, 16, 25]
</pre>
</details>

4.การค้นหาข้อมูล: คุณสามารถใช้ for each loop เพื่อค้นหาข้อมูลที่ตรงตามเงื่อนไขในคอลเลกชัน เช่นการค้นหาข้อมูลที่มีค่ามากกว่าหรือน้อยกว่าที่กำหนด
```dart
List<int> numbers = [10, 20, 30, 40, 50];
int target = 30;

numbers.forEach((number) {
  if (number == target) {
    print("Found $target!");
  }
});
```
<details open>
<summary><b>output</b></summary>
 <pre>
Found 30!
</pre>
</details>

5.การเรียกใช้ฟังก์ชันบนสมาชิก: คุณสามารถเรียกใช้ฟังก์ชันบนแต่ละสมาชิกในคอลเลกชันโดยใช้ for each loop เพื่อดำเนินการหรือประมวลผลต่อสมาชิกที่แต่ละตัว
```dart
List<String> fruits = ['apple', 'banana', 'cherry'];

fruits.forEach((fruit) {
  print(fruit.toUpperCase());
});
```
<details open>
<summary><b>output</b></summary>
 <pre>
APPLE
BANANA
CHERRY
</pre>
</details>

6.การประมวลผลลำดับของการกระทำ: การใช้ for each loop เพื่อทำลำดับของการกระทำหรือการดำเนินการตามลำดับ โดยจะดำเนินการกับแต่ละขั้นตอนในลูป
```dart
List<String> actions = ['Jump', 'Run', 'Swim', 'Climb'];

actions.forEach((action) {
  print("Performing: $action");
});
```
<details open>
<summary><b>output</b></summary>
 <pre>
Performing: Jump
Performing: Run
Performing: Swim
Performing: Climb
</pre>
</details>

การใช้งาน for each loop ช่วยให้โค้ดมีความอ่านง่าย ลดความซับซ้อน และเพิ่มความคล้ายคลึงกับภาษาธรรมชาติในการพูดคุยเกี่ยวกับแต่ละสมาชิกในคอลเลกชัน

## **การใช้ For Each Loop ในภาษา Java** ##

For each loop หรือ Enhanced for loop ในภาษา Java เป็นโครงสร้างการวนลูปที่ใช้ในการวนลูปผ่านสมาชิกในอาร์เรย์หรือคอลเล็กชัน (collections) ต่าง ๆ โดยที่คุณไม่ต้องใช้ดัชนี (index) เพื่อเข้าถึงข้อมูล มันทำให้การเขียนโค้ดดูง่ายและอ่านง่ายขึ้น เพราะคุณเน้นกับสมาชิกแต่ละตัวในอาร์เรย์หรือคอลเล็กชัน

รูปแบบของ for each loop ในภาษา Java มีดังนี้:

```java
for (type variableName : arrayName) {
  // code block to be executed
}
```

ตัวอย่างการใช้ลูป "for-each" โดยจะแสดงผลองค์ประกอบทั้งหมดในอาร์เรย์ cars :

```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (String i : cars) {
  System.out.println(i);
}
```

<details open>
<summary><b>output</b></summary>
 <pre>
Volvo
BMW
Ford
Mazda
</pre>
</details>
