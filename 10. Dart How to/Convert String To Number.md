# Convert String to Number
ในการแปลง String เป็น number ใน Dart เราสามารถทำได้ด้วยการใช้ Method int.parse() และ double.parse()
วิธีการนี้สามารถใช้ได้กับ String ที่เป็นตัวเลขและเลขฐาน เราสามารถใช้ Try-Catch เพื่อตรวจว่าแปลงเป็นNumberได้ไหม ถ้าแปลงไม่ได้ให้ส่งข้อความบอกว่าไม่สามารถแปลงได้ และ การใช้Extension ในการเพิ่ม Method ไปในคลาส String ทำให้แปลงStringได้ง่านขึ้น  
#### การสร้าง Extension  
```dart
extension <extension name> on <type> {
  (<member definition>)*
}
```
### Example การใช้ Extension  
```dart
extension NumberParsing on String { // คลาสที่ต้องการเพิ่ม Method
  int parseInt() { //Methodที่เพิ่ม
    return int.parse(this);
  }
}

void main() {
  String value_str = "1";
  int n = value_str.parseInt(); //เรียกใช้
  print(n); 
}
```
Output  
```dart
1
```
#
### Example การใช้ int.parse() 
## Dart
```dart
void main(){
  String value_int = "1";
  int n = int.parse(value_int);
  print(n);
}
```
Output   
```dart
1
```  
จากตัวอย่างเราได้แปลง Value_int ที่เป็น String เป็น int โดยใช้ Method int.pares()  
#
### Example การใช้ double.parse()  
```dart
void main(){
  String value_double = "3.14";
  double n = double.parse(value_double);
  print(n);
}
```
Output  
```
3.14
```  
จากตัวอย่างเราได้แปลง Value_double ที่เป็น String เป็น double โดยใช้ Method double.pares()  
#
### Example แปลง String เลขฐาน16เป็น Number  
```dart
void main(){
  String value = "A";
  int n = int.parse(value,radix: 16);
  print(n);
}
```
Output  
```
10
```
#
### Example การใช้ Try-Catch  
```dart
void main(){
try { 
String value = "Silpakorn";
int n = int.parse(value);
print(n); //ถ้าแปลงได้จะPrintกรณีนี้
  }
catch(ex){
print("Eror"); //ถ้าไม่สามารถแปลงได้Printกรณีนี้
}
}
```
Output  
```dart
Error
```
### เทียบกับ C,Java,Python  
## Dart
```dart
void main(){
  String value_int = "1";
  int n = int.parse(value_int);
  print(n);
}
```
## Java
```java
public class Main {
    public static void main(String[] args) {
        String value_int = "1";
        int n = Integer.parseInt(value_int);
        System.out.println(n);
    }
}
```
## C  
```C
#include <stdio.h>
#include <stdlib.h>

int main() {
    char value_int[] = "1";
    int n = atoi(value_int);
    printf("%d\n", n);
}
```
## Python  
```Python
value_int = "1"
n = int(value_int)
print(n)
```
จากCodeจะเห็นว่า Dart,C,Java,Pythonมีลักษณะคล้ายกันคือการเรียกใช้ Method มาแปลง String เป็น Number

Link Slide https://drive.google.com/file/d/1PIbymgrPPZ_J8Fpera3TyCkzZ0uYqTa1/view?usp=drive_link  

Link Video https://www.youtube.com/watch?v=IVHSiPTrHqk
### Reference
https://dart-tutorial.com/dart-how-to/convert-string-to-int-in-dart/  
https://www.educative.io/answers/how-to-convert-a-string-to-an-integer-in-c  
https://www.javatpoint.com/java-string-to-int  
https://www.scaler.com/topics/convert-string-to-int-python/  
https://dart.dev/language/extension-methods



