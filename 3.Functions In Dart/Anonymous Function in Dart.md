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
## เปรียบเทียบกับภาษาอื่นๆ
- Python
```python
lambda arguments : expression
```
- C#
```c#
(input-parameters) => { <sequence-of-statements> }
```
- JavaScript 
```javascript
(function () {
   //...
});
```
- ไม่มี Anonymous Function ใน ภาษา C หรือ Java
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
### For Example 1 :
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
### ตัวอย่างเดียวกันในภาษาอื่น
- Python
```python
sum = lambda x,y:x+y
print(sum(10,20))
```
- C#
```c#
using System;
class Program
{
    delegate int AddFunction(int x, int y);
    static void Main()
    {
        AddFunction sum = (x, y) => x + y;
        Console.WriteLine(sum(10, 20));
    }
}
```
- JavaScript 
```javascript
const sum = (x, y) => {
    return x + y;
};
console.log(sum(10, 20));
```

### For Example 2 :
- Dart
```dart
void show(fn) {
  for (var i = 0; i < 10; i++) {
    if (fn(i)) {
      print(i);
    }
  }
}

void main() {
  // show even numbers
  show((int x) {
    return x % 2 == 0;
  });
}
```
**output**
```
0
2
4
6
8
```
### ตัวอย่างเดียวกันในภาษาอื่น
- Python
```python
def show(fn):
    for i in range(10):
        if fn(i):
            print(i)

def main():
    # show even numbers
    show(lambda x: x % 2 == 0)

if __name__ == "__main__":
    main()
```

- C#
```c#
using System;
class Program
{
    delegate bool FilterDelegate(int x);

    static void Show(FilterDelegate fn)
    {
        for (var i = 0; i < 10; i++)
        {
            if (fn(i))
            {
                Console.WriteLine(i);
            }
        }
    }

    static void Main(string[] args)
    {
        // show even numbers
        Show((int x) =>
        {
            return x % 2 == 0;
        });
    }
}
```
- JavaScript 
```javascript
function show(fn) {
  for (var i = 0; i < 10; i++) {
    if (fn(i)) {
      console.log(i);
    }
  }
}

function main() {
  // show even numbers
  show(function(x) {
    return x % 2 === 0;
  });
}

main();
```

## สรุป
Anonymous Function คือฟังก์ชันที่ไม่มีชื่อ
### *< Reference >*
https://dart-tutorial.com/dart-functions/anonymous-function-in-dart/

https://www.javatpoint.com/dart-anonymous-function

https://www.darttutorial.org/dart-tutorial/dart-anonymous-functions/

https://supapongai.com/lambda-function/

https://www.javascripttutorial.net/javascript-anonymous-functions/

### *< Presentation >*
Link Video : https://youtu.be/wjLM1nS5iO4 <br>
Link Slide : [Anonymous Function](https://github.com/duangtan/Anonymous-Slide/blob/main/Anonymous-Function-in-Dart.pdf) <br>
Link dowload Slide : [Anonymous Function in Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12884450/Anonymous.Function.in.Dart.pdf) 

