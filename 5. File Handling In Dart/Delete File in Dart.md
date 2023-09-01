# Delete File in Dart
# deleteSync method
## Declaration

 Following is the declaration for **deleteSync()** method.
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

if **recursive** is false, the directory must be empty. and if **recursive** is true, FileStstemEntity will be deleted including, all directory and sup-directories and files in the directories. 

## Example deleteSync()
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

 Following is the declaration for **existsSync()** method.
 ```dart
bool existsSync()
```
## Example existsSync()
use **existsSync()** method to check if a file exists or not.
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

import dart:io library to use **deleteSync()** for Synchronously deletes this FileSystemEntity.
and **existsSync()** for Synchronously checks whether the file system entity with this path exists.

**!NOTE** Synchronously 

## Delete file in other language
- # Java
## **delete()** and **deleteIfExists()** method 
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

import Package java.io for use method **delete()** to delete a file and method **deleteIfExists()** to Deletes a file if it exists, By use Parameters is a path



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
import **module os**  to use method **os.remove()**  to delete a file and
**os.path.exists()** is used to check whether the specified path exists or not.


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

## File Handling must import  library or module that related with I/O Streams, required for input and output operations
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






