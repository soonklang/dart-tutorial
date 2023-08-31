# DateTime In Dart

## การดึงเวลาปัจจุบันจากในเครื่องมาใช้
 Example
``` dart
void main() {
  print(DateTime.now());
}
```
- Output
## ถ้าต้องการYear Month Day ของ Datetime 
รวมถึง Hour Minute Second Milliseconds และMicroseconds

Example
``` dart
void main() {
  DateTime datetime = DateTime.now();
  print("Year is " + datetime.year);
  print("Month is " + datetime.month);
  print("Hour is " + datetime.hour);
  print("Minutes is " + datetime.minute);
  print("Second is " + datetime.second);
}
```

## การแปลง Datetime เป็น String 
ใช้ methods `.toString()`

Example
``` dart
void main() {
  String datetime = DateTime.now().toString();
  print(datetime);
  print("Day is ${datetime.day}"); // If you don't want to use .toString
}
```

## การแปลง String เป็น Datetime
ในกรณีที่รับค่าเข้ามาเราไม่สามารถรับวัน เดือน และปีได้โดยตร แต่ไม่สามารถดําเนินการคํานวณวันที่โดยใช้ String ได้ ดังนั้นเราต้องแปลง String เป็น DateTime ก่อน

Example
``` dart
void main() {
  String myDateInString = "2022-05-01";
  DateTime myConvertedDate = DateTime.parse(myDateInString);
  print("Year is " + myConvertedDate.year.toString());
  print("Month is " + myConvertedDate.month.toString());
  print("Day is " + myConvertedDate.day.toString());
}
```

## การเพิ่มจำนวนวันและเวลาใน Datetime
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("1997-05-14");
  myBirthday = myBirthday.add(Duration(days: 1));
  print("Year is " + myBirthday.year.toString());
  print("Month is " + myBirthday.month.toString());
  print("Day is " + myBirthday.day.toString());
}
```

## การลดจำนวนวันและเวลาใน Datetime
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("1997-05-14");
  myBirthday = myBirthday.subtract(Duration(days: 1));
  print("Year is " + myBirthday.year.toString());
  print("Month is " + myBirthday.month.toString());
  print("Day is " + myBirthday.day.toString());
}
```
## การหาความแตกต่างของวันที่ใน Dart
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("1997-05-14");
  DateTime today = DateTime.now();
  Duration diff = today.difference(myBirthday);
  print("Difference in days: " + diff.inDays.toString());
  print("Difference in hours: " + diff.inHours.toString());
  print("Difference in minutes: " + diff.inMinutes.toString());
}
```
## การเปรียบเทียบ Datetime ที่มาก่อนหรือมาหลัง
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("2002-09-21");
  DateTime today = DateTime.now();

  if (myBirthday.isBefore(today)) {
    print("My Birthday is before today.");
  } else if (myBirthday.isAfter(today)) {
    print("My Birthday is after today.");
  } else if (myBirthday.isAtSameMomentAs(today)) {
    print("My Birthday date and today's date is same.");
  }
}
```

## การเช็คว่า Datetime เท่ากันหรือไม่
``` dart
void main() {
  var songKranDay = DateTime.utc(2019, 04, 13);
  var happyDay = DateTime.parse("2018-02-14 20:18:04Z");
  songKranDay.compareTo(songKranDay); // => 0 (equal)
  happyDay.compareTo(songKranDay); // => -1 (not equal)
}
```
## การ return DateTime เป็นของ UTC time
``` dart
void main() {
  var songKranDay = DateTime.utc(2019, 04, 13);
  var happyDay = DateTime.parse("2018-02-14 20:18:04Z");
  happyDay.toUtc(); // => 2018-02-14 20:18:04.000Z
  happyDay.timeZoneName; // => UTC
}
```
> UTC (Coordinated Universal Time) หน่วยของเวลาในมาตรฐานของ GMT ที่ใช้ในการอ้างอิงการหมุนของโลก ใช้นาฬิกาอะตอม (Atomic clock) เป็นตัวกำหนดเวลา โดยการนับการสั่นของอะตอม
