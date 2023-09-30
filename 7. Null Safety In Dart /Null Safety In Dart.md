# Null Safety In Dart

Null safety คือคุณสมบัติหนึ่งในภาษาโปรแกรม Dart ที่ช่วยผู้พัฒนาเพื่อป้องกันข้อผิดพลาดที่เกิดจากค่า null ฟีเจอร์นี้เรียกว่า "Sound Null Safety" ใน Dart นี้ ซึ่งช่วยให้ผู้พัฒนาสามารถตรวจจับข้อผิดพลาดที่เกิดจากค่า null ในขั้นตอนการแก้ไขโค้ดได้ในขณะที่กำลังแก้ไขโค้ดอยู่


# Advantage Of Null Safety (ข้อดี)

- เขียนโค้ดที่ปลอดภัย
- ลดโอกาสเกิดข้อผิดพลาดของแอปพลิเคชัน
- ง่ายต่อการค้นหาและแก้ไขข้อบกพร่องในโค้ด

## Note: 
คุณสมบัติ Null safety ช่วยป้องกันข้อผิดพลาดที่เกิดจากค่า null, ข้อบกพร่องระหว่างรันไทม์, ช่องโหว่และความผิดพลาดของระบบที่ยากต่อการค้นหาและแก้ไข

# Example 1: Using Null In Variables (การใช้ค่า Null ในตัวแปร)

ในตัวอย่างด้านล่างนี้ ตัวแปรชื่อ age เป็นชนิด int หากคุณใส่ค่า null เข้าสู่ตัวแปรนี้ จะทำให้เกิดข้อผิดพลาดทันที

```dart
void main() { 
   int age = null; // give error
}
```

# Non-Nullable By Default

ใน Dart ตัวแปรและฟิลด์จะไม่มีค่า Null ตามค่าเริ่มต้น ซึ่งหมายความว่าตัวแปรและฟิลด์จะไม่สามารถมีค่าเป็น Null ได้ เว้นแต่คุณจะอนุญาตไว้อย่างชัดเจน

```dart
int productid = 20; // non-nullable
int productid = null; // give error
```
# How To Declare Null Value (วิธีการประกาศค่า Null)

ด้วย Dart Sound Null Safety (ความปลอดภัยจากค่า null ใน Dart) คุณไม่สามารถกำหนดค่า null ได้โดยค่าเริ่มต้น หากคุณมั่นใจ 100% ในการใช้ค่า null คุณสามารถใช้ตัวดำเนินการ ? หลังจากประกาศชนิดข้อมูลได้

```dart
// Declaring a nullable variable by using ?
String? name;
```
การประกาศตัวแปรชื่อ (name) ที่อาจจะเป็นค่า null หรือเป็นสตริง (string)

# How To Assign Values To Nullable Variables (วิธีการกำหนดค่าให้กับตัวแปรที่สามารถเป็นค่า null ได้)

คุณสามารถกำหนดค่าให้กับตัวแปรที่สามารถเป็นค่า null ได้เหมือนกับตัวแปรอื่นๆ อย่างไรก็ตามคุณยังสามารถกำหนดค่าเป็น null ให้กับตัวแปรเหล่านั้นได้ด้วย
```dart
void main(){
// Declaring a nullable variable by using ?
String? name;
// Assigning John to name
name = "John";
// Assigning null to name
name = null;
}
```
# How To Use Nullable Variables (วิธีการใช้งานตัวแปรที่สามารถเป็นค่า null ได้)

คุณสามารถใช้ตัวแปรที่สามารถเป็นค่า null ได้ในหลายวิธี เช่น
- คุณสามารถใช้คำสั่ง if เพื่อตรวจสอบว่าตัวแปรเป็นค่า null หรือไม่
- คุณสามารถใช้ตัวดำเนินการ ! ซึ่งจะคืนค่า null หากตัวแปรเป็นค่า null
- คุณสามารถใช้ตัวดำเนินการ ? เพื่อกำหนดค่าเริ่มต้นหากตัวแปรเป็นค่า null

# Example 2: Define List Of Nullable Items (การกำหนด List ที่สามารถเป็นค่า null ได้)

คุณยังสามารถเก็บค่า null ใน list ได้เช่นกัน ในตัวอย่างนี้ List items เป็นรายการของจำนวนเต็มที่สามารถเป็นค่า null ได้ มันสามารถมีค่า null และจำนวนเต็มได้ด้วย
```dart
void main() {
  // list of nullable ints
  List<int?> items = [1, 2, null, 4];
  print(items);
}
```

