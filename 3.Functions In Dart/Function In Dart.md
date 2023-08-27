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
- Phython
```python
def function_name(arguments):
    # function body 

    return
}
 ```
ส่วนใหญ่จะมี syntax ที่คล้ายๆกันแต่จะมีรายละเอียดยิบย่อยที่ต่างกันไปตามภาษา



