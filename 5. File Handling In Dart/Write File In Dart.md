# File Handling In Dart
## Write File in Dart

สร้างไฟล์ชื่อ **test.txt** ใน directory เดียวกันกับโปรแกรม Dart

 #### `test.txt`
```dart
// dart program to write to file
import 'dart:io';

void main() {
  // open file
  File file = File('test.txt');
  // write to file
  file.writeAsStringSync('Welcome to test.txt file.');
  print('File written.');
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File written.</code>
</pre>
</details>

**!NOTE** ถ้าหากเรามีข้อมูลบางส่วนในไฟล์ **test.txt** อยู่ก่อนแล้ว ข้อมูลนั้นจะถูกลบออกและถูกแทนที่ด้วยข้อมูลใหม่แทน

## Add New Content To Previous Content

เราสามารถใช้ **FileMode.append** ในการเพิ่มข้อมูลลงไปในไฟล์ที่มีข้อมูลอยู่ก่อนแล้วได้

สมมติว่าไฟล์ **test.txt** มีข้อมูลอยู่ก่อนแล้ว

```
Welcome to test.txt file.
```

ตัวอย่างการเพิ่มข้อมูลในไฟล์โดยการใช้ **FileMode.append**

```dart
// dart program to write to existing file
import 'dart:io';

void main() {
  // open file
  File file =  File('test.txt');
  // write to file
  file.writeAsStringSync('\nThis is a new content.', mode: FileMode.append);
  print('Congratulations!! New content is added on top of previous content.');
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Congratulations!! New content is added on top of previous content.</code>
</pre>
</details>

## Write CSV File In Dart

ตัวอย่าง การขอให้ผู้ใช้ป้อน **name** และ **phone** ของนักเรียน 3 คนและเขียนลงในไฟล์ csv ชื่อ **students.csv**

```dart
// dart program to write to csv file
import 'dart:io';

void main() {
  // open file
  File file = File("students.csv");
  // write to file
  file.writeAsStringSync('Name,Phone\n');
  for (int i = 0; i < 3; i++) {
    // user input name
    stdout.write("Enter name of student ${i + 1}: ");
    String? name = stdin.readLineSync();
    stdout.write("Enter phone of student ${i + 1}: ");
    // user input phone
    String? phone = stdin.readLineSync();
    file.writeAsStringSync('$name,$phone\n', mode: FileMode.append);
  }
  print("Congratulations!! CSV file written successfully.");
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Enter name of student 1: John 
Enter phone of student 1: 1234567890
Enter name of student 2: Mark
Enter phone of student 2: 0123456789
Enter name of student 3: Elon
Enter phone of student 3: 0122112322
Congratulations!! CSV file written successfully.</code>
</pre>
</details>

ไฟล์ **students.csv** จะมีลักษณะดังนี้:
```
Name,Phone
John,1234567890
Mark,0123456789
Elon,0122112322
```

**!NOTE** เราสามารถใช้เมธอด **writeAsStringSync()** ในการสร้างไฟล์ประเภทใดก็ได้ ตัวอย่างเช่น .html, .json, .xml เป็นต้น

## การเขียนไฟล์ในภาษาอื่นๆ
- **Python**
  
  ## Write to an Existing File

  ในการเขียนข้อมูลลงในไฟล์ที่มีอยู่ก่อนแล้วเราต้องเพิ่มพารามิเตอร์ลงในฟังก์ชัน open():

  "a" - Append - จะเพิ่มข้อมูลต่อกับส่วนท้ายของไฟล์
  
  "w" - Write - จะเขียนข้อมูลทับเนื้อหาที่มีอยู่ก่อนแล้วในไฟล์

   #### `ตัวอย่าง`
  
  ไฟล์ **demofile.txt** มีข้อมูลอยู่ก่อนแล้วดังนี้:
  ```
  Hello! Welcome to demofile.txt
  This file is for testing purposes.
  Good Luck!
  ```

  #### `ตัวอย่างที่ 1`

  เปิดไฟล์ **demofile.txt** และเพิ่มข้อมูลลงในไฟล์:
  ```python
  f = open("demofile.txt", "a")
  f.write("Now the file has more content!")
  f.close()

  #open and read the file after the appending:
  f = open("demofile.txt", "r")
  print(f.read())
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Hello! Welcome to demofile.txt
  This file is for testing purposes.
  Good Luck!Now the file has more content!</code>
  </pre>
  </details>

  #### `ตัวอย่างที่ 2`

  เปิดไฟล์ **demofile.txt** และเขียนข้อมูลทับลงไปในไฟล์:
  ```python
  f = open("demofile.txt", "w")
  f.write("Woops! I have deleted the content!")
  f.close()

  #open and read the file after the overwriting:
  f = open("demofile.txt", "r")
  print(f.read())
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Woops! I have deleted the content!</code>
  </pre>
  </details>

  **!NOTE** เมื่อใช้ "w" จะเขียนทับไฟล์ทั้งหมด


  
