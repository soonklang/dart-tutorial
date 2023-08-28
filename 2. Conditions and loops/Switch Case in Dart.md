# Switch Case in Dart

ใน tutorial นี้คุณจะเรียนรู้การใช้ switch case ในภาษา Dart เพื่อควบคุมกระแสของโปรแกรมของคุณ คำสั่ง switch case ใช้ในการประมวลผลบล็อกของโค้ดตามเงื่อนไขที่กำหนด

### Switch Case Statement
คำสั่ง **Switch case** ในภาษา Dart ถูกใช้เพื่อหลีกเลี่ยงการใช้เงื่อนไข if-else แบบ long chain เป็นรูปแบบที่เรียบง่ายของคำสั่ง if-else ที่ซ้อนกัน ค่าของตัวแปรจะถูกเปรียบเทียบกับหลายๆกรณี และหากพบการตรงกัน จะมีการประมวลผลบล็อกของคำสั่งที่เกี่ยวข้องกับกรณีนั้น ค่าที่กำหนดไว้จะถูกเปรียบเทียบกับแต่ละกรณีจนกว่าจะพบการตรงกัน เมื่อจากพบค่าที่ตรงกันแล้ว จะระบุบล็อกของโค้ดที่จะถูกประมวลผล

### หลักการทำงานของ Switch Case
![image](https://github.com/chonnigan/PL/assets/95559071/7ca7de28-0d4c-4dc6-be58-103475d071fc)

## Syntax
- ### ในภาษา Dart , C, Java , Javascript ใช้ switch case
```
switch(expression) {
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
    case value3:
        // statements
        break;
    default:
       // default statements
}
```
คำอธิบาย

- นิพจน์ถูกประเมินครั้งเดียวและเปรียบเทียบกับค่าของแต่ละ **case**
- หากนิพจน์ตรงกับค่าของ case ค่าที่ 1 คำสั่งใน case ค่าที่ 1 จะถูกประมวลผล ในทางเดียวกัน กรณีค่าที่ 2 จะถูกประมวลผลหากนิพจน์ตรงกับ case ค่าที่ 2 ถ้านิพจน์ตรงกับค่าของ case ค่าที่ 3 คำสั่งใน case ค่าที่ 3 จะถูกประมวลผล
- คีย์เวิร์ด **break** ใช้ในการบอก Dart ให้ออกจากคำสั่ง switch เนื่องจากคำสั่งในบล็อก case เสร็จสิ้น
- หากไม่มีการตรงกัน คำสั่งในบล็อก **default** จะถูกประมวลผล

> [!NOTE]
> **สามารถใช้ Switch case เพื่อเป็นทางเลือกแทนเงื่อนไข if-else-if ได้**

- ### Python ใช้ match case
```
parameter = "Geeksforgeeks"
match parameter:
    case first  :
        do_something(first)
    case second :
          do_something(second)       
    case third :
        do_something(third)
        .............
        ............
    case n :
        do_something(n)
    case _  :
          nothing_matched_function()
```


