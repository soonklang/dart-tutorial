# Comments in dart
  comment เป็นชุดคำสั่งที่ถูกละเว้นโดย dart compiler ระหว่างการทำงานของโปรแกรม ใช้เพื่ออธิบายโค้ด
เพื่อให้ผู้อื่นสามารถเข้าใจได้ง่าย

## Advantages Of Comments (ข้อดีของ Comments)
  * สามารถอธิบายโค้ดของคุณได้
  * ผู้อื่นจะเข้าใจโค้ดของคุณชัดเจนยิ่งขึ้น

## Types Of Comments (ชนิดของ Comments)
  * Single-Line Comment: สำหรับการแสดงความคิดเห็นในโค้ดบรรทัดเดียว เช่น //.
  * Multi-line comments: สำหรับการแสดงความคิดเห็นในโค้ดหลายบรรทัด เช่น /* และลงท้ายด้วย */.
  * Documentation Comment In Dart: สำหรับสร้างเอกสารหรืออ้างอิงสำหรับโครงการ/ แพ็คเกจซอฟต์แวร์ เช่น ///

### Single-Line Comment
  เริ่มต้นด้วย // ทุกอย่างที่อยู่ระหว่าง // ถึงจุดสิ้นสุดของบรรทัดจะถูกละเว้นด้วย Dart compiler
```
  void main() {
  // TODO: refactor into an AbstractLlamaGreetingFactory?
  print('Welcome to my Llama farm!');
}
```  

