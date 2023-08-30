# List in Dart (replace-end)
# การแทนที่ช่วงใน List
เราสามารถแทนที่ค่าในลิสในช่วงที่เราเลือกโดยใช้เมดตอท replaceRange() โดยเมดตอทจะทำการลบค่าที่อยู่ในช่วงเริ่มจนถึงค่าสิ้นสุดที่ตามเรากำหนด
void main() {
 List<int> list = [1, 2, 3, 4, 5];
 print("${list}");
list.replaceRange(1, 4, [6, 7]);
print("${list}");
}
