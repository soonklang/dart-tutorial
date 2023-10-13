# FUNCTIONS IN DART

## Functions In Dart
ใน tutorial นี้เราจะมาสอนคุณเกี่ยวกับ Function ใน ภาษา Dart โดย Function คือชุดของคำสั่งเพื่อที่จะทำงานบางสิ่งให้สำเร็จ มักจะถูกสร้างมาเมื่อบางคำสั่งถูกเรียกใช้ซ้ำๆในโปรแกรม Function จะช่วยให้โค้ดในโปรแกรมมี Reusability เพิ่มมากขึ้น

**ข้อควรจำ**
สำคัญ: จุดประสงค์หลักของ Function คืออย่าใช้คำสั่งเดิมซ้ำๆ

## ประโยชน์ของ Function
- หลีกเลี่ยงการเขียนโค้ดซ้ำๆ
- ทำให้สามารถแยกโค้ดที่ดูซับซ้อนเป็นส่วนย่อยๆได้
- ทำให้โค้ดสามารถอ่านได้ง่าย

## Syntax ของ Dart
- Dart
```dart
returnType functionName(parameter1, parameter2, ...) {
  // function body
}
 ```
- **Return Type** : เป็นตัวกำหนดประเภทข้อมูลออกของ function สามารถเป็น void, String, int, double หรืออื่นๆ ถ้า function ไม่ได้  return อะไรเลยเราสามารถใช้  void ได้
- **Function Name** : คือชื่อของ Function เราจะสามารถตั้งชื่อเป็นอะไรก็ได้ ถ้าเราทำตามกฎการตั้งชื่อที่ชื่อว่า lowerCamelCase อย่างเช่น void printName()
- **Parameters** : Parameter คือข้อมูลเข้าของ function โดยเราจะสามารถกำหนดประเภทของข้อมูลและชื่อข้อมูลได้ในวงเล็บ () ชื่อนั้นควรตั้งตามกฎ lowerCamelCase ด้วยเหมือนกัน

สำหรับ functions ที่มีแค่คำสั่งเดียว เราสามารถเขียนให้สั้นลงได้อีกแบบเช่น 
```dart
bool isNoble(int atomicNumber) => _nobleGases[atomicNumber] != null;
}
 ```
=> expr คือการเขียนย่อของ { return expr; } 

## Anonymous functions
ใน Dart เราจะสามารถสร้าง Anonymous functions หรือบางครั้งถูกเรียกว่า lambda functions หรือ closure functions โดยเราจะมีตัวอย่างเป็น โค้ดที่มี item เป็นตัว parameter ส่งไปเปลี่ยนเป็นตัวอักษรใหญ่ จากในส่งให้ Anonymous function แสดงคำๆนั้นออกมาพร้อมกับความยาวของข้อความ
```dart
const list = ['apples', 'bananas', 'oranges'];
list.map((item) {
  return item.toUpperCase();
}).forEach((item) {
  print('$item: ${item.length}');
});
}
 ```
Output
```
APPLES: 6
BANANAS: 7
ORANGES: 7
 ```



## เทียบกับภาษาอื่นๆ
- Java
```java
returnType methodName() {
  // method body
}
 ```
- C
```c
returnType functionName(parameter1, parameter2, parameter3) {
  // code to be executed
}
 ```
- python
```python
def function_name(arguments):
    # function body 

    return
}
 ```
ส่วนใหญ่จะมี syntax ที่คล้ายๆกันแต่จะมีรายละเอียดยิบย่อยที่ต่างกันไปตามภาษา
## Keypoint ของ Function 
- ใน Dart function ก็เป็น object
- ควรจะตั้งชื่อ function ตามกฎ lowerCamelCase
- ควรจะตั้งชื่อ function parameter ตามกฎ lowerCamelCase
## อะไรคือ lowerCamelCase
ชื่อควรจะเริ่มด้วย ตัวอักษรภาษาอังกฤษแบบ lower-case และ คำที่สองให้เป็น upper-case เช่น num1, fullName, isMarried

## Example : printName() Function
- Dart
```dart
// เขียน function นอก main function.
void printName(){
  print("My name is Kritthana Sawankaloke. I am from function.");
}
// นี่คือ main function.
void main(){
  printName();
}
 ```
**output**
```
My name is Kritthana Sawankaloke. I am from function.
```
##ตัวอย่างเดียวกันในภาษาอื่น
- Java
```java
public class Main {
    static void printName() {
        System.out.println("My name is Kritthana Sawankaloke. I am from function.");
    }
    
    public static void main(String[] args) {
        printName();
    }
}
 ```
- C
```c
#include <stdio.h>

void printName() {
    printf("My name is Kritthana Sawankaloke. I am from function.\n");
}

void main() {
    printName();
}
 ```
- Phython
```python
def printName():
    print("My name is Kritthana Sawankaloke. I am from function.")

def main():
    printName()
 ```
## Example : Function รวมเลขสองตัวเลข
- Dart
```dart
 void add(int num1, int num2){
  int sum = num1 + num2;
   print("The sum is $sum");
}

void main(){
  add(10, 20);
}
 ```
**output**
```
The sum is 30
```
##ตัวอย่างเดียวกันในภาษาอื่น
- Java
```java
public class Main {
    static void add(int num1, int num2) {
        int sum = num1 + num2;
        System.out.println("The sum is " + sum);
    }
    
    public static void main(String[] args) {
        add(10, 20);
    }
}
 ```
- C
```c
#include <stdio.h>

void add(int num1, int num2) {
    int sum = num1 + num2;
    printf("The sum is %d\n", sum);
}

void main() {
    add(10, 20);
}
 ```
- Phython
```python
def add(num1, num2):
    sum = num1 + num2
    print("The sum is", sum)

def main():
    add(10, 20)
 ```
## Function Parameters Vs Arguments
```dart
// ในที่นี้ num1 และ num2 คือ parameter
void add(int num1, int num2){
  int sum;
  sum = num1 + num2;
   
  print("The sum is $sum");
}

void main(){
// ในที่นี้ 10 และ 20 คือ arguments
  add(10, 20);
}
 ```
- arguments คือสิ่งที่เป็นเหมือนข้อมูลเข้าให้กับ Function
- ในที่นี้ add(int num1, int num2), num1 และ num2 เป็น parameters และใน add(10, 20), 10 และ 20 คือ arguments.
- Parameter คือชื่อและ data type ที่คุณอยากจะให้เป็นข้อมูลเข้าของ function.
**ข้อควรจำ**
สำคัญ: ใน dart, ถ้าคุณไม่เขียน return type ของ function. มันก็จะยังสามารถทำงานได้อยู่ดี

### *< Reference >*
https://www.idtech.com/blog/what-is-an-argument-in-programming

https://dart-tutorial.com/dart-functions/functions-in-dart/

https://www.programiz.com/java-programming/methods

https://www.w3schools.com/c/index.php

https://dart.dev/language/functions

https://www.techtarget.com/whatis/definition/lowerCamelCase
### *< Link Video >*
https://youtu.be/9-FAwjsoHUw?si=rFaw5hTHAWpHs-62
### *< Slide File >*
pdf:[Function in dart.pdf](https://github.com/sawankaloke/Slideadnpdf/blob/main/FUNCTIONS%20IN%20DART.pdf)

slide:[Function in dart.pptx](https://github.com/sawankaloke/Slideadnpdf/blob/14d0f9551b4139f95484945801f99fe4a1627a6d/FUNCTIONS%20IN%20DART.pptx)
