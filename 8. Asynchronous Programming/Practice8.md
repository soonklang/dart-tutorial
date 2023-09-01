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
- Dart
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
- C
~~~ c
#include <stdio.h>
#include <time.h>

void _delayedPrint() {
    time_t start_time, current_time;
    time(&start_time);
    printf("Started at: %s", ctime(&start_time));
    
    while (1) {
        time(&current_time);
        if (current_time - start_time >= 2) {
            printf("Current time after 2 seconds: %s", ctime(&current_time));
            break;
        }
    }
}

int main() {
    _delayedPrint();
    return 0;
}
~~~
- Java
~~~ java
import java.util.Date;

public class Main {
    public static void main(String[] args) {
        System.out.println("Started at: " + new Date());
        delayedPrint();
    }

    public static void delayedPrint() {
        try {
            Thread.sleep(2000); // รอเป็นเวลา 2 วินาที
            System.out.println("Current time after 2 seconds: " + new Date());
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
~~~
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Started at: 2023-08-31 17:30:25.123456
Current time after 2 seconds: 2023-08-31 17:30:27.123456
</code></pre>
</details>

## 4.เขียนโปรแกรมอ่านไฟล์'csv'และแสดง
- Dart
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
- Java
~~~ java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
public class Main {
    public static void main(String[] args) {
        String csvFilePath = "path_to_your_csv_file.csv";
        try (BufferedReader br = new BufferedReader(new FileReader(csvFilePath))) {
            String line;
            while ((line = br.readLine()) != null) {
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
~~~
- Python
~~~ python
import csv
csvFilePath = 'path_to_your_csv_file.csv'
with open(csvFilePath, newline='') as csvfile:
    csvreader = csv.reader(csvfile)
    for row in csvreader:
        print(row)
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
- Dart
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
- Python
~~~ python
import asyncio
async def fetch_data(id):
    await asyncio.sleep(2)
    return f'Data for ID {id}'
async def main():
    futures = []
    for i in range(1, 6):
        future = fetch_data(str(i))
        futures.append(future)
    results = await asyncio.gather(*futures)
    print('All operations completed:')
    for i, result in enumerate(results):
        print(f'Result for operation {i + 1}: {result}')
if __name__ == '__main__':
    asyncio.run(main())
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
- Dart
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
- Python
~~~ python
import asyncio
async def calculate_sum(a, b):
    await asyncio.sleep(2)
    return a + b
async def main():
    n1 = 1
    n2 = 2
    result = await calculate_sum(n1, n2)
    print(f'{n1} + {n2} : {result}')
if __name__ == '__main__':
    asyncio.run(main())
~~~
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>1 + 2 : 3
</code></pre>
</details>

## 7.เขียนโปรแกรมDartโดยรับจำนวนเต็มเข้ามา2ตัวรอ3วินาทีจากนั้นพิมพ์ผลรวมของตัวเลขทั้งสอง
- Dart
~~~ dart
import 'dart:io';
Future<void> calculateSumAndPrint(int a, int b) async {
  await Future.delayed(Duration(seconds: 3));// รอ 3 วินาที
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
- Java
~~~ java
import java.util.Scanner;
public class Main {
    public static void calculateSumAndPrint(int a, int b) {
        try {
            Thread.sleep(3000); // รอ 3 วินาที
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        int sum = a + b;
        System.out.println(a + " + " + b + " : " + sum);
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        try {
            System.out.print("Enter the first number: ");
            int num1 = scanner.nextInt();
            System.out.print("Enter the second number: ");
            int num2 = scanner.nextInt();

            calculateSumAndPrint(num1, num2);
        } catch (Exception e) {
            System.out.println("An error occurred: " + e.getMessage());
        } finally {
            scanner.close();
        }
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
- Dart
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
- Java
~~~ java
import java.util.Arrays;
import java.util.Scanner;
import java.util.concurrent.CompletableFuture;

public class Main {
    public static CompletableFuture<String> readLineAsync(Scanner scanner) {
        CompletableFuture<String> future = new CompletableFuture<>();
        new Thread(() -> {
            String input = scanner.nextLine();
            future.complete(input);
        }).start();
        return future;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        CompletableFuture<String> inputFuture = readLineAsync(scanner);
        inputFuture.thenAccept(input -> {
            String[] items = input.split(" ");
            Arrays.sort(items);
            for (String item : items) {
                System.out.println(item);
            }
        });
        try {
            // รอให้การอ่านข้อมูลเสร็จสิ้น
            inputFuture.get();
        } catch (Exception e) {
            e.printStackTrace();
        }
        scanner.close();
    }
}
~~~
- Python
~~~ python
import asyncio
async def read_line_async():
    loop = asyncio.get_event_loop()
    return await loop.run_in_executor(None, input, "Enter a list of words separated by space: ")
async def main():
    try:
        input_str = await read_line_async()
        items = input_str.split()
        items.sort()
        for item in items:
            print(item)
    except Exception as e:
        print(f'Error: {e}')
if __name__ == '__main__':
    asyncio.run(main())
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

## 9.เขียนโปรแกรมDartที่รับจำนวนเต็มและคูณจำนวนเต็มแต่ละตัวด้วย 2 แบบ asynchronous จากนั้นพิมพ์รายการที่แก้ไข
- Dart
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
- Java
~~~ java
import java.util.Scanner;
import java.util.concurrent.CompletableFuture;
public class Main {
    public static CompletableFuture<String> readLineAsync(Scanner scanner) {
        CompletableFuture<String> future = new CompletableFuture<>();
        new Thread(() -> {
            String input = scanner.nextLine();
            future.complete(input);
        }).start();
        return future;
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a list of integers separated by spaces: ");
        CompletableFuture<String> inputFuture = readLineAsync(scanner);
        inputFuture.thenAcceptAsync(input -> {
            String[] inputArray = input.split(" ");
            int[] numbers = new int[inputArray.length];
            for (int i = 0; i < inputArray.length; i++) {
                numbers[i] = Integer.parseInt(inputArray[i]);
            }
            multiplyAndPrint(numbers);
        });
        try {
            // รอให้การอ่านข้อมูลเสร็จสิ้น
            inputFuture.get();
        } catch (Exception e) {
            e.printStackTrace();
        }
        scanner.close();
    }
    public static void multiplyAndPrint(int[] numbers) {
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] *= 2;
        }
        System.out.print("[");
        for (int i = 0; i < numbers.length; i++) {
            System.out.print(numbers[i]);
            if (i < numbers.length - 1) {
                System.out.print(", ");
            }
        }
        System.out.println("]");
    }
}
~~~
- Python
~~~ python
import asyncio
async def read_line_async():
    loop = asyncio.get_event_loop()
    return await loop.run_in_executor(None, input)
async def main():
    try:
        input_str = await read_line_async()
        input_list = list(map(int, input_str.split()))
        await multiply_and_print(input_list)
    except Exception as e:
        print(f'Error: {e}')
async def multiply_and_print(numbers):
    await asyncio.gather(*[multiply_async(number) for number in numbers])
async def multiply_async(number):
    await asyncio.sleep(2)  # รอ 2 วินาที
    result = number * 2
    print(result, end=', ')
if __name__ == '__main__':
    asyncio.run(main())
~~~
- Input 1 2 3 4 5
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>[2,4,6,8,10]
</code></pre>
</details>

## 10.เขียนโปรแกรมDartที่รับStringเป็นInputและย้อนกลับสตริงแบบ asynchronous จากนั้นพิมพ์Stringที่กลับกัน
- Dart
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
- Python
~~~ python
import asyncio
async def reverse_text_async(text):
    await asyncio.sleep(2)  # รอ 2 วินาที
    reversed_text = text[::-1]
    return reversed_text
async def main():
    try:
        text = input()
        reversed_text = await reverse_text_async(text)
        print("Reversed text:", reversed_text)
    except Exception as e:
        print(f'Error: {e}')
if __name__ == '__main__':
    asyncio.run(main())
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
