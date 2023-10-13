# Write File in Dart

วิธีที่ง่ายที่สุดในการเขียนไฟล์ในภาษา Dart คือการใช้เมธอด **writeAsStringSync()** ของคลาส **File**

ตัวอย่าง สร้างไฟล์ชื่อ **test.txt** ใน directory เดียวกันกับโปรแกรม Dart

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

เมธอด **writeAsStringSync()** มักจะใช้ในการเขียนข้อมูลจํานวนเล็กน้อยเพื่อความรวดเร็ว 
แต่สําหรับข้อมูลจํานวนมากเราควรใช้เมธอด **writeAsBytesSync()** แทน เช่น สามารถใช้สร้าง List<int> ได้<br><br>
ตัวอย่าง หากต้องการเขียนไฟล์ที่มีข้อมูลไบต์ "0x01, 0x02, 0x03" สามารถทำได้ดังนี้:

#### `ตัวอย่าง`
```dart
import 'dart:io'; 

void main() {
  final file = File('sample.bin');
  file.writeAsBytesSync([0x01, 0x02, 0x03]);
}
```

## Add New Content To Previous Content

สมมติว่าไฟล์ **test.txt** มีข้อมูลอยู่ก่อนแล้ว

```
Welcome to test.txt file.
```

หากเราต้องการเพิ่มข้อมูลลงในไฟล์ที่มีอยู่ก่อนแล้ว สามารถทําได้โดยใช้เมธอด **writeAsStringSync()** หรือ **writeAsBytesSync()** ของคลาส **File** <br><br>
ตัวอย่าง หากต้องการเขียนข้อมูล "Goodbye, world!" ในไฟล์ **test.txt** สามารถทำได้ดังนี้:

#### `ตัวอย่าง`
```dart
import 'dart:io'; 

void main() {
  final file = File('test.txt');
  file.writeAsStringSync('Goodbye, world!');
}
```

**!NOTE** วิธีนี้เป็นการเขียนข้อมูลใหม่ทับข้อมูลในไฟล์ 'test.txt' เดิม

แต่ถ้าต้องการเพิ่มข้อมูลลงในไฟล์ที่มีอยู่โดยไม่ต้องเขียนทับเนื้อหาที่มีอยู่เราสามารถใช้ **FileMode.append** ในการเพิ่มข้อมูลลงไปในไฟล์ที่มีข้อมูลอยู่ก่อนแล้วได้
วิธีการนี้ใช้จะเป็นการเพิ่มข้อมูลไปยังส่วนท้ายของไฟล์แทนการเขียนทับ<br><br>

ตัวอย่าง การเพิ่มข้อมูลในไฟล์โดยการใช้ **FileMode.append**

#### `ตัวอย่าง`
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

#### `ตัวอย่าง`
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

> ไฟล์ **students.csv** จะมีลักษณะดังนี้:
```
Name,Phone
John,1234567890
Mark,0123456789
Elon,0122112322
```

**!NOTE** เราสามารถใช้เมธอด **writeAsStringSync()** ในการสร้างไฟล์ประเภทใดก็ได้ ตัวอย่างเช่น .html, .json, .xml เป็นต้น

## Writing to a Stream

ในบางกรณี เราอาจต้องเขียนข้อมูลลงในไฟล์ด้วยวิธีที่ยืดหยุ่นมากขึ้น เช่น อาจจะต้องเขียนข้อมูลเป็นส่วนๆ, เขียนข้อมูลหลายๆ ครั้ง หรืออาจต้องเขียนข้อมูลจากหลาย ๆ แหล่ง 
คลาส **File** มีเมธอด **openWrite()** ที่สามารถคืนค่า StreamSink object ได้ โดย object นี้สามารถใช้ในการเขียนข้อมูลไปยังไฟล์ในรูปแบบ streaming

ตัวอย่าง เมื่อต้องการเขียนข้อความ "Hello, world!" และข้อความ "Goodbye, world!" ไปยังไฟล์ **sample.txt** สามารถทำได้ดังนี้:

#### `ตัวอย่าง`
```dart
import 'dart:io'; 

void main() {
  final file = File('sample.txt');
  final sink = file.openWrite();
  sink.write('Hello, world!');
  sink.write('Goodbye, world!');
  sink.close();
}
```

