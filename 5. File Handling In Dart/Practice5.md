# Practice5
## แบบฝึกหัดในเรื่อง File Handling in Dart 7 ข้อต่อไปนี้<br>
1.Write a dart program to add your name to “hello.txt” file.<br>
2.Write a dart program to append your friends name to a file that already has your name.<br>
3.Write a dart program to get the current working directory.<br>
4.Write a dart program to copy the “hello.txt” file to “hello_copy.txt” file.<br>
5.Write a dart program to create 100 files using loop.<br>
6.Write a dart program to delete the file “hello_copy.txt”. Make sure you have created the file “hello_copy.txt.<br>
7.Write a dart program to store name, age, and address of students in a csv file and read it.<br>
--------------------------------------------------------------------------------------------------------------------<br>
## 1.Write a dart program to add your name to “hello.txt” file.
 ```dart
  import 'dart:io'; 

void main() {
  final file = File('hello.txt');
  file.writeAsStringSync('your name');
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
with open("hello.txt", 'w') as f:
	f.write("your name")

```

## 2.Write a dart program to append your friends name to a file that already has your name.
```dart
 import 'dart:io'; 

void main() {
  final file = File('hello.txt');
  file.writeAsStringSync('your name');
  file.writeAsStringSync('\nyour friends name', mode: FileMode.append);
   ```
### • C
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // File path
    const char *filePath = "names.txt";

    // Your name
    const char *yourName = "Your Name";

    // Your friend's name
    const char *friendName = "Friend's Name";

    // Open the file in append mode
    FILE *file = fopen(filePath, "a");
    
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }

    // Append your friend's name
    fprintf(file, "%s\n", friendName);

    // Close the file
    fclose(file);

    printf("Friend's name added to the file.\n");

    return 0;
}
```
### • Java
```java
import java.io.FileWriter;
import java.io.BufferedWriter;
import java.io.IOException;

public class AppendToFile {
    public static void main(String[] args) {
        // File path
        String filePath = "names.txt";

        // Your name
        String yourName = "Your Name";

        // Your friend's name
        String friendName = "Friend's Name";

        try {
            // Open the file in append mode
            BufferedWriter writer = new BufferedWriter(new FileWriter(filePath, true));

            // Append your friend's name
            writer.write(friendName);
            writer.newLine();

            // Close the writer
            writer.close();

            System.out.println("Friend's name added to the file.");
        } catch (IOException e) {
            System.err.println("Error: " + e.getMessage());
        }
    }
}
```

## 3.Write a dart program to get the current working directory.
-Make sure you have the path package added to your pubspec.yaml file
```dart
  dependencies:
  path: ^1.8.0
   ```
-Import the necessary libraries and create the Dart program
```dart
  import 'dart:io';
import 'package:path/path.dart';

