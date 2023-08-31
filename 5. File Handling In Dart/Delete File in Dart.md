# Delete File in Dart
## deleteSync method
 **deleteSync()** 
 ```
void deleteSync(
{bool recursive = false}
)
```

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

**!NOTE** If you try to delete a file that does not exist, then it will throw an exception.


deleteSync() is Synchronously deletes this  #### `FileSystemEntity`.

```dart
// FileSystemEntity
File file = File('test.txt');
```

