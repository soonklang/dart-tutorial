# PRACTICE 8
## 1.อะไรคือโปรแกรมAsychronousในdart
- คือ การเขียนโค้ดในแบบที่ช่วยให้โปรแกรมสามารถทำงานพร้อมกันหลายๆกิจกรรมโดยไม่ต้องรอให้กิจกรรมหนึ่งเสร็จก่อน
ซึ่งมีความสำคัญเมื่อต้องจัดการกับการทำงานที่ใช้เวลานานหรือแบบที่ไม่คาดหวังได้ว่าจะเสร็จสิ้นทันทีเช่นการเขียนข้อมูลลงในไฟล์ เป็นต้น โดยมีการใช้ async และ await
- async: คีย์เวิร์ดที่ใช้ระบุว่าฟังก์ชันนั้นมีการทำงานแบบ asynchronous.
- await: คีย์เวิร์ดที่ใช้รอให้การทำงาน asynchronous เสร็จสิ้นและคืนค่ากลับมาก่อนที่จะดำเนินการ

## 2.Futureคืออะไรในdart
- Future คืออ็อบเจกต์(Object)ที่ใช้ในการจัดการกับการทำงานแบบ asynchronous และการสื่อสารระหว่างส่วนของโปรแกรมที่ทำงานในเวลาต่างๆหรือทำงานพร้อมกัน
  โดย Future จะแทนการสัญญาว่าจะมีข้อมูลหรือผลลัพธ์ที่กำลังจะมาถึงในอนาคตเมื่องาน asynchronous เสร็จสิ้นหรือข้อมูลพร้อมใช้งาน

## 3.เขียนโปรแกรมเพื่อพิมพ์เวลาปัจจุบันหลังจากใช้ Future.delayed() 2 วินาที
~~~ dart
void main() async {
  print("Started at: ${DateTime.now()}");
  await _delayedPrint(); //รอการทำงานเสร็จก่อน
}

Future<void> _delayedPrint() async {
  await Future.delayed(Duration(seconds: 2));
  print("Current time after 2 seconds: ${DateTime.now()}");
}
~~~
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Started at: 2023-08-31 17:30:25.123456
Current time after 2 seconds: 2023-08-31 17:30:27.123456
</code></pre>
</details>

## 4.เขียนโปรแกรมอ่านไฟล์'csv'และแสดง
~~~ dart
import 'dart:io';
import 'package:csv/csv.dart';
Future<void> main() async {
  final csvFilePath = 'path_to_your_csv_file.csv'; // ใส่ที่ ที่ไฟล์csvอยู่
  final input = File(csvFilePath).openRead();
  final fields = await input.transform(utf8.decoder).transform(CsvToListConverter()).toList();
  for (var row in fields) {
    print(row);
  }
}
~~~
ตัวอย่างการนำเข้าไฟล์'csv'
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Name,Age,City
John,30,New York
Jane,25,Los Angeles
Michael,40,Chicago
</code></pre>
</details>

## 5.เขียนโปรแกรมภาษาDartที่ใช้Futureเพื่อดำเนินการแบบ asynchronous รอให้ทำทั้งหมดก่อนแล้วพิมพ์ค่าออกมา

~~~ dart
import 'dart:async';
Future<String> fetchData(String id) {
  return Future.delayed(Duration(seconds: 2), () => 'Data for ID $id');
}
void main() {
  final List<Future<String>> futures = [];
  for (int i = 1; i <= 5; i++) {
    final future = fetchData(i.toString());
    futures.add(future);
  }
  Future.wait(futures)
      .then((List<String> results) {
        print('All operations completed:');
        for (int i = 0; i < results.length; i++) {
          print('Result for operation ${i + 1}: ${results[i]}');
        }
      })
      .catchError((error) {
        print('An error occurred: $error');
      });
}
~~~
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>All operations completed:
Result for operation 1: Data for ID 1
Result for operation 2: Data for ID 2
Result for operation 3: Data for ID 3
Result for operation 4: Data for ID 4
Result for operation 5: Data for ID 5

</code></pre>
</details>

## 6.เขียนโปรแกรมภาษาDartเพื่อคำนวนผลรวมเลข2ตัวที่ใช้ async/await

