# Practice5
แบบฝึกหัดในเรื่อง File Handling in Dart 
## 1.Write a dart program to add your name to “hello.txt” file.
 ```dart
  import 'dart:io';

void main() async {
  File file = File('hello.txt');
  var contents = await file.writeAsString('your name');
}
   ```
### • C
```c
#include <stdio.h>
#include <stdlib.h>
  
int main()
{
    // file pointer
    FILE* fptr;
  
    // creating file using fopen() access mode "w"
    fptr = fopen("hello.txt", "w");
  
    // checking if the file is created
    if (fptr == NULL) {
        printf("The file is not opened. The program will "
               "exit now");
        exit(0);
    }
    else {
        printf("The file is created Successfully : your name");
    }
    
    return 0;
}
```
### • Java
```java
import java.io.File;
 
// Displaying file property
class fileProperty {
    public static void main(String[] args)
    {
 
        // accept file name or directory name through
        // command line args
        String fname = args[0];
 
        // pass the filename or directory name to File
        // object
        File f = new File(fname);
 
        // apply File class methods on File object
        System.out.println("File name :" + f.getName());
 
        if (f.exists()) {
            System.out.println("Is writable:"
                               + f.canWrite());
            System.out.println("Is readable:" + f.canRead());
            System.out.println("Is a directory:"
                               + f.isDirectory());
            System.out.println("File Size in bytes "
                               + f.length());
        }
    }
}
```
### • Python
```python
  # Python code to illustrate with() alongwith write()
with open("hello.txt", "w") as f:
	f.write("your name")

```
## 2.Write a dart program to append your friends name to a file that already has your name.

## 3.Write a dart program to get the current working directory.

## 4.Write a dart program to copy the “hello.txt” file to “hello_copy.txt” file.

## 5.Write a dart program to create 100 files using loop.

## 6.Write a dart program to delete the file “hello_copy.txt”. Make sure you have created the file “hello_copy.txt.

## 7.Write a dart program to store name, age, and address of students in a csv file and read it.


## < Reference >
https://dart-tutorial.com/introduction-and-basics/questions-for-practice-1/
https://flutterawesome.com/learn-the-dart-programming-language-in-this-full-tutorial-for-beginners/
https://www.geeksforgeeks.org/basics-file-handling-c/?ref=lbp
https://www.geeksforgeeks.org/file-class-in-java/?ref=lbp
https://www.geeksforgeeks.org/file-handling-python/?ref=lbp
