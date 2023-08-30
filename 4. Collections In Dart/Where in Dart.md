# Where in Dart
Where ใช้ในการแสดงผลเฉพาะข้อมูลที่เราต้องการตามเงื่อนไขที่ตั้งไว้จากข้อมูลที่มีปริมาณมาก เข่น List,Set
## Syntax
```dart
Iterable<E> where(bool f(E element))
```
## เปรียบเทียบกับภาษาอื่นๆ
ในภาษาโปรแกรมอื่นมักใช้คำสั่งว่า filter  
**Java**
```Java
List<String> languageList = Arrays.asList("Java", "Python", "C#");

String language = languageList.stream().filter(languageInList ->"Python".equals(languageInList));
        
System.out.println(language);
```
**Python**
```Python
language_list = ["Java", "Python", "C#"]

filtered_languages = filter(lambda lang: lang == "Python", language_list)
language = next(filtered_languages, "PHP")

print(language)
```
**Dart**
```Dart
void main() {
  List<String> languageList = ["Java", "Python", "C#"];

  var filteredLanguages = languageList.where((lang) => lang == "Python");
  var language = filteredLanguages.isNotEmpty ? filteredLanguages.first : "PHP";

  print(language);
}

```
## Example
**1.Filter เฉพาะเลขคี่จาก List**
```Dart
void main() {
  List<int> numbers = [2, 4, 6, 8, 10, 11, 12, 13, 14];

  List<int> oddNumbers = numbers.where((number) => number.isOdd).toList();
  print(oddNumbers);
}
```
**Output**
```Dart
[11, 13]
```
**2.Filter วันที่เรื่มต้นด้วย "S"**
```Dart
void main() {
  List<String> days = [
    "Sunday",
    "Monday",
    "Tuesday",
    "Wednesday",
    "Thursday",
    "Friday",
    "Saturday"
  ];

  List<String> startWithS =
      days.where((element) => element.startsWith("S")).toList();

  print(startWithS);
}
```
**Output**
```Dart
[Sunday, Saturday]
```
**3.Filter ใน maps หาคะแนนนักเรียนที่ได้มากกว่าหรือเท่ากับ 32**
```Dart
void main() {
  Map<String, double> mathMarks = {
    "ram": 30,
    "mark": 32,
    "harry": 88,
    "raj": 69,
    "john": 15,
  };

  mathMarks.removeWhere((key, value) => value < 32); # ใช้ removeWhere เพื่อเอาสิ่งที่ไม่ต้องการออก ในทีนี้คือค่า value ที่น้อยกว่า 32 ให้เอาออกไป #

  print(mathMarks);
}
```
**Output**
```Dart
{mark: 32.0, harry: 88.0, raj: 69.0}
```
### *< Reference >*
[Where in Dart :: Dart Tutorial - Learn Dart Programming (dart-tutorial.com)](https://dart-tutorial.com/collections/where-in-dart/)

[[Dart] รวมคำสั่งดีๆ เอาไว้ใช้กับ List – TAmemo.com](https://www.tamemo.com/post/177/dart-list-helper-method/)





