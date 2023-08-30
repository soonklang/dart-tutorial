# STRING IN DART

## Methods Of String
*	trim(): ส่งกลับสตริงโดยไม่มีช่องว่างนำหน้าและต่อท้าย
* compareTo(): เปรียบเทียบวัตถุนี้กับวัตถุอื่น
*  replaceAll(): แทนที่สตริงย่อยทั้งหมดที่ตรงกับรูปแบบที่ระบุด้วยค่าที่กำหนด
*   split(): แยกสตริงที่ตรงกับตัวคั่นที่ระบุและส่งคืนรายการสตริงย่อย
*    toString(): ส่งกลับการแสดงสตริงของวัตถุนี้
* string(): ส่งกลับสตริงย่อยของสตริงนี้ที่ขยายจาก startIndex แบบรวม ถึง endIndex แบบเอกสิทธิ์เฉพาะบุคคล
*  codeUnitAt(): ส่งกลับหน่วยรหัส UTF-16 16 บิตที่ดัชนีที่กำหนด

## Trim String In Dart

Return สตริงใหม่โดยการลบช่องว่างนำหน้าและต่อท้ายทั้งหมด และยังสามารถใช้เมธอด trimLeft() และ trimRight() เพื่อลบช่องว่างจากซ้ายและขวาตามลำดับ

> หมายเหตุ: วิธีการ trim() ใน Dart จะไม่ลบช่องว่างตรงกลาง 

#### Return Type
Return ค่าสตริง

#### ตัวอย่าง trim() ในภาษา Dart
```dart
void main() { 
   String str1 = "hello"; 
   String str2 = "hello world"; 
   String str3 = "hello"; 
   
   print(str1.trim()); 
   print(str2.trim()); 
   print(str3.trim()); 
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>hello 
hello world 
hello</code></pre>
</details>
<br>

## Compare String In Dart

ส่งกลับสตริงใหม่โดยการลบช่องว่างนำหน้าและต่อท้ายทั้งหมด วิธีการนี้สามารถเปรียบเทียบสตริงสองสตริงได้ 

#### Return Type
Return จำนวนเต็มที่แสดงถึงความสัมพันธ์ระหว่างสองสตริง
   0 - เมื่อสตริงเท่ากัน
   1 - เมื่อสตริงแรกมากกว่าสตริงที่สอง
   -1 - เมื่อสตริงแรกมีขนาดเล็กกว่าสตริงที่สอง

   #### ตัวอย่าง compareTo() ในภาษา Dart
```dart
void main() { 
   String str1 = "A"; 
   String str2 = "A"; 
   String str3 = "B"; 
   
   print("str1.compareTo(str2): ${str1.compareTo(str2)}"); 
   print("str1.compareTo(str3): ${str1.compareTo(str3)}"); 
   print("str3.compareTo(str2): ${str3.compareTo(str2)}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>str1.compareTo(str2): 0 
str1.compareTo(str3): -1 
str3.compareTo(str2): 1 </code></pre>
</details>
<br>

## Replace String In Dart

สามารถแแทนที่ค่าหนึ่งด้วยอีกค่าหนึ่งด้วยวิธีแทนที่ทั้งหมด("เก่า", "ใหม่") ใน Dart มันจะแทนที่คำ "เก่า" ทั้งหมดด้วย "ใหม่" 

#### Return Type
Return ค่าสตริง


  #### ตัวอย่าง replaceAll() ในภาษา Dart
```dart
void main() { 
   String str1 = "Hello World"; 
   print("New String: ${str1.replaceAll('World','ALL')}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>New String: Hello ALL </code></pre>
</details>
<br>



   
