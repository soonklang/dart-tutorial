# Convert String to Number
ในการแปลง String เป็น number ใน Dart เราสามารถทำได้ด้วยการใช้ Method int.parse() และ double.parse()
วิธีการนี้สามารถใช้ได้กับ String ที่เป็นตัวเลขและเลขฐาน  
### Example การใช้ int.parse()
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
### Example แปลง String เลขฐาน16เป็น Int  
```dart
void main(){
  String value = "ABC";
  int n = int.parse(value,radix: 16);
  print(n);
}
```
Output  
```
2748
```
