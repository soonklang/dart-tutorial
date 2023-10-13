# Delete File in Dart
learn how to delete file in dart programming language
# deleteSync method
## Declaration

 The following code is the declaration for **deleteSync()** method.
 ```dart
void deleteSync(
{bool recursive = false}
)
```

**FileSystemEntity** is a directory

```dart
// FileSystemEntity
File file = File('test.txt');
```

if **recursive** is false, the directory must be empty. and if **recursive** is true, FileStstemEntity will be deleted including, all directory and sub-directories and files in the directories. 

## Example deleteSync()
Assuming that file named **test.txt** is in the same directory with dart program

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

The following code is the declaration for **existsSync()** method.
 ```dart
bool existsSync()
```
## Example existsSync()
use **existsSync()** method to check whether if a file exists or not.
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

## Summary

import dart:io library to use **deleteSync()** for Synchronously deletes this FileSystemEntity
and **existsSync()** for Synchronously checks whether the file system entity with this path exists.

**!NOTE** Synchronous means the code runs in a particular sequence of instructions given in the program.

## Delete file in other language
- # Java
## **delete()** and **deleteIfExists()** method 
## Declaration

The method's signature is:
 ```java
public static void delete(Path path)
                   throws IOException
```
```java
public static boolean deleteIfExists(Path path)
                              throws IOException
``` 
## Example **delete()**
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

## Example deleteIfExists()  
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

## Summary

Import java.io package to use method **delete()** to delete a file and method **deleteIfExists()** to deletes a file if it exists (remind that that parameters must be a path).



- # Python
## **os.remove()** and **os.path.exists()** method 
## Declaration

Syntax:
 ```Python
os.remove(path, *, dir_fd=None)
```
```Python
os.path.exists(path)
``` 
## Example os.remove()
```Python
import os
os.remove("demofile.txt")
```
## Example os.path.exists()  
```Python
import os
if os.path.exists("demofile.txt"):
  os.remove("demofile.txt")
else:
  print("The file does not exist")
```
## Summary
import **module os**  to use  **os.remove()** method to delete a file and
**os.path.exists()** method is use to check whether the specified path is exists or not (remind that that parameters must be a path).


- # C
## remove() function
## Declaration
Syntax:
 ```C
int remove(const char *filename);
```

## Example remove()
```C
#include <stdio.h>

int main() {
  char* filename = "myfile.txt";
  int status = remove(filename);
  if (status == 0) {
    printf("File '%s' deleted successfully.\n", filename);
  } else {
    printf("Error deleting file '%s'.\n", filename);
  }
  return 0;
}
```
## Summary
Use the C **remove()** function from the standard library to delete a file.

# Comparing Dart with other languages (Python, C and Java) 

## The File Handling must import library or module that is related with I/O Streams (Input and output operations is required).
- Dart
 ```Dart
import 'dart:io'
```
- Java
```Java
import java.io.*;
```  
- Python
```Python
import os
``` 
- C Standard library
## After import library or module, use method or funtion for File Handling target (remind that that parameters must be a path).
- Dart
 ```Dart
void deleteSync(
{bool recursive = false}
)
```
- Java
```Java
public static void delete(Path path)
                  throws IOException
```
```Java
public static boolean deleteIfExists(Path path)
                              throws IOException
```  
- Python
```Python
os.remove(path, *, dir_fd=None)
```
```Python
os.path.exists(path)
``` 
- C 
```C
int remove(const char *filename);
```
## Raference
- Dart<br>
  https://api.flutter.dev/flutter/dart-io/FileSystemEntity/deleteSync.html<br>
  https://api.flutter.dev/flutter/dart-io/FileSystemEntity/existsSync.html<br>
  https://api.dart.dev/stable/3.1.0/dart-io/dart-io-library.html<br>
- Java<br>
  https://docs.oracle.com/en/java/javase/18/docs/api/java.base/java/nio/file/Files.html#deleteIfExists(java.nio.file.Path)<br>
  https://docs.oracle.com/javase/tutorial/essential/io/delete.html<br>
  https://www.geeksforgeeks.org/delete-file-using-java/<br>
- Python<br>
  https://docs.python.org/3/library/os.html<br>
  https://docs.python.org/3/library/os.path.html?highlight=os%20path%20exists#os.path.exists<br>
  https://www.w3schools.com/python/python_file_remove.asp<br>
- C<br>
 https://www.ibm.com/docs/en/i/7.2?topic=functions-remove-delete-file<br>
 https://iq.opengenus.org/different-ways-to-delete-file-in-c/<br>
 https://www.learnc.net/c-tutorial/c-delete-file/<br>
 https://www.tutorialkart.com/c-programming/c-delete-file/#gsc.tab=0<br>

## Slide & Video
[Read File In Dart.pdf](https://github.com/PasinYst/silde/blob/main/Delete%20File%20in%20Dart.pdf)<br>
https://youtu.be/M_HkHvEa3HE<br>



