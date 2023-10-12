# **For Each Loop in dart**

## **บทนำ**

For each loop ในภาษา Dart เป็นวิธีการวนลูปผ่านสมาชิกในคอลเลกชัน (collection) หรือ Iterable โดยไม่จำเป็นต้องใช้ดัชนี (index) ในกระบวนการวนลูป ทำให้สามารถดำเนินการกับแต่ละสมาชิกในคอลเลกชันอย่างง่ายดาย โดยใช้ฟังก์ชันสำหรับการดำเนินการกับแต่ละสมาชิก

## **วิธีวนซ้ำองค์ประกอบด้วย forEach ใน Dart** ##

ในภาษาการเขียนโปรแกรม Dart เมธอด forEach เป็นวิธีหนึ่งในการวนซ้ำองค์ประกอบในคอลเลกชันที่ทำซ้ำได้ เช่น รายการ แผนที่ หรือชุด วิธีการนี้ช่วยให้สามารถดำเนินการฟังก์ชันที่กำหนดกับแต่ละองค์ประกอบในคอลเลกชันได้โดยไม่จำเป็นต้องวนซ้ำอย่างชัดเจน

ความสำคัญของการเขียนโปรแกรม forEach ใน Dart นั้นอยู่ที่ความเรียบง่ายและความสามารถรอบด้าน เป็นวิธีที่กระชับและตรงไปตรงมาซึ่งสามารถใช้เพื่อดำเนินการต่างๆ กับองค์ประกอบในคอลเลกชันได้

เมธอด forEach รับพารามิเตอร์ตัวเดียว ซึ่งเป็นฟังก์ชันที่ใช้กับแต่ละองค์ประกอบในคอลเลกชัน ฟังก์ชันรับหนึ่งอาร์กิวเมนต์ซึ่งเป็นองค์ประกอบปัจจุบันที่กำลังประมวลผล ไวยากรณ์สำหรับวิธี forEach เป็นดังนี้:

 ```dart
 iterable.forEach((element) { ... });
```

 * วิธีการ forEach ใช้ในการวนซ้ำองค์ประกอบในคอลเลกชัน (แสดงโดยความสามารถในการวนซ้ำ)

 * วิธีการนี้ใช้ฟังก์ชันที่ไม่ระบุชื่อเป็น argument ซึ่งถูกกำหนดไว้ที่จุดเรียกใช้งาน

 * ฟังก์ชั่นที่ไม่ระบุชื่อรับหนึ่งองค์ประกอบของ argument ซึ่งแสดงถึงองค์ประกอบปัจจุบันที่กำลังประมวลผลจากวัตถุที่ทำซ้ำได้

 * เนื้อความของฟังก์ชันที่ไม่ระบุชื่อ ซึ่งกำหนดไว้ในเครื่องหมายปีกกา { ... } ประกอบด้วยการดำเนินการที่จะดำเนินการกับแต่ละองค์ประกอบในขณะที่ประมวลผลจาก object ที่ทำซ้ำได้

## **กรณีการใช้งานของ for each loop** ##

**1.วนลูปผ่านสมาชิกใน List:** <br>
> การใช้งาน for each loop เพื่อวนลูปผ่านสมาชิกแต่ละตัวใน List เพื่อดำเนินการตามที่ต้องการ เช่นการแสดงข้อมูลทั้งหมดใน List
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

**2.การประมวลผลทั้งหมดใน Collection:** <br>
> ถ้ามี Collection อื่น ๆ เช่น Set, Map, หรือ Iterable อื่น ๆ การใช้ for each loop จะช่วยในการประมวลผลทั้งหมดหรือดำเนินการกับสมาชิกทั้งหมดใน Collection นั้น ๆ
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

**3.การแปลงและปรับแต่งข้อมูล:** <br>
> สามารถใช้ในการแปลงหรือปรับแต่งข้อมูลของแต่ละสมาชิก โดยการปรับเปลี่ยนค่าของสมาชิกแต่ละตัวให้เข้ากับการประมวลผลที่ต้องการ
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

**4.การค้นหาข้อมูล:** <br>
> สามารถใช้ค้นหาข้อมูลที่ตรงตามเงื่อนไขในคอลเลกชัน เช่นการค้นหาข้อมูลที่มีค่ามากกว่าหรือน้อยกว่าที่กำหนด
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

**5.การเรียกใช้ฟังก์ชันบนสมาชิก:** <br>
> สามารถเรียกใช้ฟังก์ชันบนแต่ละสมาชิกในคอลเลกชันโดยใช้ for each loop เพื่อดำเนินการหรือประมวลผลต่อสมาชิกที่แต่ละตัว
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

**6.การประมวลผลลำดับของการกระทำ:** <br>
> การใช้ for each loop เพื่อทำลำดับของการกระทำหรือการดำเนินการตามลำดับ โดยจะดำเนินการกับแต่ละขั้นตอนในลูป
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

**ตัวอย่าง: Sum of student grades using nested forEach loops**

```dart
void main() {
  List<Map<String, int>> grades = [
    {'Ayo': 60, 'Samuel': 89, 'Vic': 70},
    {'Ayo': 58, 'Samuel': 78, 'Vic': 58},
    {'Ayo': 86, 'Samuel': 70, 'Vic': 99}
  ];

  int sum = 0;
  grades.forEach((studentGrades) {
    studentGrades.forEach((student, grade) {
      sum += grade;
    });
  });

  print('The sum of all grades is $sum');
}
```
<details open>
<summary><b>output</b></summary>
 <pre>
The sum of all grades is 668
</pre>
</details>

