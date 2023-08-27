# File Handling In Dart

## Read File in Dart
สันนิษฐานว่ามีไฟล์ที่ชื่อ test.txt อยู่ในdirectoryเดียวกันกับโปรแกรมdart

**test.txt**
```dart
Welcome to test.txt file.
This is a test file.
 ```

ตอนนี้เราสามารถอ่านไฟล์นี้ได้โดยใช้คลาส File และเมธอด **readAsStringSync()** ได้เลย

```dart
// dart program to read from file
import 'dart:io';

void main() {
  // creating file object
  File file = File('test.txt');
  // read file
  String contents = file.readAsStringSync();
  // print file
  print(contents);
}
 ```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

## Get File Information
ในตัวอย่างต่อไปนี้ จะเรียนรู้วิธีการรับข้อมูลไฟล์ เช่น ตำแหน่งไฟล์ ขนาดไฟล์ และเวลาที่แก้ไขล่าสุด

```dart
import 'dart:io';

void main() {
  // open file
  File file = File('test.txt');
  // get file location
  print('File path: ${file.path}');
  // get absolute path
  print('File absolute path: ${file.absolute.path}');
  // get file size
  print('File size: ${file.lengthSync()} bytes');
  // get last modified time
  print('Last modified: ${file.lastModifiedSync()}');
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File path: test.txt
File absolute path: /home/iambrp/Desktop/Dart Practice/test.txt
File size: 25 bytes
Last modified: 2023-01-28 11:00:32.000</code>
</pre>
</details>

**! NOTE**
ถ้าเราพยายามรับข้อมูลของไฟล์ที่ไม่มีอยู่ ไฟล์นั้นจะทำให้เกิดข้อยกเว้น

## CSV File
ไฟล์CSV (Comma Separated Values) คือไฟล์ข้อความที่มีข้อมูลอยู่ในรูปแบบตาราง โดยคอลัมน์จะถูกแบ่งด้วยเครื่องหมายcomma และแถวจะถูกแบ่งด้วยการขึ้นบรรทัดใหม่ ไฟล์ CSV ใช้สำหรับ:

 - การแลกเปลี่ยนข้อมูลระหว่างแอพพลิเคชั่นต่างๆ
 - การสำรองและกู้คืนข้อมูล
 - การนำเข้าและส่งออกข้อมูลจากฐานข้อมูล
 - ระบบอัตโนมัติของงานการประมวลผลข้อมูล

## Read CSV File In Dart
สันนิษฐานว่ามีไฟล์ที่ชื่อ test.csv อยู่ในdirectoryเดียวกันกับโปรแกรมdart

**test.csv**
```dart
Name,Email,Phone
John, john@gmail.com, 1234567890
Smith, smith@gmail.com, 0987654321
```

ตอนนี้เราสามารถอ่านไฟล์นี้ได้โดยใช้คลาส File และเมธอด **readAsStringSync()** เราจะใช้เมธอด **split()** เพื่อแยกสตริงออกเป็นlistของสตริง

```dart
// dart program to read from csv file
import 'dart:io';

