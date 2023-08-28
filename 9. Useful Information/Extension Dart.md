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

ในส่วนของ Extension name นั้นสามารถละไว้ได้ แต่ที่ Dart แนะนำให้เราตั้งชื่อด้วยนั้น เนื่องจากเราไม่รู้ว่านักพัฒนาคนอื่น ๆ ในทีมจะมีการตั้งชื่อ Method ใน Extension ซ้ำกับเราหรือไม่ ซึ่งอาจทำให้เกิดความสับสนได้


