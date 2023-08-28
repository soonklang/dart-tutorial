# File Handling In Dart
## Write File in Dart

สร้างไฟล์ชื่อ **test.txt** ใน directory เดียวกันกับโปรแกรม Dart

**test.txt**
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

## Add New Content To Previous Content

เราสามารถใช้ **FileMode.append** ในการเพิ่มเนื้อหาหรือข้อมูลลงไปในไฟล์ที่มีเนื้อหาอยู่ก่อนแล้วได้

สมมติว่าไฟล์ **test.txt** มีเนื้อหาหรือข้อมูลอยู่ก่อนแล้ว

```
Welcome to test.txt file.
```

ตัวอย่างการเพิ่มเนื้อหาหรือข้อมูลลงไปในไฟล์โดยใช้ **FileMode.append**

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