~~~ dart
Future<int> calculateSum(int a, int b) async {
  await Future.delayed(Duration(seconds: 2));
  return a + b;
}
void main() async {
  try {
    int n1 = 1;
    int n2 = 2;
    int sum = await calculateSum(n1, n2);
    print('$n1 + $n2 : $sum');
  } catch (error) {
    print('An error occurred: $error');
  }
}
~~~
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>1 + 2 : 3
</code></pre>
</details>

## 7.เขียนโปรแกรมDartโดยรับจำนวนเต็มเข้ามา2ตัวรอ3วินาทีจากนั้นพิมพ์ผลรวมของตัวเลขทั้งสอง

~~~ dart
import 'dart:io';
Future<void> calculateSumAndPrint(int a, int b) async {
  await Future.delayed(Duration(seconds: 3));
  int sum = a + b;
  print('$a + $b : $sum');
}
void main() {
  try {
    int num1 = int.parse(stdin.readLineSync()!);
    int num2 = int.parse(stdin.readLineSync()!);
    calculateSumAndPrint(num1, num2);
  } catch (error) {
    print('An error occurred: $error');
  }
}
~~~
Enter : 1 และ Enter : 2
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>1 + 2 : 3
</code></pre>
</details>

## 8.เขียนโปรแกรมDartที่จะรับStringเป็นInputเรียงลำดับรายการแบบ asynchronous จากนั้นพิมพ์รายการที่เรียงลำดับแล้ว

~~~ dart
import 'dart:io';
Future<void> main() async {
  try {
    String input = stdin.readLineSync()!;
    List<String> items = input.split(' ');
    items.sort(); // เรียงลำดับรายการ
    for (String item in items) {
      print(item);
    }
  } catch (error) {
    print('Error : $error');
  }
}
~~~
- Input "Bat Ant Cat"
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>
    Ant
    Bat
    Cat
</code></pre>
</details>

## 9.เขียนโปรแกรมDartที่รับจำนวนเต็มและคูณจำนวนเต็มแต่ละตัวด้วย 2 แบบอะซิงโครนัสจากนั้นพิมพ์รายการที่แก้ไข

~~~ dart
import 'dart:async';
import 'dart:convert';
import 'dart:io';
void main() {
  print('Enter a list of integers separated by spaces:');
  String input = stdin.readLineSync()!;
  List<int> inputList = input.split(' ').map((e) => int.parse(e)).toList();
  multiplyAndPrint(inputList);
}
Future<void> multiplyAndPrint(List<int> numbers) async {
  List<Future<int>> futures = [];
  for (int number in numbers) {
    Future<int> future = multiplyAsync(number);
    futures.add(future);
  }
  List<int> modifiedList = await Future.wait(futures);
  print('$modifiedList');
}
Future<int> multiplyAsync(int number) async {
  await Future.delayed(Duration(seconds: 2));
  return number * 2;
}
~~~
- Input 1 2 3 4 5
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>[2,4,6,8,10]
</code></pre>
</details>

## 10.เขียนโปรแกรมDartที่รับStringเป็นInputและย้อนกลับสตริงแบบ asynchronous จากนั้นพิมพ์Stringที่กลับกัน

~~~ dart
import 'dart:async';
void main() {
  String input = stdin.readLineSync()!;  
  reverseAndPrint(input);
}
Future<void> reverseAndPrint(String text) async {
  String reversedText = await reverseAsync(text);
  print('$reversedText');
}
Future<String> reverseAsync(String text) async {
  await Future.delayed(Duration(seconds: 2));
  return text.split('').reversed.join('');
}
~~~

- Input "Silpakorn"
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>"nrokapliS"
</code></pre>
</details>

# Reference
- https://dart.dev/codelabs/async-await
- https://www.ninenik.com/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%83%E0%B8%8A%E0%B9%89%E0%B8%87%E0%B8%B2%E0%B8%99_Asynchronous_Programming_%E0%B9%83%E0%B8%99%E0%B8%A0%E0%B8%B2%E0%B8%A9%E0%B8%B2_Dart_%E0%B9%80%E0%B8%9A%E0%B8%B7%E0%B9%89%E0%B8%AD%E0%B8%87%E0%B8%95%E0%B9%89%E0%B8%99-949.html
- https://dart-tutorial.com/asynchronous-programming/
