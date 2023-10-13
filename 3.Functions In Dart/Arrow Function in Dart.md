# Arrow Functions in Dart
ใน tutorial นี้ คุณจะได้เรียนรู้วิธีการเขียน Function ใน ภาษา Dart ให้สั้นลงโดยใช้ arrow functions
## Arrow functions หรือฟังก์ชันลูกศร
Arrow Function เป็นการเขียนฟังก์ชันแบบย่อ ใช้สำหรับการเขียนฟังก์ชันที่มีเพียงนิพจน์เดียวให้สั้นลง โดย arrow function มีหน้าตาเป็นแบบนี้ => โดยฝั่งขวาของลูกศร จะเป็นค่าที่เราต้องการ return

## Syntax
- Dart
 ```dart
returnType functionName(parameters...) => expression;
```
## เปรียบเทียบกับภาษาอื่นๆ
- Python
```python
lambda arguments : expression
```

- JavaScript 
```javascript
returnType functionName(parameters...) => expression; 
```
ใน JavaScript Arrow Function ใช้งานเหมือนกับใน Dart 
- ไม่มี Arrow Function ใน C หรือ Java  

### Example : เขียนฟังก์ชันแบบธรรมดา
 ```dart
int add(int x, int y) {
  return x + y;
}
```

### Example : เขียนฟังก์ชันแบบ Arrow Function
 ```dart
int add(int x, int y) => x + y;

```
เราจะกำหนดให้ค่าที่เราต้องการ return อยู่ด้านขวาของลูกศร => 
### For Example 1 :
- Dart
```dart
void main() {
  // Arrow Function รวมเลขสองตัว
  int add(int a, int b) => a + b;

  // เรียกใช้งาน Arrow Function
  print(add(5, 3));  
}

```
**output**
```
8
```
### ตัวอย่างเดียวกันในภาษาอื่น
- Python
```python
add = lambda a, b: a + b
print(add(5, 3))
```

- JavaScript
```
const add = (a, b) => a + b;
console.log(add(5, 3));
```
### For Example 2 :
- ถึงแม้ว่าเราไม่สามารถใช้  if statement ใน Arrow Function แต่ใน Dart เราสามารถใช้ conditional expression ได้
```dart
String playerName(String? name) => name != null ? name : 'Guest';

```
สำหรับตัวอย่างด้านบนจะเป็นการตรวจสอบว่า String ที่ส่งมามีค่าเป็น null หรือไม่ ถ้าใช่ก็จะส่ง String 'Guest' แต่ถ้าไม่ก็จะส่งค่าที่ได้กลับไป
### ตัวอย่างเดียวกันในภาษาอื่น
- JavaScript
```
const playerName = (name) => (name !== null) ? name : 'Guest';
```
- python
```
player_name = lambda name: name if name is not None else 'Guest'
```

## สรุป
Arrow Function เป็นการเขียนฟังก์ชันในรูปแบบที่สั้นลง สามารถใช้ได้เฉพาะกับฟังก์ชันที่มีเพียงแค่นิพจน์เดียว  
### *< Reference >*
https://dart-tutorial.com/dart-functions/arrow-function-in-dart/

https://dart.dev/language/functions

https://www.w3schools.com/python/python_lambda.asp

https://javascript.info/arrow-functions-basics

https://www.geeksforgeeks.org/javascript-ternary-operator/
### *< Video >*
https://youtu.be/UVtbrH8uqWE
### *< slide >*
https://docs.google.com/presentation/d/1jwt_gHkHa3OM4U3nYTxmdfcB9v8OviBx/edit#slide=id.p1

[arrow functions.pdf](https://github.com/soonklang/dart-tutorial/files/12888915/arrow.functions.pptx.pdf)