void main() {
  String currentDirectory = Directory.current.path;
  print('Current working directory: $currentDirectory');
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Current working directory: /path/to/your/current/directory.</code>
</pre>
</details>

### • C
```c
#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <limits.h>

int main() {
    char cwd[PATH_MAX];

    if (getcwd(cwd, sizeof(cwd)) != NULL) {
        printf("Current working directory: %s\n", cwd);
    } else {
        perror("getcwd() error");
        return EXIT_FAILURE;
    }

    return EXIT_SUCCESS;
}
```
### • Java
```java
public class GetCurrentWorkingDirectory {
    public static void main(String[] args) {
        String currentDirectory = System.getProperty("user.dir");
        System.out.println("Current working directory: " + currentDirectory);
    }
}
```
### • Python
```python
import os

current_directory = os.getcwd()
print("Current working directory:", current_directory)
```

## 4.Write a dart program to copy the “hello.txt” file to “hello_copy.txt” file.
```dart
import 'dart:io';

void main() {
  copyFile("hello.txt", "hello_copy.txt");
}

void copyFile(String sourcePath, String destinationPath) {
  File sourceFile = File(sourcePath);
  File destinationFile = File(destinationPath);

  if (!sourceFile.existsSync()) {
    print("Source file not found.");
    return;
  }

  try {
    sourceFile.copySync(destinationPath);
    print("File copied successfully.");
  } catch (e) {
    print("An error occurred: $e");
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File copied successfully.</code>
</pre>
</details>

### • C
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *source_file, *destination_file;
    char ch;

    source_file = fopen("hello.txt", "r");
    if (source_file == NULL) {
        printf("Source file not found.\n");
        return 1;
    }

    destination_file = fopen("hello_copy.txt", "w");
    if (destination_file == NULL) {
        printf("Error creating destination file.\n");
        fclose(source_file);
        return 1;
    }

    while ((ch = fgetc(source_file)) != EOF) {
        fputc(ch, destination_file);
    }

    printf("File copied successfully.\n");

    fclose(source_file);
    fclose(destination_file);

    return 0;
}
```
### • Python
```python
def copy_file(source_path, destination_path):
    try:
        with open(source_path, 'r') as source_file:
            with open(destination_path, 'w') as destination_file:
                destination_file.write(source_file.read())
        print("File copied successfully.")
    except FileNotFoundError:
        print("Source file not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

def main():
    source_file_path = "hello.txt"
    destination_file_path = "hello_copy.txt"
    copy_file(source_file_path, destination_file_path)

if __name__ == "__main__":
    main()

```

## 5.Write a dart program to create 100 files using loop.
```dart
import 'dart:io';

void main() {
  for (int i = 1; i <= 100; i++) {
    createFile('file_$i.txt', 'This is the content of file $i.');
  }
}

void createFile(String filename, String content) {
  File file = File(filename);

  try {
    file.writeAsStringSync(content);
    print('File $filename created successfully.');
  } catch (e) {
    print('An error occurred: $e');
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File file_1.txt created successfully.
File file_2.txt created successfully.
File file_3.txt created successfully.
File file_4.txt created successfully.
File file_5.txt created successfully.
File file_6.txt created successfully.
File file_7.txt created successfully.
File file_8.txt created successfully.
File file_9.txt created successfully.
File file_10.txt created successfully.
File file_11.txt created successfully.
File file_12.txt created successfully.
File file_13.txt created successfully.
File file_14.txt created successfully.
File file_15.txt created successfully.
File file_16.txt created successfully.
File file_17.txt created successfully.
File file_18.txt created successfully.
File file_19.txt created successfully.
File file_20.txt created successfully.
File file_21.txt created successfully.
File file_22.txt created successfully.
File file_23.txt created successfully.
File file_24.txt created successfully.
File file_25.txt created successfully.
File file_26.txt created successfully.
File file_27.txt created successfully.
File file_28.txt created successfully.
File file_29.txt created successfully.
File file_30.txt created successfully.
File file_31.txt created successfully.
File file_32.txt created successfully.
File file_33.txt created successfully.
File file_34.txt created successfully.
File file_35.txt created successfully.
File file_36.txt created successfully.
File file_37.txt created successfully.
File file_38.txt created successfully.
File file_39.txt created successfully.
File file_40.txt created successfully.
File file_41.txt created successfully.
File file_42.txt created successfully.
File file_43.txt created successfully.
File file_44.txt created successfully.
File file_45.txt created successfully.
File file_46.txt created successfully.
File file_47.txt created successfully.
File file_48.txt created successfully.
File file_49.txt created successfully.
File file_50.txt created successfully.
File file_51.txt created successfully.
File file_52.txt created successfully.
File file_53.txt created successfully.
File file_54.txt created successfully.
File file_55.txt created successfully.
File file_56.txt created successfully.
File file_57.txt created successfully.
File file_58.txt created successfully.
File file_59.txt created successfully.
File file_60.txt created successfully.
File file_61.txt created successfully.
File file_62.txt created successfully.
File file_63.txt created successfully.
File file_64.txt created successfully.
File file_65.txt created successfully.
File file_66.txt created successfully.
File file_67.txt created successfully.
File file_68.txt created successfully.
File file_69.txt created successfully.
File file_70.txt created successfully.
File file_71.txt created successfully.
File file_72.txt created successfully.
File file_73.txt created successfully.
File file_74.txt created successfully.
File file_75.txt created successfully.
File file_76.txt created successfully.
File file_77.txt created successfully.
File file_78.txt created successfully.
File file_79.txt created successfully.
File file_80.txt created successfully.
File file_81.txt created successfully.
File file_82.txt created successfully.
File file_83.txt created successfully.
File file_84.txt created successfully.
File file_85.txt created successfully.
File file_86.txt created successfully.
File file_87.txt created successfully.
File file_88.txt created successfully.
File file_89.txt created successfully.
File file_90.txt created successfully.
File file_91.txt created successfully.
File file_92.txt created successfully.
File file_93.txt created successfully.
File file_94.txt created successfully.
File file_95.txt created successfully.
File file_96.txt created successfully.
File file_97.txt created successfully.
File file_98.txt created successfully.
File file_99.txt created successfully.
File file_100.txt created successfully.</code>
</pre>
</details>

### • Java
```java
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;

public class CreateFiles {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            String filename = "file_" + i + ".txt";
            String content = "This is the content of file " + i + ".";
            createFile(filename, content);
        }
    }

    public static void createFile(String filename, String content) {
        try {
            File file = new File(filename);
            FileWriter writer = new FileWriter(file);
            writer.write(content);
            writer.close();
            System.out.println("File " + filename + " created successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred: " + e.getMessage());
        }
    }
}
```
### • Python
```python
for i in range(1, 101):
    filename = f'file_{i}.txt'
    content = f'This is the content of file {i}.'
    
    with open(filename, 'w') as file:
        file.write(content)
    
    print(f'File {filename} created successfully.')

