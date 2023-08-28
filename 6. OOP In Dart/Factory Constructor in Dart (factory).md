# Factory Constructor in Dart (factory)
ในส่วนนี้เราจะเรียนรู้เกี่ยวกับ constructor แบบ factory พร้อมตัวอย่างการใช้งาน ก่อนที่เราจะเรียนรู้เกี่ยวกับ constructor แบบ factory เราควรมีความเข้าใจพื้นฐานเกี่ยวกับclassและobject constructor, abstract class, interface and inheritance in Dart ก่อน
# Factory Constructor In Dart
ทุกconstructorsของที่เราได้เรียนรู้จนถึงตอนนี้เป็น constructor แบบ generative แต่ Dart ยังมี constructor ประเภทพิเศษที่เรียกว่า constructor แบบ factory
constructor แบบ factory มอบความยืดหยุ่นมากขึ้นในการสร้างวัตถุ constructor แบบ generative เพียงแค่สร้างตัวอย่างของคลาสเท่านั้น แต่ constructor แบบ factory สามารถสร้างตัวอย่างของคลาสหรือคลาสย่อยได้เช่นกัน นอกจากนี้ยังใช้ในการส่งคืนตัวอย่างของคลาสที่ถูกเก็บไว้ในแคชได้อีกด้วย
# Syntax
```dart
class ClassName {
  factory ClassName() {
    // TODO: return ClassName instance
  }

  factory ClassName.namedConstructor() {
    // TODO: return ClassName instance
  }
}
```
# Rules For Factory Constructors
Constructor แบบ factory จำเป็นต้องส่งคืนตัวอย่างของคลาสหรือคลาสย่อย
คุณไม่สามารถใช้คีย์เวิร์ด this ภายใน constructor แบบ factory ได้
มันสามารถมีชื่อหรือไม่มีชื่อและเรียกใช้เหมือนกับ constructor ทั่วไป
มันไม่สามารถเข้าถึงสมาชิกของตัวอย่างได้





