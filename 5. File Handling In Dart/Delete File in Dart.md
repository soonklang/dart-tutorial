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

## Delete file in other language
- # Java
## delete() and deleteIfExists() method 
## Declaration

The method signature is:
 ```java
public static void delete(Path path)
                   throws IOException
```
```java
public static boolean deleteIfExists(Path path)
                              throws IOException
``` 
## Ex delete()
```java

// Java program to delete a file
import java.io.*;

public class delete {
    public static void main(String[] args) {
        File file = new File("demo.txt");
        file.delete();
        System.out.println("File deleted successfully");
        
    }
}
```
<details>
 
<summary><strong>Output</strong></summary>
<pre>
<code>File deleted successfully.</code>
</pre>
</details>

## Ex deleteOnExit()  
```java
import java.io.IOException;
import java.nio.file.*;

public class deleteIfExists {
    public static void main(String[] args) {
        try {
            Files.deleteIfExists(Paths.get("demo.txt"));
        } catch (NoSuchFileException e) {
            System.out.println("No such file/directory exists");
        } catch (DirectoryNotEmptyException e) {
            System.out.println("Directory is not empty.");
        } catch (IOException e) {
            System.out.println("Invalid permissions.");
        } 
        System.out.println("Deletion successful.");
    }
}
```
<details>
 
<summary><strong>Output</strong></summary>
<pre>
<code>Deletion successful.</code>
</pre>
</details>




