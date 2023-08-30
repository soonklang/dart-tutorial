# List in Dart (replace-end)
# การแทนที่ช่วงใน List
เราสามารถแทนที่ค่าในลิสในช่วงที่เราเลือกโดยใช้เมดตอท replaceRange() โดยเมดตอทจะทำการลบค่าที่อยู่ในช่วงเริ่มจนถึงค่าสิ้นสุดที่ตามเรากำหนด
Ex.
	void main() {
 	 List<int> list = [5, 3, 1, 4, 5];
	  print("ก่อนใช้ replaceRange ${list}");
	  list.replaceRange(1, 4, [8, 2]);
	  print("หลังใช้ replaceRange ${list}");
	 }

 output
 	ก่อนใช้ replaceRange [5, 3, 1, 4, 5]
	หลังใช้ replaceRange [5, 8, 2, 5]
 
#