**คำอธิบาย**
* บรรทัดที่ 2–6: กำหนดรายการของแผนที่เป็นเกรด โดยแต่ละแผนที่แทนชุดของชื่อนักเรียนเป็นคีย์และเกรดที่เกี่ยวข้องเป็นค่า

* บรรทัดที่ 8–13: กำหนดค่าเริ่มต้นให้ตัวแปรชื่อ sum เป็น 0 จากนั้นเราใช้เมธอด forEach เพื่อวนลูปผ่านรายการแผนที่ โดยแต่ละแผนที่จะถูกแทนด้วยตัวแปร studentGrades ภายใน forEach ภายใน studentGrades แต่ละคู่คีย์และค่าภายใน studentGrades จะถูกเข้าถึงและค่าจะถูกเพิ่มเข้าสู่ตัวแปร sum

* บรรทัดที่ 15: ผลรวมของเกรดทั้งหมดถูกพิมพ์ออกทางคอนโซล

<pre> <b>หมายเหตุ: หลีกเลี่ยงการวนซ้ำเพื่อประสิทธิภาพที่ดีขึ้น เนื่องจากอาจทำให้โค้ดช้าลง</b> </pre>

การใช้งาน for each loop ช่วยให้โค้ดมีความซับซ้อนลดลง มีความอ่านง่ายมากขึ้น

# **For Each Loop In Java** #

For each loop หรือ Enhanced for loop ในภาษา Java เป็นโครงสร้างการวนลูปที่ใช้ในการวนลูปผ่านสมาชิกในอาร์เรย์หรือคอลเล็กชัน (collections) ต่าง ๆ โดยไม่ต้องใช้ดัชนี (index) เพื่อเข้าถึงข้อมูล ทำให้การเขียนโค้ดดูง่ายและอ่านง่ายขึ้น เพราะเน้นกับสมาชิกแต่ละตัวในอาร์เรย์หรือคอลเล็กชัน

รูปแบบของ for each loop ในภาษา Java มีดังนี้:

```java
for(dataType item : array) {
    ...
}
```

dataType - ชนิดข้อมูลของอาร์เรย์/คอลเลกชัน<br>
item - แต่ละรายการของอาร์เรย์/คอลเลกชันถูกกำหนดให้กับตัวแปรนี้<br>
array - อาร์เรย์หรือคอลเลกชัน

**ตัวอย่างที่ 1: การแสดงผลองค์ประกอบทั้งหมดในอาร์เรย์ :**

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

**ตัวอย่างที่ 2: การแสดงผลรวมขององค์ประกอบอาร์เรย์ :**

```java
int[] numbers = {3, 4, 5, -5, 0, 12};
   int sum = 0;

   for (int number: numbers) {
     sum += number;
   }
  
   System.out.println("Sum = " + sum);
```

<details open>
<summary><b>output</b></summary>
 <pre>
Sum = 19
</pre>
</details>

| Iteration | Variables |
|:----:|:----|
|1| number = 3 <br> sum = 0 + 3 = 3 |
|2| number = 4 <br> sum = 3 + 4 = 7 |
|3| number = 5 <br> sum = 7 + 5 = 12 |
|4| number = -5 <br> sum = 12 + (-5) = 7 |
|5| number = 0 <br> sum = 0 + 7 = 7 |
|6| number = 12 <br> sum = 12 + 7 = 19 |

## **เปรียบเทียบ For Each Loop ในภาษา Dart และ ภาษา Java** ##

**1.การประกาศตัวแปร:**

Dart: ไม่จำเป็นต้องประกาศประเภทข้อมูลของตัวแปร โปรแกรมจะวิเคราะห์ประเภทข้อมูลอัตโนมัติ<br>
Java: ต้องระบุประเภทข้อมูลของตัวแปรที่ใช้ในการวนลูป

**2.การวนลูปในคอลเลกชันแบบต่าง:**

Dart: สามารถใช้กับ Iterable ทั้งหมด, รวมถึง List, Set, Map และอื่น ๆ<br>
Java: สามารถใช้กับอาร์เรย์และคอลเลกชันที่ประกาศเป็น Iterable หรือมี Iterable ที่สนับสนุน

**3.การเข้าถึงสมาชิก:**

Dart: สามารถใช้ชื่อตัวแปรในตำแหน่งของค่าเพื่อเข้าถึงสมาชิกแต่ละตัวในคอลเลกชัน<br>
Java: ต้องใช้ตัวแปรตามด้วยจุด (.) เพื่อเข้าถึงสมาชิกแต่ละตัวในคอลเลกชัน

> **_Note:_** 
 ใน Python ไม่มี for each loop อย่างที่มีในภาษาอื่น ๆ เช่น Dart หรือ Java แต่ Python มีการใช้ for loop ในการวนลูปผ่าน Iterable และสมาชิกในคอลเลกชัน การวนลูปนี้คือรูปแบบที่ Python ใช้แทนการ for each loop:

```python
numbers = [1, 2, 3, 4, 5]
for number in numbers:
    print(number)
```
<details open>
<summary><b>output</b></summary>
 <pre>
1
2
3
4
5
</pre>
</details>

## **Link Video** ##
https://youtu.be/_7Pun0i6BDQ

## **Slide** ##
[For each loop in dart.pptx](https://github.com/zhunAkkarapong/forEachLoopInDart/raw/main/For%20Each%20Loop%20in%20dart.pptx)

## **อ้างอิง** ##
https://dart-tutorial.com/conditions-and-loops/for-each-loop-in-dart/<br>
https://www.w3schools.com/java/java_foreach_loop.asp<br>
https://www.educative.io/answers/how-to-iterate-elements-with-foreach-in-dart<br>
https://www.programiz.com/java-programming/enhanced-for-loop<br>
https://www.pythonpool.com/python-foreach/
