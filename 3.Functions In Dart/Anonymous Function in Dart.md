# Anonymous Function in Dart
ใน tutorial นี้ คุณจะได้เรียนรู้วิธีกำหนด Function ใน ภาษา Dart โดยไม่ระบุชื่อ
## Anonymous functions หรือฟังก์ชันนิรนาม
ฟังก์ชันโดยส่วนใหญ่จะมีชื่อทั้งนั้น เช่น main(), printElement() ถึงอย่างนั้นคุณก็สามารถสร้างฟังก์ชันที่ไม่มีชื่อได้เหมือนกัน หรือที่เรียกว่า anonymous functions บางทีก็เรียก lambda หรือบ้างก็เรียก closure
ซึ่งหน้าตาของฟังก์ชันนิรนามก็เหมือนกันฟังก์ชันที่มีชื่อ ต่างกันแค่ไม่มีชื่อให้เรียก โดยปกติแล้วเราจะกำหนดมันใส่ตัวแปร หรือส่งไปเป็น Parameter ของฟังก์ชันอื่น
## Syntax
- Dart
 ```dart
(parameter_list) {  
   statement(s)  
}  
```
## เทียบกับภาษาอื่นๆ
- Python
```python
lambda arguments : expression
```
- Java
```java
(parameters) -> { body }  
```
- C#
```c#
(input-parameters) => { <sequence-of-statements> }
```
### Example : เขียนฟังก์ชันแบบธรรมดา
 ```dart
int add(int x, int y) {
  return x + y;
}
```
ถ้าคุณนำ return type (int) และ name (add) ออกจาก ฟังก์ชัน add() คุณจะได้ anonymous function:
### Example : เขียนฟังก์ชันแบบ Anonymous Function
 ```dart
(int x, int y) {
  return x + y;
}
```
โดยทั่วไป เราจะกำหนดตัวแปรให้กับฟังก์ชันที่ไม่ระบุชื่อ และจะใช้ตัวแปรเพื่อเรียกใช้ฟังก์ชัน 
### For Example :
- Dart
```dart
void main() {
  var sum = (int x, int y) {
    return x + y;
  };

  print(sum(10, 20));
}
```
**output**
```
30
```
- Python
```python
sum = lambda x,y:x+y
print(sum(10,20))
```
-Java
```java
public class Main {
    public static void main(String[] args) {
        Operation operation = new Operation() {
            public int operate(int x, int y) {
                return x + y;
            }
        };

        System.out.println(operation.operate(20, 10));
    }
}
```