```

## 6.Write a dart program to delete the file “hello_copy.txt”. Make sure you have created the file “hello_copy.txt.
```dart
import 'dart:io';

void main() {
  final filename = 'hello_copy.txt';
  if (File(filename).existsSync()) {
    deleteFile(filename);
  } else {
    print("File $filename does not exist.");
  }
}

void deleteFile(String filename) {
  try {
    File(filename).deleteSync();
    print("File $filename deleted successfully.");
  } catch (e) {
    print("An error occurred: $e");
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File hello_copy.txt deleted successfully.</code>
</pre>
</details>

### • C
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    const char *filename = "hello_copy.txt";
    
    if (remove(filename) == 0) {
        printf("File %s deleted successfully.\n", filename);
    } else {
        printf("File %s could not be deleted.\n", filename);
    }

    return 0;
}
 ```
### • Python
```python
import os

filename = "hello_copy.txt"

if os.path.exists(filename):
    os.remove(filename)
    print(f"File {filename} deleted successfully.")
else:
    print(f"File {filename} does not exist.")
```

## 7.Write a dart program to store name, age, and address of students in a csv file and read it.
```dart
import 'dart:io';
import 'package:csv/csv.dart';

void main() {
  final students = <Map<String, dynamic>>[];

  // Collect student information
  for (var i = 1; i <= 3; i++) {
    stdout.write('Enter name of student $i: ');
    final name = stdin.readLineSync() ?? '';
    stdout.write('Enter age of student $i: ');
    final age = stdin.readLineSync() ?? '';
    stdout.write('Enter address of student $i: ');
    final address = stdin.readLineSync() ?? '';

    students.add({
      'Name': name,
      'Age': age,
      'Address': address,
    });
  }
  // Write the student information to a CSV file
  final csvFile = File('students.csv');
  csvFile.writeAsString(const ListToCsvConverter().convert(students));

  print('Student information has been saved to students.csv');

  // Read and display the contents of the CSV file
  final csvContent = csvFile.readAsStringSync();
  final csvToList = CsvToListConverter().convert(csvContent);

  print('\nStudent information from students.csv:');
  for (final row in csvToList) {
    final name = row[0];
    final age = row[1];
    final address = row[2];

    print('Name: $name, Age: $age, Address: $address');
  }
}

   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Data written to students.csv
Name: Alice, Age: 20, Address: 123 Main St
Name: Bob, Age: 22, Address: 456 Elm St
Name: Eve, Age: 19, Address: 789 Oak St.</code>
</pre>
</details>

### • Python
```python
import csv

class Student:
    def __init__(self, name, age, address):
        self.name = name
        self.age = age
        self.address = address
    
    def to_csv_row(self):
        return [self.name, str(self.age), self.address]

    @classmethod
    def from_csv_row(cls, csv_row):
        return cls(csv_row[0], int(csv_row[1]), csv_row[2])

def main():
    students = [
        Student('Alice', 20, '123 Main St'),
        Student('Bob', 22, '456 Elm St'),
        Student('Eve', 19, '789 Oak St')
    ]

    csv_file = 'students.csv'

    # Writing to CSV file
    with open(csv_file, mode='w', newline='') as file:
        writer = csv.writer(file)
        for student in students:
            writer.writerow(student.to_csv_row())

    print('Data written to students.csv')

    # Reading from CSV file
    read_students = []
    with open(csv_file, mode='r') as file:
        reader = csv.reader(file)
        for row in reader:
            read_students.append(Student.from_csv_row(row))

    # Displaying read data
    for student in read_students:
        print(f'Name: {student.name}, Age: {student.age}, Address: {student.address}')

if __name__ == "__main__":
    main()
```
# Presentation
Link video : https://youtu.be/NQtiZqzITSc?feature=shared <br>
Link slides : https://github.com/PhurichaN/668/blob/main/Practice5_630710668.pdf <br>
Link download slides : [Practice5_630710668.pdf](https://github.com/soonklang/dart-tutorial/files/12774793/Practice5_630710668.pdf)


## < Reference >
https://dart-tutorial.com/introduction-and-basics/questions-for-practice-1/<br>
https://flutterawesome.com/learn-the-dart-programming-language-in-this-full-tutorial-for-beginners/<br>
https://www.geeksforgeeks.org/basics-file-handling-c/?ref=lbp<br>
https://www.geeksforgeeks.org/file-class-in-java/?ref=lbp<br>
https://www.geeksforgeeks.org/file-handling-python/?ref=lbp<br>
