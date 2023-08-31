# Delete File in Dart
# deleteSync method
## Declaration

 Following is the declaration for deleteSync() function.
 ```dart
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

## Ex
Assume that file named **test.txt** in same directory with dart program

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

# existsSync abstract method
## Declaration

 Following is the declaration for existsSync() function.
 ```dart
bool existsSync()
```
existsSync() is checks whether the file system entity with this path exists.

## Ex
use existsSync() method to check if a file ecists or not.
```dart
// dart program to delete file if exists
import 'dart:io';

void main() {
  // open file
  File file = File('test.txt');
  // check if file exists
  if (file.existsSync()) {
    // delete file
    file.deleteSync();
    print('File deleted.');
  } else {
    print('File does not exist.');
  }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File does not exist.</code>
</pre>
</details>

