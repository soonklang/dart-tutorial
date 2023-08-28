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

  ในการเขียนข้อมูลลงในไฟล์ที่มีอยู่ก่อนแล้วเราต้องเพิ่มพารามิเตอร์ลงในฟังก์ชัน open() ดังนี้:

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

  ## Create a New File

  หากต้องการสร้างไฟล์ใหม่ใน Python ต้องใช้เมธอด open() ร่วมกับหนึ่งในพารามิเตอร์ต่อไปนี้:

  "x" - Create - จะสร้างไฟล์และ return ค่า error กลับมาหากมีไฟล์นั้นอยู่ก่อนแล้ว

  "a" - Append - จะสร้างไฟล์หากไฟล์ที่สร้างไม่ใช่ไฟล์ที่มีอยู่ก่อนแล้ว

  "w" - Write - จะสร้างไฟล์หากไฟล์ที่สร้างไม่ใช่ไฟล์ที่มีอยู่ก่อนแล้ว

  #### `ตัวอย่างที่ 1`
  
  สร้างไฟล์ชื่อ **myfile.txt**:
  ```python
  f = open("myfile.txt", "x")
  ```

  <details>
  <summary><strong>Result:</strong></summary>
  <pre>
  <code>a new empty file is created!</code>
  </pre>
  </details>

  #### `ตัวอย่างที่ 2`
  
  การสร้างไฟล์ใหม่หากไฟล์นั้นไม่ได้มีอยู่ก่อนแล้ว:
  ```python
  f = open("myfile.txt", "a")
  ```
  หรือ
  ```python
  f = open("myfile.txt", "w")
  ```

  

- **C**

  ในภาษา C เราสามารถสร้างไฟล์, อ่านไฟล์, และเขียนไฟล์ได้โดยประกาศตัวชี้ประเภท FILE และใช้ฟังก์ชัน fopen():
  
  ```c
  FILE *fptr
  fptr = fopen(filename, mode);
  ```

  หากต้องการเปิดไฟล์ เราต้องใช้ฟังก์ชัน fopen() ร่วมกับพารามิเตอร์สองตัว:
   
  **1.** filename	คือชื่อของไฟล์ที่เราต้องการเปิดหรือสร้าง ตัวอย่างเช่น filename.txt
 
  **2.** mode คืออักขระที่แสดงถึงสิ่งที่เราต้องการทํากับไฟล์:
  
     "w" - การเขียนไฟล์
     
     "a" - การเพิ่มข้อมูลใหม่ในไฟล์
     
     "r" - การอ่านไฟล์

  ## Create a File

  ในการสร้างไฟล์เราจะใช้ "w" ร่วมกับฟังก์ชัน fopen()

  โดยโหมด "w" จะใช้เพื่อเขียนไฟล์ แต่ถ้าหากไม่มีไฟล์นั้น โหมดนี้จะสร้างไฟล์ให้เราโดยอัตโนมัติ:

  #### `ตัวอย่าง`
  
  ```c
  FILE *fptr;

  // Create a file
  fptr = fopen("filename.txt", "w");

  // Close the file
  fclose(fptr);
  ```

  **!NOTE** ไฟล์จะถูกสร้างขึ้นใน directory เดียวกันกับไฟล์ภาษา C อื่น ๆ ของเรา

  ## Write To a File

  ใช้ "w" ในการเขียนข้อมูลลงในไฟล์ที่เราสร้างขึ้น โดยโหมด "w" หมายความว่าไฟล์ถูกเปิดเพื่อเขียนข้อมูล
  ในการแทรกข้อมูลนั้น เราสามารถใช้ฟังก์ชัน fprint() และเพิ่มตัวชี้ (ตัวอย่างเช่น fptr) หรือเนื้อหาบางส่วนได้:

  #### `ตัวอย่าง`
  
  ```c
  FILE *fptr;

  // Open a file in writing mode
  fptr = fopen("filename.txt", "w");

  // Write some text to the file
  fprintf(fptr, "Some text");

  // Close the file
  fclose(fptr);
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Some text</code>
  </pre>
  </details>

  **!NOTE** ถ้าเราเขียนข้อมูลในไฟล์ที่มีอยู่แล้ว ข้อมูลเก่าจะถูกลบ และถูกแทนที่ด้วยข้อมูลใหม่ นี่เป็นสิ่งสําคัญที่ต้องจำให้ขึ้นใจเนื่องจากเราอาจจะเผลอลบข้อมูลที่มีอยู่โดยไม่ตั้งใจ

  #### `ตัวอย่าง`
  
  ```c
  fprintf(fptr, "Hello World!");
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Hello World!</code>
  </pre>
  </details>

  **!NOTE** ด้วยเหตุนี้หากเราเปิดไฟล์ **filename.txt** บนคอมพิวเตอร์ของเรา ข้อมูลในไฟล์จะเป็น ```Hello World!``` แทนที่จะเป็น ```Some text```



- **Java**
