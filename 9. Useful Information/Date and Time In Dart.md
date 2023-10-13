# Date and Time In Dart

## การดึงเวลาปัจจุบันจากในเครื่องมาใช้
Example
``` dart
void main() {
  print(DateTime.now());
}
```
Output
``` dart
2023-09-01 14:18:31.310711
```
## ถ้าต้องการYear Month Day ของ Datetime 
รวมถึง Hour Minute Second Milliseconds และMicroseconds

Example
``` dart
void main() {
  DateTime datetime = DateTime.now();
  print("Year is " + datetime.year.toString());
  print("Month is " + datetime.month.toString());
  print("Day is ${datetime.day}"); // If you don't want to use .toString()
  print("Hour is " + datetime.hour.toString());
  print("Minutes is " + datetime.minute.toString());
  print("Second is " + datetime.second.toString());
}
```
Output
``` dart
Year is 2023
Month is 9
Day is 1
Hour is 14
Minutes is 26
Second is 34
```
## การแปลง Datetime เป็น String 
ใช้ methods `.toString()`

Example
``` dart
void main() {
  String datetime = DateTime.now().toString();
  print(datetime);
}
```
Output
``` dart
  2023-09-01 14:29:00.668877
``` 
## การแปลง String เป็น Datetime
ในกรณีที่รับค่าเข้ามาเราไม่สามารถรับวัน เดือน และปีได้โดยตรง แต่ไม่สามารถดําเนินการคํานวณวันที่โดยใช้ String ได้ ดังนั้นเราต้องแปลง String เป็น DateTime ก่อน

ใช้ methods `DateTime.parse()`

Example
``` dart
void main() {
  String myDateInString = "2023-09-21";
  DateTime myConvertedDate = DateTime.parse(myDateInString);
  print("Year is " + myConvertedDate.year.toString());
  print("Month is " + myConvertedDate.month.toString());
  print("Day is " + myConvertedDate.day.toString());
}
```
Output
``` dart
Year is 2023
Month is 9
Day is 21
```
## การเพิ่มจำนวนวันและเวลาใน Datetime
ใช้ method `.add()`

Example
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("2002-09-21");
  myBirthday = myBirthday.add(Duration(days: 1));
  print("Year is " + myBirthday.year.toString());
  print("Month is " + myBirthday.month.toString());
  print("Day is " + myBirthday.day.toString());
}
```
Output
``` dart
Year is 2023
Month is 9
Day is 22
```

## การลดจำนวนวันและเวลาใน Datetime
ใช้ method `.subtract()`

Example
``` dart
void main() {
  DateTime myBirthday = DateTime.parse("2002-09-21");
  myBirthday = myBirthday.subtract(Duration(days: 2));
  print("Year is " + myBirthday.year.toString());
  print("Month is " + myBirthday.month.toString());
  print("Day is " + myBirthday.day.toString());
}
```
Output
``` dart
Year is 2023
Month is 9
Day is 19
```
## การหาระยะความต่างของวันที่ใน Dart
ใช้ method `.difference()`

Example
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
Output
``` dart
Difference in days: 7650
Difference in hours: 183614
Difference in minutes: 11016876
```
## การเปรียบเทียบ Datetime ที่มาก่อนหรือมาหลัง
ใช้ methods `.isBefore() `มาก่อน, `.isAfter() `มาหลัง, `.isAtSameMomentAs() `วันเดัยวกัน

Example
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
Output
``` dart
My Birthday is before today.
```

## การเช็คว่า Datetime เท่ากันหรือไม่
ใช้ method `.compareTo()` ให้ผลลัพธ์เป็น 0 (equal) และ -1 (not equal)

Example
``` dart
void main() {
  var songKranDay = DateTime.utc(2023, 04, 13);
  var happyDay = DateTime.parse("2023-02-14 20:18:04Z");
  print(songKranDay.compareTo(songKranDay)); 
  print(happyDay.compareTo(songKranDay));  
}
```
Output
``` dart
0 
-1 
```
## การ return DateTime เป็นของ UTC time
ใช้ method `.toUtc()`

Example
``` dart
void main() {
  var songKranDay = DateTime.utc(2023, 04, 13);
  var happyDay = DateTime.parse("2023-02-14 20:18:04Z");
  print(happyDay.toUtc()); 
  print(happyDay.timeZoneName); // .timeZoneName() เป็น method เช็ค timezone
}
```
Output
``` dart
2023-02-14 20:18:04.000Z
UTC
```
> UTC (Coordinated Universal Time) หน่วยของเวลาในมาตรฐานของ GMT ที่ใช้ในการอ้างอิงการหมุนของโลก ใช้นาฬิกาอะตอม (Atomic clock) เป็นตัวกำหนดเวลา โดยการนับการสั่นของอะตอม


# ตัวอย่าง Date and time in Java
 ในภาษา Java จะไม่มี class Date มาในตัวซึ่งต่างจากภาษา Dart ที่มีอยู่แล้ว แต่ใน Java สามารถ import package `java.time` ที่ใช้เกี่ยวกับวันที่และเวลาได้ ตัวอย่างเช่น
 - Class
 
       LocalDate       แสดงวันที่ (year, month, day (yyyy-MM-dd))

       LocalTime       แสดงเวลา (hour, minute, second and nanoseconds (HH-mm-ss-ns))
  
       LocalDateTime   แสดงทั้งวันที่และเวลา (yyyy-MM-dd-HH-mm-ss-ns)
  
       DateTimeFormatter   ใช้สำหรับแสดงแยกส่วนวัตถุของวันที่และเวลา

 Example
 ``` Java
 import java.time.LocalDate; // import the LocalDate class

 public class Main {
  public static void main(String[] args) {
   LocalDate myObj = LocalDate.now(); // Create a date object
   System.out.println(myObj); // Display the current date
  }
 }