# Example 3: Null Safety In Dart Functions (Null Safety ในฟังก์ชันของ Dart)

ในตัวอย่างนี้ ฟังก์ชัน printAddress มีพารามิเตอร์ชื่อ address ที่เป็นชนิดข้อมูล String หากคุณส่งค่า null เข้าไปในฟังก์ชันนี้ จะเกิดข้อผิดพลาดระหว่างเวลาแก้ไข (edit-time error)
```dart
void printAddress(String address) {
  print(address);
}

void main() {
  printAddress(null); // give error
}
```

# Example 4: Define Function With Nullable Parameter (การกำหนดฟังก์ชันที่มีพารามิเตอร์ที่สามารถเป็นค่า null ได้)

หากคุณมั่นใจ 100% คุณสามารถใช้เครื่องหมาย ? สำหรับการประกาศชนิดข้อมูล ในตัวอย่างนี้ ฟังก์ชัน printAddress มีพารามิเตอร์ชื่อ address ที่เป็นชนิดข้อมูล String? คุณสามารถส่งค่า null และค่าสตริงไปยังฟังก์ชันนี้ได้

```dart
  // address is a nullable string
void printAddress(String? address) {
  print(address);
}
void main() {
  // Passing null to printAddress
  printAddress(null); // Works
}
```
# Example 5: Null Safety In Dart Classes (Null Safety ในคลาสของ Dart)

ในตัวอย่างนี้ คลาส Person มีพารามิเตอร์ชื่อ name ที่เป็นชนิดข้อมูล String หากคุณส่งค่า null เข้าไปในคลาสนี้ จะเกิดข้อผิดพลาดระหว่างเวลาคอมไพล์ (compile-time error)

```dart
class Person {
  String name;
  Person(this.name);
}

void main() {
  Person person = Person(null); // give error
}
```
# Example 6: Define Null To Class Property (การกำหนดค่า null ให้กับคุณสมบัติของคลาส)

ในตัวอย่างนี้ คลาส Person มีพารามิเตอร์ชื่อ name ที่เป็นชนิดข้อมูล String? คุณสามารถส่งค่า null และค่าสตริงไปยังคลาสนี้ได้ ในการกำหนดคุณสมบัติที่เป็นค่า null ในคลาส คุณสามารถใช้ตัวดำเนินการ ? หลังจากประเภทข้อมูล
```dart
class Person {
  String? name;
  Person(this.name);
}

void main() {
  Person person = Person(null); // Works
}
```
# Example 7: Working With Nullable Class Properties (การทำงานกับคุณสมบัติของคลาสที่สามารถเป็นค่า null ได้)

ในตัวอย่างด้านล่างนี้ คลาส Profile มีคุณสมบัติสองอย่างที่สามารถเป็นค่า null ได้: name และ bio วิธี printProfile จะพิมพ์ชื่อและข้อมูลประวัติส่วนตัวของโปรไฟล์ หาก name หรือ bio เป็นค่า null จะพิมพ์ค่าเริ่มต้นแทน

```dart
  class Profile {
  String? name;
  String? bio;

  Profile(this.name, this.bio);

  void printProfile() {
    print("Name: ${name ?? "Unknown"}");
    print("Bio: ${bio ?? "None provided"}");
  }
}

void main() {
  // Create a profile with a name and bio
  Profile profile1 = Profile("John", "Software engineer and avid reader");
  profile1.printProfile();

  // Create a profile with only a name
  Profile profile2 = Profile("Jane", null);
  profile2.printProfile();

  // Create a profile with only a bio
  Profile profile3 = Profile(null, "Loves to travel and try new foods");
  profile3.printProfile();

  // Create a profile with no name or bio
  Profile profile4 = Profile(null, null);
  profile4.printProfile();
}
```

# Important Point In Dart Null Safety (จุดสำคัญของ Null Safety ใน Dart)

- ค่า null หมายถึงไม่มีค่า
- ข้อผิดพลาดที่พบบ่อยในการเขียนโปรแกรมเกิดจากค่า null
- Dart 2.12 นำเสนอความปลอดภัยจากค่า null ที่เรียกว่า "sound null safety" เพื่อแก้ไขปัญหาที่เกี่ยวกับค่า null
- ประเภทที่ไม่สามารถเป็นค่า null ได้ถูกยืนยันว่าจะไม่เป็นค่า null แน่นอน

# ตัวอย่างเพิ่มเติมจากเว็ป dart.dev

