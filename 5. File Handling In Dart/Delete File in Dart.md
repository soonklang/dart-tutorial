# Delete File in Dart
# deleteSync method
## Declaration

 Following is the declaration for deleteSync() method.
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

 Following is the declaration for existsSync() method.
 ```dart
bool existsSync()
```
existsSync() is checks whether the file system entity with this path exists.

## Ex
use existsSync() method to check if a file exists or not.
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

# Delete file in other language
- ## Java
# delete() method
## Declaration

 Following is the declaration for delete() function.
 ```java
public boolean delete() 
```
## Ex
use delete() method to delete file.
```java
import java.io.File;

public class FileDeleteExample {
    public static void main(String[] args) {
        try {
            File f = new File("E:\\demo.txt"); // file to be delete
            if (f.delete()) // returns Boolean value
            {
                System.out.println(f.getName() + " deleted"); // getting and printing the file name
            } else {
                System.out.println("failed");
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
<details>
 
<summary><strong>Output</strong></summary>
<pre>
<code>File does not exist.</code>
</pre>
</details>