```
Output
``` Java
2023-09-01
```
### Formatting Date and Time

เราสามารถใช้class `DateTimeFormatter` กับmethod `ofPattern()` ในแพ็คเกจเดียวกันเพื่อจัดรูปแบบหรือแยกวัตถุของ date-time ตัวอย่างต่อไปนี้จะลบทั้ง "T" และนาโนวินาทีออกจากวันที่และเวลา

Example
``` Java
import java.time.LocalDateTime; // Import the LocalDateTime class
import java.time.format.DateTimeFormatter; // Import the DateTimeFormatter class

public class Main {
  public static void main(String[] args) {
    LocalDateTime myDateObj = LocalDateTime.now();
    System.out.println("Before formatting: " + myDateObj);
    DateTimeFormatter myFormatObj = DateTimeFormatter.ofPattern("dd-MM-yyyy HH:mm:ss");

    String formattedDate = myDateObj.format(myFormatObj);
    System.out.println("After formatting: " + formattedDate);
  }
}
```
Output
``` Java
Before Formatting: 2023-09-01T14:14:45.189226 
After Formatting: 01-09-2023 14:14:45
```
- method `ofPattern()` ใช้จัดรูปแบบที่เราต้องการแสดงวันที่และเวลาในรูปแบบอื่นและสามารถใช้ได้กับทุกค่า

Example  

    yyyy-MM-dd      ->  "1988-09-29"	

    dd/MM/yyyy      ->  "29/09/1988"	

    dd-MMM-yyyy     ->  "29-Sep-1988"	

    E, MMM dd yyyy  ->  "Thu, Sep 29 1988"

### เทียบการเพิ่มและลด Datetime, ระยะของ Datetime ที่ต่างกัน
- การเพิ่ม Datetime
``` Java
val next2Days = date.plusDays(2)
```
- การลด Datetime
``` Java
val previous2Months = date.minusMonths(2)
```
- ระยะ datetime ที่ต่างกัน
ใช้ method `ChronoUnit.(object ของ Datetime).between( , )`
``` Java
val dateTimeA: LocalDateTime = /* ... */
val dateTimeB: LocalDateTime = /* ... */
val diffInHour = ChronoUnit.HOURS.between(dateTimeA, dateTimeB)
```
# ตัวอย่าง Date and time in Python
Datetime ใน Python ไม่ใช่ data type แต่เราสามารถ import module `datetime` เพื่อทำงานกับวันที่เป็นวัตถุวันที่

Example 
``` Python
import datetime

x = datetime.datetime.now()
print(x)
```
Output
``` Python
2023-09-01 15:21:18.035686
```
### หากต้องการข้อมูลเกี่ยวกับ object อื่นๆใน Datetime
เช่น year, month, day, hour, minute, second, and microsecond.
สามารถใช้ method `.year` `.mouth` เช่นเดียวกับภาษา Dart 

Example
``` Python
import datetime