การแนะนำผ่านตัวอย่าง
ด้วย Null Safety ไม่มีตัวแปรใดในรหัสด้านล่างนี้ที่สามารถเป็นค่า null ได้:

```dart
// With null safety, none of these can ever be null.
var i = 42; // Inferred to be an int.
String name = getFileName();
final b = Foo();
```
เพื่อแสดงว่าตัวแปรอาจมีค่าเป็น null เพียงแค่เพิ่ม ? ในประกาศชนิดข้อมูลของมัน:

```dart
int? aNullableInt = null;
```

# หลักการของ Null Safety

Dart รองรับ Null Safety โดยใช้หลักการออกแบบต่อไปนี้:
- Non-nullable by default หากคุณไม่ระบุเป็นชัดเจนว่าตัวแปรใดสามารถเป็นค่า null ได้ ใน Dart จะถือว่าเป็นค่าที่ไม่สามารถเป็นค่า null ได้ เรื่องนี้ได้รับการกำหนดค่ามาตรฐานเนื่องจากการวิจัยพบว่าเป็นสิ่งที่พบบ่อยที่สุดใน APIs
- Fully sound ความปลอดภัยจากค่า null ใน Dart เป็นเสียง ซึ่งช่วยให้เกิดการปรับปรุงแบบคอมไพล์ หากระบบประเภทกำหนดให้สิ่งบางอย่างไม่เป็นค่า null แสดงว่าสิ่งนั้นไม่สามารถเป็นค่า null ได้ ไม่เพียงแค่ลดจำนวนข้อผิดพลาด แต่ยังลดขนาดไบนารีและเพิ่มความเร็วในการประมวลผล

## แหล่งอ้างอิง https://dart.dev/null-safety

# Null Safety In Dart เมื่อเทียบกับภาษาอื่น

## Dart และ Kotlin:

- Dart มี Null Safety ที่เป็นความครอบคลุมและรองรับความปลอดภัยทั้งการคอมไพล์และเวลารันโปรแกรม (sound null safety) ซึ่งให้ประสิทธิภาพสูงในการประมวลผล และช่วยลดข้อผิดพลาดระหว่างเวลาคอมไพล์และรัน
- Kotlin ก็มีระบบป้องกันค่า null ที่เป็นความปลอดภัยและรองรับประสิทธิภาพเสมือนเช่นกัน แต่มันเรียกว่า "nullable types" และ "non-nullable types" แทน

## Dart และ Java:

- Dart มี Null Safety ที่เป็นความครอบคลุมและรองรับความปลอดภัยทั้งการคอมไพล์และเวลารันโปรแกรม (sound null safety) ซึ่งให้ประสิทธิภาพสูงในการประมวลผล และช่วยลดข้อผิดพลาดระหว่างเวลาคอมไพล์และรัน
- ใน Java ไม่มีการจัดการเฉพาะกับค่า null เช่นใน Dart และ Kotlin ซึ่งอาจทำให้เกิดข้อผิดพลาดแบบ NullPointerException ในระหว่างการเรียกใช้

## Dart และ Python:

- Dart มี Null Safety ที่เป็นความครอบคลุมและรองรับความปลอดภัยทั้งการคอมไพล์และเวลารันโปรแกรม (sound null safety) ซึ่งให้ประสิทธิภาพสูงในการประมวลผล และช่วยลดข้อผิดพลาดระหว่างเวลาคอมไพล์และรัน
- Python ไม่มีระบบความปลอดภัยจากค่า null และเมื่อค่า null ถูกใช้ในที่ที่ไม่เหมาะสมอาจเกิดข้อผิดพลาดแบบ AttributeError หรือ NoneType ในระหว่างการทำงาน

## สรุป: 

Dart มีความปลอดภัยจากค่า null และระบบป้องกันค่า null ที่มีประสิทธิภาพ โดยภาษาอื่น ๆ อาจมีแนวคิดคล้ายกันแต่อาจมีลักษณะและการทำงานที่แตกต่างกันไปเล็กน้อย การเลือกภาษาที่เหมาะสมกับโปรเจคของคุณนั้นขึ้นอยู่กับความต้องการและการพิจารณาความปลอดภัยจากค่า null ที่คุณต้องการในโปรเจคของคุณ

# Slide

[Null Safety In Dart.pdf](https://github.com/soonklang/dart-tutorial/files/12774141/640710545.pdf)

# Video

[Video](https://www.youtube.com/watch?v=JbUw-iChiWA)

### Reference

- https://dart-tutorial.com/null-safety/null-safety-in-dart/
- https://dart.dev/null-safety
