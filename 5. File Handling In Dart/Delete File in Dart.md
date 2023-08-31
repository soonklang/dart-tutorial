# Delete File in Dart
## deleteSync method
## Declaration
 **deleteSync()** 
 Following is the declaration for deleteSync() function.
 ```
void deleteSync(
{bool recursive = false}
)
```
deleteSync() is Synchronously deletes this  **FileSystemEntity**.

```dart
// FileSystemEntity
File file = File('test.txt');
```
**FileSystemEntity** is a directory

if **recursive** is false, the directory must be empty. and if **recursive** is true, FileStstemEntity will be deleted including, all directory and sup-directories and files in the directories. 


 **test.txt** ใน directory เดียวกันกับโปรแกรม Dart

 #### `test.txt`
```dart
// dart program to delete file
import 'dart:io';

void main() {
  // open file
  File file = File('test.txt');
  // delete file
  file.deleteSync();
  print('File deleted.');
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File deleted.</code>
</pre>
</details>

**!NOTE** Throws an exception if the FileSystemEntity cannot be deleted.



