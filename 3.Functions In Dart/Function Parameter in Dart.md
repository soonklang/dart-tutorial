# FUNCTION PARAMETER IN DART
# Parameter In Dart
Parameter หรือ พารามิเตอร์ คือกระบวนการส่งผ่านค่าไปยังฟังก์ชัน 
ค่าที่ส่งไปยังฟังก์ชันจะต้องตรงกับจำนวนพารามิเตอร์ที่กำหนดไว้ 
โดยฟังก์ชันจะสามารถมีพารามิเตอร์ได้ไม่จำกัดจำนวน
### Dart
```dart
// a และ b คือพารามิเตอร์
void add(int a, int b) { 
} 
```
## ตัวอย่างในภาษาอื่นๆ
### Java
```java
// a และ b คือพารามิเตอร์
public double add(double a,double b) {
    double answer = a + b;
    return answer;
}
```
### Python
```python
# a และ b คือพารามิเตอร์
def my_function(a, b):
    print(int(a) + int(b))
```
# Positional Parameter In Dart
ใน Positional Parameter หรือ ลำดับพารามิเตอร์ คือจะต้องระบุ argument ในลำดับเดียวกับที่คุณกำหนดไว้บนพารามิเตอร์เมื่อคุณเขียนฟังก์ชัน หากเรียกใช้ฟังก์ชันด้วยลำดับที่ไม่ถูกต้อง จะได้ผลลัพธ์ที่ไม่ถูกต้อง

## ตัวอย่างที่ 1 การใช้ Positional Parameter
ตัวอย่างด้านล่าง มีฟังก์ชัน printInfo ที่รับพารามิเตอร์สองตัว เราต้องส่งค่า name และ gender ของบุคคลในลำดับที่ถูกต้อง หากส่งค่าผิดลำดับ จะได้รับผลลัพธ์ที่ไม่ถูกต้อง 
### Dart
```dart
void printInfo(String name, String gender) {
  print("Hello $name your gender is $gender.");
}

void main() {
  // ส่งค่าในลำดับที่ไม่ถูกต้อง
  printInfo("Male", "John");
  // ส่งค่าในลำดับที่ถูกต้อง
  printInfo("John", "Male");
}
```
#### output
```
Hello Male your gender is John.
Hello John your gender is Male.
```
## ตัวอย่างในภาษาอื่นๆ
### Python
```python
def nameAge(name, age):
    print("Hi, I am", name)
    print("My age is ", age)
# ส่งค่าในลำดับที่ไม่ถูกต้อง 
nameAge(20, "Prince")
# ส่งค่าในลำดับที่ถูกต้อง 
nameAge("Prince", 20)
```
#### output
```
Hi, I am 20
My age is  Prince
Hi, I am Prince
My age is  20
```
## ตัวอย่างที่ 2 การระบุค่าเริ่มต้นให้กับ Positional Parameter #1
ตัวอย่างด้านล่าง มีฟังก์ชัน printInfo ที่รับพารามิเตอร์สองตัวและพารามิเตอร์ทางเลือกหนึ่งตัว พารามิเตอร์ title หากผู้ใช้ไม่ระบุคำนำหน้า โปรแกรมจะระบุคำนำหน้าเป็น sir/ma'am โดยอัตโนมัติ
### Dart
```dart
void printInfo(String name, String gender, [String title = "sir/ma'am"]) {
  print("Hello $title $name your gender is $gender.");
}

void main() {
  printInfo("John", "Male");
  //เพิ่มคำนำหน้า
  printInfo("John", "Male", "Mr.");
  printInfo("Kavya", "Female", "Ms.");
}
```
#### output
```
Hello sir/ma'am John your gender is Male.
Hello Mr. John your gender is Male.
Hello Ms. Kavya your gender is Female.
```
## ตัวอย่างในภาษาอื่นๆ
### Python
```python
def student(firstname, lastname ='Mark', standard ='Fifth'):
     print(firstname, lastname, 'studies in', standard, 'Standard')
# เพิ่มค่า 1 ค่า
student('John')
# เพิ่มค่า 3 ค่า                        
student('John', 'Gates', 'Seventh')    
# เพิ่มค่า 2 ค่า 
student('John', 'Gates')                 
student('John', 'Seventh')
```
#### output
```
John Mark studies in Fifth Standard
John Gates studies in Seventh Standard
John Gates studies in Fifth Standard
John Seventh studies in Fifth Standard
```
## ตัวอย่างที่ 3 การระบุค่าเริ่มต้นให้กับ Positional Parameter #2
ตัวอย่างด้านล่าง มีฟังก์ชั่น add ที่รับพารามิเตอร์สองตัวและพารามิเตอร์ทางเลือกหนึ่งตัว พารามิเตอร์ num3 เป็นพารามิเตอร์ทางเลือก โดยมีค่าเริ่มต้นเป็น 0
### Dart
```dart
void add(int num1, int num2, [int num3=0]){
    int sum;
    sum = num1 + num2 + num3;
   
    print("The sum is $sum");
}

void main(){
    add(10, 20);
    add(10, 20, 30);
}
```
#### output
```
The sum is 30
The sum is 60
```
# Named Parameter In Dart
ภาษา Dart นั้นอนุญาตให้ใช้ named Parameters หรือ พารามิเตอร์ที่มีชื่อ เพื่อแจกแจงความหมายของพารามิเตอร์ในการเรียกใช้ในฟังก์ชัน

