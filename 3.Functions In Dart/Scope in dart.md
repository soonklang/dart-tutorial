# ***Scope in dart***

## Scope คือ
* เป็นแนวคิดที่อ้างอิงตำแหน่งที่สามารถเข้าถึงหรืออ้างอิงค่าได้ และ Dart ใช้เครื่องหมายปีกกา เพื่อกำหนดขอบเขตของตัวแปร หากกำหนดตัวแปรไว้ในเครื่องหมายปีกกา จะไม่สามารถใช้ตัวแปรนั้นนอกเครื่องหมายปีกกาได้

    * scopeใช้งานง่ายมากไม่จําเป็นต้องสำรวจเพิ่มเติม 

## Scope in dart 
*   ### Method Scope 
*   ### Global Scope
*   ### Lexical Scope

## Method Scope
* หากสร้างตัวแปรภายใน Method คุณสามารถใช้ตัวแปรใน Method นั้นได้ แต่ไม่สามารถใช้ตัวแปรนอก Method นั้นได้

## ตัวอย่าง Method Scope :
**Dart**
```Dart
void main() {
  String text = "I am text inside main. Anyone can't access me.";
  print(text);
}
```
### Output :
```
I am text inside main. Anyone can't access me.
```

**Python**
```python
def print_number():
    first_num = 1
    print("The first number defined is : ", first_num)
```
### Output :
```
The first number defined is : 1
```

**Java**
```java
public class Main(){
    public static void main(String[] args){
        int x = 100;
        System.out.println(x);
    }
}
```

### Output :
```
100
```

## Global Scope
* คุณสามารถกำหนดตัวแปรในขอบเขตส่วนกลาง เพื่อใช้ตัวแปรนั้นได้ทุกที่ในโปรแกรม

## ตัวอย่าง Global Scope :
**Dart**
```Dart
String global = "I am Global. Anyone can access me."

void main(){
    print(global);
} 
```

### Output :
```Dart
I am Global. Anyone can access me.
```

**Python**
```python
x = 300

def myfunc():
    print(x)

myfunc()

print(x)
```

### Output :
```
300
300
```

## Lexical Scope
* ขอบเขตการทำงานที่ฟังก์ชันด้านในสามารถเข้าถึงตัวแปรที่อยู่ด้านนอกได้

## ตัวอย่าง Lexical Scope
**Dart**
```dart
void main(){
    var language = 'Dart';
    void printLanguage(){
        language = 'DartLang';
        print("Language is ${language}");
    }
    printLanguage();
}
```

### Output :
```
Language is DartLang
```

**Python**
```python
def f():
    print(x)

def g(foo):
    x = 99
    foo()
    print(x)

x = 1
g(f)
```

### Output :
```
1
99
```

## <***Reference***>
* https://www.w3schools.com/java/java_scope.asp
*   https://www.w3schools.com/python/python_scope.asp
*   https://www.datacamp.com/tutorial/scope-of-variables-python?
*   https://dart-tutorial.com/dart-functions/scope-in-dart/
*   https://www.tutorialspoint.com/lexical-scoping-in-dart-programming?
*   https://stackoverflow.com/questions/51604346/

## **Link Video** ##
https://youtu.be/SiUSeKjG1HU

pdf file : [SCOPE IN DART.pdf](https://github.com/soonklang/dart-tutorial/files/12774190/Scope.pdf)