x = datetime.datetime.now()
print(x.day)
print(x.hour)
```
Output
``` Python
1
15
```
- แต่ใน python object`datetime`มี method สำหรับ date object ที่เป็น String ที่อ่านได้
method นี้เรียกว่า `strftime()` และใช้ 1 พารามิเตอร์และformat เพื่อระบุรูปแบบของ String ที่ส่งคืน

Example
``` Python
import datetime

x = datetime.datetime(2018, 6, 1)
print(x.strftime("%B")) // %B	Month name, full version
```
Output
``` Python
June
```
  
ซึ่งในตัวอย่างนี้ "%B" เป็นแค่ส่วนนึงของ Date format codes 

# ตัวอย่าง Date and time in C
- การแสดงผลเวลาในภาษา C
ในการทำงานกับวันที่และเวลาในภาษา C เราใช้ฟังก์ชัน ctime สำหรับจัดรูปแบบการแสดงผลของวันที่ในรูปแบบที่มนุษย์สามารถเข้าใจได้ แต่ฟังก์ชันนี้สนับสนุนเพียงแค่รูปแบบเดียวนั่นคือ

Www Mmm dd hh:mm:ss yyyy
นี่เป็นรูปแบบของวันที่ที่เราสามารถแปลงได้โดยการใช้ฟังก์ชัน ctime() โดยการส่งออบเจ็คของเวลาเข้าไปยังฟังก์ชัน และเราจะได้เวลาในรูปแบบ C-string ที่สอดคล้องกับเวลาท้องถิ่นจากออบเจ็คของเวลาดังกล่าว ยกตัวอย่างเช่น

Example
``` c
#include <stdio.h>
#include <time.h> // นำเข้าไลบรารี time.h เพื่อใช้งานฟังก์ชันเกี่ยวกับวันที่และเวลา

int main()
{
    time_t now;
    time(&now);

    printf("The current local time is: %s", ctime(&now));
    printf("The current timestamp is: %ld", now);
    return 0;
}
```

Output
``` c
The current local time is: Fri Sep  1 15:12:57 2023
The current timestamp is: 1693581177
```
### ภาษา C มีการจัดรูปแบบของวันที่และเวลาที่ใช้function `strftime()` 
จะเก็บผลลัพธ์ลงในตัวแปรarray buffer ที่มีขนาดไม่เกิน 80 ตัวอักษร รูปแบบที่ใช้ในการจัดรูปแบบการแสดงผลคือ %d %B %Y %H:%M:%S และค่านำเข้าของเวลาที่ใช้ในการจัดรูปแบบคือ timeinfo

Example
``` c
#include <stdio.h>
#include <time.h>

int main ()
{
    time_t rawtime;
    struct tm * timeinfo;
    char buffer[80];

    time(&rawtime);
    timeinfo = localtime(&rawtime);

    strftime(buffer, 80, "%B %d, %Y %I:%M:%S %p", timeinfo);
    printf("%s\n", buffer);

    strftime(buffer, 80, "%Y-%m-%dT%H:%M:%SZ", timeinfo);
    printf("%s\n", buffer);
    return 0;
}
```

Output
``` c
September 01, 2023 03:14:07 PM
2023-09-01T15:14:07Z
```

> ซึ่งในภาษา C มีรูปแบบการใช้ Date format codes คล้ายกับภาษา python

## Reference
[Date and time in Dart](https://dart-tutorial.com/useful-information/date-time-in-dart/)<br>
[Date and time in Dart](https://siriphonnot.medium.com/7-ฟังก์ชันสำหรับ-datetime-ที่ควรรู้ในภาษา-dart-cad22cc61504)<br>
[Date and time in Java](https://www.w3schools.com/java/java_date.asp)<br>
[Date and time in Java](https://akexorcist.dev/datetime-api-in-java-8-cheatsheet/)<br>
[Date and time in Python](https://www.w3schools.com/python/python_datetime.asp)<br>
[Date and time in C](http://marcuscode.com/lang/c/date-and-time-formats)

## Slide
[Date_and_Time](https://drive.google.com/file/d/1ErxLdy1oYK4Jlbzk4Jzs7HqbdJXhHL7y/view?usp=drivesdk)
[DateandTime.pdf](https://github.com/soonklang/dart-tutorial/files/12889458/DateandTime.pdf)


## Video
https://youtu.be/_TP8emNyrU8?si=Hi47ev2IP73jvfkd
