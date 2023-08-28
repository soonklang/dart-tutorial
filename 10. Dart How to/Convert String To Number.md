# Convert String to Number
ในการแปลง String เป็น number ใน Dart เราสามารถทำได้ด้วยการใช้ Method int.parse() และ double.parse()
วิธีการนี้สามารถใช้ได้กับ String ที่เป็นตัวเลขและเลขฐาน  
### Example  
```dart
void main(){
  String value_int = "1";
  int n = int.parse(value);
  print(n);
}