void main() {
  // open file
  File file = File('test.csv');
  // read file
  String contents = file.readAsStringSync();
  // split file using new line
  List<String> lines = contents.split('\n');
  // print file
  print('---------------------');
  for (var line in lines) {
    print(line);
  }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>---------------------
Name,Email,Phone
John, john@gmail.com, 1234567890
Smith, smith@gmail.com, 0987654321</code>
</pre>
</details>

## Read Only Part Of File
เราสามารถอ่านแค่บางส่วนของไฟล์ได้โดยการใช้เมธอด **substring()** 
ตัวอย่างต่อไปนี้จะอ่านเฉพาะตัวอักขระ 10 ตัวแรกของไฟล์ โดยที่ไฟล์ชื่อว่า **test.txt** อยู่ในdirectoryเดียวกันกับโปรแกรมdart

```dart
Welcome to test.txt file
This is a test file.
```

```dart
// dart program to read from file
import 'dart:io';

void main() {
  // open file
  File file = new File('test.txt');
  // read only first 10 characters
  String contents = file.readAsStringSync().substring(0, 10);
  // print file
  print(contents);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to</code>
</pre>
</details>

## Read File From Specific Directory
หากต้องการอ่านไฟล์จากspecific directory จะต้องระบุpathแบบเต็มของไฟล์นั้น

```dart
// dart program to read from file
import 'dart:io';

void main() {
  // open file
  File file = File('C:\\Users\\test.txt');
  // read file
  String contents = file.readAsStringSync();
  // print file
  print(contents);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

## การอ่านไฟล์ในภาษาอื่นๆ
- Python

  ในการเปิดอ่านไฟล์ของPython จะใช้ฟังก์ชันbuilt-in **open()**
  ฟังก์ชัน **open()** ต้องรับพารามิเตอร์ 2 ตัว (filenameและmode)
  โดย **mode "r"** คือ อักขระ "r" ตัวเดียว ซึ่งแสดงถึงการอ่านไฟล์
  ฟังก์ชัน **open()** จะreturnวัตถุไฟล์ ซึ่งมีเมธอด **read()** สำหรับการอ่านเนื้อหาในไฟล์

  ```python
  f = open("test.txt", "r")
  print(f.read())
  ```
  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Welcome to test.txt file.
  This is a test file.</code>
  </pre>
  </details>

  หากไฟล์อยู่ในตำแหน่งอื่น เราต้องระบุไฟล์path

  #### `ตัวอย่าง`
  >เปิดไฟล์ในตำแหน่งอื่น:
  ```python
  f = open("D:\\myfiles\test.txt", "r")
  print(f.read())
  ```

  ### Read Only Parts of the File
  ตามค่าเริ่มต้นแล้วเมธอด **read()** จะreturnข้อความทั้งหมด แต่เราสามารถระบุจำนวนอักขระที่จะส่งคืนได้
  
  #### `ตัวอย่าง`
  >Returnอักขระ 7 ตัวแรกของไฟล์:
  ```python
  f = open("test.txt", "r")
  print(f.read(7))
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Welcome</code>
  </pre>
  </details>

  ### Read CSV File In Python
  เราจะimport pandas ซึ่งเป็นไลบรารี Python ที่ใช้ในการจัดการและวิเคราะห์ข้อมูล จะมีเมธอด **.read_csv()** ที่เราต้องการเพื่ออ่านไฟล์csv

  ```python
  import pandas as pd
  data = pd.read_csv("test.csv")
  data
  ```

- C

  การเปิดอ่านไฟล์ของภาษาC จะใช้ฟังก์ชัน **fopen()** ซึ่งรับพารามิเตอร์ 2 ตัว ก็คือ **filename** และ **mode "r"**

  #### `ตัวอย่างที่ 1`
  ```c
  FILE *fptr;

  // Open a file in read mode
  fptr = fopen("filename.txt", "r");
  ```

  ฟังก์ชัน **fread()** 
  #### `ตัวอย่างที่ 2`
  > mode "rb" ใช้ในเปิดการอ่านไฟล์ในโหมดไบนารี
  ```c
  FILE *fptr;

  // Open for reading in binary mode
  fptr = fopen("filename.txt", "rb");
  ```

  หากไฟล์อยู่ในตำแหน่งอื่น เราต้องระบุไฟล์pathแบบเต็มไปยังไฟล์รวมถึงdirectoryด้วย

  ```c
  #include <stdio.h>

  int main() {
    FILE *file;
    char filepath[] = "/path/to/your/directory/yourfile.txt";
    
    file = fopen(filepath, "r");
    
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }
    
    char buffer[1024];
    while (fgets(buffer, sizeof(buffer), file) != NULL) {
        printf("%s", buffer);
    }
    
    fclose(file);
    return 0;
    }
  ```

  แทนที่ "/path/to/your/directory/yourfile.txt" ด้วยpathไปยังไฟล์ที่ต้องการอ่าน ฟังก์ชัน **fopen** จะเปิดไฟล์สำหรับการอ่าน (mode "r") และฟังก์ชัน fgets ใช้เพื่ออ่านไฟล์ทีละบรรทัดลงในบัฟเฟอร์

- Java

  การเปิดอ่านไฟล์ของภาษาC จะใช้คลาส **Scanner** เพื่ออ่านเนื้อหาของไฟล์

  #### `ตัวอย่าง`
  ```java

  ```
