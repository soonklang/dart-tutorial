# Dart Extension
## Introduction to Dart extension methods
ฟีเจอร์ Extension Methods เป็นฟีเจอร์ที่เข้ามาเพื่อช่วยให้เราสามารถเพิ่มความสามารถของ Class โดยที่ไม่ต้องใช้ Inheritance นั่นหมายความว่าความสามารถใด ๆ ก็ตามที่เราเพิ่มเข้าไปนั้น จะสามารถเรียกใช้งานผ่าน Class เดิมได้เลย

## Dart extension method syntax
method ของการใช้งาน Extension dart จะเป็นดังนี้
```dart
extension <extension name> on <type> {
  (<member definition>)*
}
   ```
> การใช้ Extension ควรประกาศอยู่ส่วนบนสุดของไฟล์ หรือก็คือไม่ควรประกาศใช้ภายใน Function หรือ Class

ในส่วนของ Extension name นั้นสามารถละไว้ได้ แต่ที่ Dart แนะนำให้เราตั้งชื่อด้วยนั้น เนื่องจากเราไม่รู้ว่านักพัฒนาคนอื่น ๆ ในทีมจะมีการตั้งชื่อ Method ใน Extension ซ้ำกับเราหรือไม่ ซึ่งอาจทำให้เกิดความสับสน

ภายในส่วนขยาย เราสามารถนิยาม method ได้ โดยใน method เหล่านี้ คำสั่ง this จะอ้างอิงถึงอินสแตนซ์ปัจจุบันของชนิด (type) นั้น

นอกเหนือจาก method เรายังสามารถเพิ่มสมาชิกอื่น ๆ เช่น getter, setter, และ operator ได้


