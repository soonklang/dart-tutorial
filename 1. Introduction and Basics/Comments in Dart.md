# Comments in dart
  comment เป็นชุดคำสั่งที่ถูกละเว้นโดย dart compiler ระหว่างการทำงานของโปรแกรม ใช้เพื่ออธิบายโค้ด
เพื่อให้ผู้อื่นสามารถเข้าใจได้ง่าย

## Advantages Of Comments (ข้อดีของ Comments)
  * สามารถอธิบายโค้ดของคุณได้
  * ผู้อื่นจะเข้าใจโค้ดของคุณชัดเจนยิ่งขึ้น

## Types Of Comments (ชนิดของ Comments)
  * Single-Line Comments: สำหรับการแสดงความคิดเห็นในโค้ดบรรทัดเดียว เช่น //.
  * Multi-line comments: สำหรับการแสดงความคิดเห็นในโค้ดหลายบรรทัด เช่น /* และลงท้ายด้วย */.
  * Documentation Comments In Dart: สำหรับสร้างเอกสารหรืออ้างอิงสำหรับโครงการ/ แพ็คเกจซอฟต์แวร์ เช่น ///<br>


**Single-Line Comment**  ขึ้นต้นด้วย // ทุกอย่างที่อยู่ในระหว่าง // ถึงจุดสิ้นสุดของบรรทัดจะถูกละเว้นโดยการ Dart compiler
```
  void main() {
  // TODO: refactor into an AbstractLlamaGreetingFactory?
  print('Welcome to my Llama farm!');
}
```
**Multi-line comments**  ขึ้นต้นด้วย /* และลงท้ายด้วย */. ทุกอย่างที่อยู่ในระหว่าง /* และ */ จะถูกละเว้นโดยการ Dart compiler(เว้นแต่ความคิดเห็นจะเป็นความคิดเห็นในเอกสาร; ดูในหัวข้อถัดไป) ความคิดเห็นหลายบรรทัดสามารถซ้อนกันได้
```
  void main() {
  /*
   * This is a lot of work. Consider raising chickens.

  Llama larry = Llama();
  larry.feed();
  larry.exercise();
  larry.clean();
   */
}
```
**Documentation Comments**  เป็นความคิดเห็นหลายบรรทัดหรือบรรทัดเดียวที่ขึ้นต้นด้วย /// หรือ /**. การใช้/// ในบรรทัดที่ต่อเนื่องกันจะมีผลเช่นเดียวกับความคิดเห็นของเอกสาารหลายบรรทัด <br>
  ภายในความคิดเห็นของเอกสาร ตัววิเคราะห์จะละเว้นข้อความทั้งหมด เว้นแต่จะอยู่ในวงเล็บ การใช้วงเล็บ [ ] ทำให้คุณสามารถอ้างถึงคลาส, เมธอด, ฟิลด์, ตัวแปลระดับสูงสุด, ฟังก์ชัน และพารามิเตอร์ได้

ตัวอย่างความคิดเห็นเกี่ยวกับเอกสารที่มีการอ้างอิงถึงคลาสและอาร์กิวเมนต์อื่น:
```
/// A domesticated South American camelid (Lama glama).
///
/// Andean cultures have used llamas as meat and pack
/// animals since pre-Hispanic times.
///
/// Just like any other animal, llamas need to eat,
/// so don't forget to [feed] them some [Food].
class Llama {
  String? name;

  /// Feeds your llama [food].
  ///
  /// The typical llama eats one bale of hay per week.
  void feed(Food food) {
    // ...
  }

  /// Exercises your llama with an [activity] for
  /// [timeLimit] minutes.
  void exercise(Activity activity, int timeLimit) {
    // ...
  }
}
```


  

