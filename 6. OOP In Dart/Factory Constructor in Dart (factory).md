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
- Constructor แบบ factory จำเป็นต้องส่งคืนตัวอย่างของคลาสหรือคลาสย่อย
- คุณไม่สามารถใช้คีย์เวิร์ด this ภายใน constructor แบบ factory ได้
- มันสามารถมีชื่อหรือไม่มีชื่อและเรียกใช้เหมือนกับ constructor ทั่วไป
- มันไม่สามารถเข้าถึงสมาชิกของตัวอย่างได้
# Example 1: Without Factory Constructor
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Area ที่มีคุณสมบัติแบบ final คือ length และ breadth รวมถึง area ด้วย โดยเมื่อคุณส่งค่า length และ breadth ไปยัง constructor มันจะคำนวณพื้นที่และเก็บไว้ในคุณสมบัติ area
```dart
class Area {
  final int length;
  final int breadth;
  final int area;

  // Initializer list 
 const Area(this.length, this.breadth) : area = length * breadth;
}

void main() {
  Area area = Area(10, 20);
  print("Area is: ${area.area}");

  // notice that here is a negative value
  Area area2 = Area(-10, 20);
  print("Area is: ${area2.area}");
}
```
วัตถุ area2 มีค่าที่เป็นลบ เนื่องจากเรายังไม่ได้ตรวจสอบข้อมูลเข้าเงื่อนไขการตรวจสอบ ในกรณีนี้เราจะสร้าง constructor แบบ factory เพื่อทำการตรวจสอบข้อมูลที่ถูกส่งเข้ามา
# Example 2: With Factory Constructor
ในตัวอย่างด้านล่างนี้ มีการใช้ constructor แบบ factory เพื่อทำการตรวจสอบข้อมูลเข้าเกณฑ์ หากข้อมูลเข้าเกณฑ์ถูกต้อง จะส่งคืนอินสแตนซ์ของคลาสใหม่ แต่หากข้อมูลเข้าเกณฑ์ไม่ถูกต้อง จะโยนข้อผิดพลาดออกมา
```dart
class Area {
  final int length;
  final int breadth;
  final int area;

  // private constructor
  const Area._internal(this.length, this.breadth) : area = length * breadth;

  // Factory constructor
  factory Area(int length, int breadth) {
    if (length < 0 || breadth < 0) {
      throw Exception("Length and breadth must be positive");
    }
    // redirect to private constructor
    return Area._internal(length, breadth);
  }
}

void main() {
  // This works
  Area area = Area(10, 20);
  print("Area is: ${area.area}");

  // notice that here is negative value
  Area area2 = Area(-10, 20);
  print("Area is: ${area2.area}");
}
```