## การเขียนไฟล์ในภาษาอื่นๆ
- **Python**
  
  ## Write to an Existing File

  ในการเขียนข้อมูลลงในไฟล์ที่มีอยู่ก่อนแล้วเราต้องเพิ่มพารามิเตอร์ลงในฟังก์ชัน open() ดังนี้:<br>
  > "a" - Append - จะเพิ่มข้อมูลต่อกับส่วนท้ายของไฟล์<br>
  > "w" - Write - จะเขียนข้อมูลทับเนื้อหาที่มีอยู่ก่อนแล้วในไฟล์

  #### `ตัวอย่าง`
  > ไฟล์ **demofile.txt** มีข้อมูลอยู่ก่อนแล้วดังนี้:
  ```
  Hello! Welcome to demofile.txt
  This file is for testing purposes.
  Good Luck!
  ```

  #### `ตัวอย่างที่ 1`
  > เปิดไฟล์ **demofile.txt** และเพิ่มข้อมูลลงในไฟล์:
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
  > เปิดไฟล์ **demofile.txt** และเขียนข้อมูลทับลงไปในไฟล์:
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

  หากต้องการสร้างไฟล์ใหม่ใน Python ต้องใช้เมธอด open() ร่วมกับหนึ่งในพารามิเตอร์ต่อไปนี้:<br>
  > "x" - Create - จะสร้างไฟล์และ return ค่า error กลับมาหากมีไฟล์นั้นอยู่ก่อนแล้ว<br>
  > "a" - Append - จะสร้างไฟล์หากไฟล์ที่สร้างไม่ใช่ไฟล์ที่มีอยู่ก่อนแล้ว<br>
  > "w" - Write - จะสร้างไฟล์หากไฟล์ที่สร้างไม่ใช่ไฟล์ที่มีอยู่ก่อนแล้ว

  #### `ตัวอย่างที่ 1`
  >สร้างไฟล์ชื่อ **myfile.txt**:
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
  > การสร้างไฟล์ใหม่หากไฟล์นั้นไม่ได้มีอยู่ก่อนแล้ว:
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

  หากต้องการเปิดไฟล์ เราต้องใช้ฟังก์ชัน fopen() ร่วมกับพารามิเตอร์สองตัว:<br> 

  |พารามิเตอร์|  คำอธิบาย  |
  |--|--|
  | **filename** | ชื่อของไฟล์ที่เราต้องการเปิดหรือสร้าง ตัวอย่างเช่น filename.txt |
  | **mode** | อักขระที่แสดงถึงสิ่งที่เราต้องการทํากับไฟล์:<br> "w" - การเขียนไฟล์<br> "a" - การเพิ่มข้อมูลใหม่ในไฟล์<br> "r" - การอ่านไฟล์ |


  ## Create a File

  ในการสร้างไฟล์เราจะใช้ "w" ร่วมกับฟังก์ชัน fopen()<br>
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

  ใช้ "w" ในการเขียนข้อมูลลงในไฟล์ที่เราสร้างขึ้น โดยโหมด "w" หมายความว่าไฟล์ถูกเปิดเพื่อเขียนข้อมูล<br>
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

  ## Create a File

  ในภาษา Java เราสามารถสร้างไฟล์ได้โดยการใช้เมธอด createNewFile() โดยเมธอดนี้จะ return ค่า boolean<br>
  หากสามารถสร้างไฟล์ได้สำเร็จจะ return ค่า true คืนกลับมา<br>
  แต่ถ้าหากมีไฟล์อยู่แล้วจะ return ค่า false คืนกลับมา<br>
  ซึ่งเมธอดนี้อยู่ใน catch block ดังนั้นจะส่ง IOException กลับมาหากมีข้อผิดพลาดเกิดขึ้น

  #### `ตัวอย่าง`
  ```java
  import java.io.File;  // Import the File class
  import java.io.IOException;  // Import the IOException class to handle errors

  public class CreateFile {
    public static void main(String[] args) {
      try {
        File myObj = new File("filename.txt");
        if (myObj.createNewFile()) {
          System.out.println("File created: " + myObj.getName());
        } else {
          System.out.println("File already exists.");
        }
      } catch (IOException e) {
        System.out.println("An error occurred.");
        e.printStackTrace();
      }
    }
  }
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>File created: filename.txt</code>
  </pre>
  </details>

  ถ้าหากต้องการสร้างไฟล์ใน directory เฉพาะ ให้ระบุ **path** ของไฟล์และใช้เครื่องหมาย **double backslashes** (สําหรับ Windows แต่ถ้าเป็น Mac หรือ Linux สามารถเขียน path เช่น: /Users/name/filename.txt ได้เลย)

  #### `ตัวอย่าง`
  ```java
  import java.io.File; 
  import java.io.IOException;
  
  public class CreateFileDir {  
    public static void main(String[] args) {  
      try {  
        File myObj = new File("C:\\Users\\MyName\\filename.txt");  
        if (myObj.createNewFile()) {  
          System.out.println("File created: " + myObj.getName());  
          System.out.println("Absolute path: " + myObj.getAbsolutePath());  
        } else {  
          System.out.println("File already exists.");  
        }  
      } catch (IOException e) {
        System.out.println("An error occurred.");
        e.printStackTrace();  
      }  
    }  
  }
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>File created: filename.txt
  Absolute path: C:\Users\MyName\filename.txt</code>
  </pre>
  </details>

  ## Write To a File

  เราจะใช้คลาส **FileWriter** ร่วมกับเมธอด **write()** เพื่อเขียนข้อมูลบางส่วนในไฟล์ที่เราสร้างขึ้น โดยเมื่อเขียนข้อมูลที่ต้องการใส่ลงในไฟล์เสร็จแล้วควรปิดท้ายด้วยเมธอด **close()**:

  #### `ตัวอย่าง`
  ```java
  import java.io.FileWriter;
  import java.io.IOException;

  public class WriteToFile {  
    public static void main(String[] args) {  
      try {  
        FileWriter myWriter = new FileWriter("filename.txt");
        myWriter.write("Files in Java might be tricky, but it is fun enough!");
        myWriter.close();
        System.out.println("Successfully wrote to the file.");
      } catch (IOException e) {
        System.out.println("An error occurred.");
        e.printStackTrace();
      } 
    }  
  } 
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Successfully wrote to the file.</code>
  </pre>
  </details>

## เปรียบเทียบการเขียนไฟล์ในภาษา Dart กับภาษาอื่น ๆ

1. ภาษา Dart และภาษา Python มีลักษณะการเขียนโปรแกรมในการเขียนไฟล์ที่ง่ายและกระชับกว่าภาษา C และภาษา Java
2. หลังจากเพิ่มข้อมูลในไฟล์เสร็จแล้วภาษา dart ไม่จำเป็นต้องใช้เมธอดเพื่อปิดไฟล์เหมือนกับภาษาอื่น ๆ ยกเว้นการเขียนไฟล์แบบ Stream
3. ภาษา Dart และภาษา Java ไม่จำเป็นต้องระบุพารามิเตอร์เพื่อบอกว่าต้องการทำอะไรกับไฟล์
ในขณะที่ภาษา Python และภาษา C จะต้องระบุพารามิเตอร์ตัวอักษรหนึ่งตัว เช่น "a" หรือ "w"

## Reference

https://dart-tutorial.com/file-handling-in-dart/write-file-in-dart/<br>
https://dart.helpful.codes/tutorials/How-to-Write-Files/<br>
https://www.w3schools.com/python/python_file_write.asp<br>
https://www.w3schools.com/c/c_files.php<br>
https://www.w3schools.com/c/c_files_write.php<br>
https://www.w3schools.com/java/java_files_create.asp<br>

## Link Video

https://youtu.be/ymnNiJSY7NU

## Slide

version 1: [Write File In Dart.pdf](https://github.com/parichat663/Write_File_in_Dart/blob/main/630710663-Write%20File%20in%20Dart.pdf)<br>
version 2: [Write File In Dart.pdf](https://github.com/parichat663/Write_File_in_Dart/blob/main/Write%20File%20in%20Dart.pdf?raw=true)