ใช้วงเล็บปีกกา { } เพื่อระบุพารามิเตอร์ที่มีชื่อ

## ตัวอย่างที่ 1 การใช้ Named Parameter
ตัวอย่างด้านล่าง มีฟังก์ชัน printInfo ที่รับพารามิเตอร์ที่มีชื่อสองตัว เราสามารถส่งค่า name และ gender ของบุคคลในลำดับใดก็ได้ 
### Dart
```dart
void printInfo({String? name, String? gender}) {
  print("Hello $name your gender is $gender.");
}

void main() {
  // สามารถส่งค่าชื่อและเพศของบุคคลในลำดับใดก็ได้ 
  printInfo(gender: "Male", name: "John");
  printInfo(name: "Sita", gender: "Female");
}
```
#### output
```
Hello John your gender is Male.
Hello Sita your gender is Female.  
```
## ตัวอย่างในภาษาอื่นๆ
### Python
```python
def my_function(child3, child2, child1):
  print("The youngest child is " + child3)
  print("The middle child is " + child2)
  print("The oldest child is " + child1)

my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```
#### output
```
The youngest child is Linus
The middle child is Tobias
The oldest child is Emil
```
## ตัวอย่างที่ 2 การใช้ Required ใน Named Parameter
ตัวอย่างด้านล่าง มีฟังก์ชัน printInfo ที่รับพารามิเตอร์ที่มีชื่อสองตัว หากเราใช้ required หมายความว่าต้องส่งค่า name และ gender ถ้าไม่ส่งค่า โปรแกรมก็จะไม่ทำงาน
### Dart
```dart
void printInfo({required String name, required String gender}) {
  print("Hello $name your gender is $gender.");
}

void main() {
  // สามารถส่งค่าชื่อและเพศของบุคคลในลำดับใดก็ได้ 
  printInfo(gender: "Male", name: "John");
  printInfo(gender: "Female", name: "Suju");
}
```
#### output
```
Hello John your gender is Male.
Hello Suju your gender is Female.
```
# Optional Parameter In Dart
ภาษา Dart นั้นอนุญาตให้ใช้ optional Parameters หรือ พารามิเตอร์ทางเลือกในฟังก์ชัน

ใช้วงเล็บเหลี่ยม [ ] เพื่อระบุพารามิเตอร์ทางเลือก

## ตัวอย่างการใช้ Optional Parameter
ตัวอย่างด้านล่าง มีฟังก์ชัน printInfo ที่รับพารามิเตอร์สองตัว และ พารามิเตอร์ทางเลือกหนึ่งตัว เราจำเป็นต้องส่งค่า name และ gender ส่วน title นั้นเป็นพารามิเตอร์ทางเลือก จะส่งค่าหรือไม่ก็ได้
### Dart
```dart
void printInfo(String name, String gender, [String? title]) {
  print("Hello $title $name your gender is $gender.");
}

void main() {
  printInfo("John", "Male");
  printInfo("John", "Male", "Mr.");
  printInfo("Kavya", "Female", "Ms.");
}
```
#### output
```
Hello  John your gender is Male.
Hello Mr. John your gender is Male.
Hello Ms. Kavya your gender is Female.  
```
## ตัวอย่างในภาษาอื่นๆ
### Python
```python
def fun2(string1, string2=""):
    print(string1 + string2)

fun2('GeeksFor')
fun2('GeeksFor', "Geeks")
```
#### output
```
GeeksFor
GeeksForGeeks
```

## <***Reference***>
*   https://dart-tutorial.com/dart-functions/function-parameter-in-dart/
*   https://www.w3schools.com/python/python_functions.asp
*   https://www.geeksforgeeks.org/keyword-and-positional-argument-in-python/
*   https://www.geeksforgeeks.org/default-arguments-in-python/
*   https://www.w3schools.com/python/gloss_python_function_keyword_arguments.asp
*   https://www.geeksforgeeks.org/how-to-pass-optional-parameters-to-a-function-in-python/

*   ## Slides & Clips
Vdo link : [https://youtu.be/s0UPdajVGjE](https://www.youtube.com/watch?v=EK4lRPd3mGA)https://www.youtube.com/watch?v=EK4lRPd3mGA

Slide Files : 

[Function Parameter in Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12774265/Function.Parameter.in.Dart.pptx)

[Function Parameter in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12886423/Function.Parameter.in.Dart.pdf)
