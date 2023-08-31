
# Interface in Dart
Interface คือ การกำหนดโครงสร้างของ methood ขึ้นมาไม่มีการกำหนดรายละเอียด การทำงานใดๆ โดยทุก method จะไม่อนุญาตให้เรียกใช้ทำงาน แต่จะถูกสืบทอดและกำหนดรายละเอียด ของ Interface นั้น คลาสที่ implement ก็จะมี methood ที่เรียกใช้งานได้
-----------------------------------------------------------------------------
# Syntax ของ Dart
```dart
class Interface_class_name{
   ...
}

class Class_name implements Interface_class_name {
   ...
}
```
จะเห็นว่า ไม่ต้องเติมคำว่า intterface หน้าชื่อคลาสแม่แบบที่ต้องการให้implement  
 ในภาษา Dart จะมองว่าทุกๆ class เป็น interface สามารถนำไปใช้งานได้ โดยไม่ต้องใช้ interface keyword
# Syntax ของ java 
```java
interface Animal {
  public void animalSound(); 
  public void sleep(); 
}
```
