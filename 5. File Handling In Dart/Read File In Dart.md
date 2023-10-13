# Read File in Dart
สันนิษฐานว่ามีไฟล์ที่ชื่อ test.txt อยู่ใน directory เดียวกันกับโปรแกรม dart

**test.txt**
```dart
Welcome to test.txt file.
This is a test file.
 ```
ไฟล์จะเก็บ path ที่สามารถดำเนินการได้ เราสามารถรับ directory หลักของไฟล์ได้โดยใช้ parent ซึ่งเป็นคุณสมบัติที่สืบทอดมาจาก **FileSystemEntity**
สร้าง File object ใหม่ด้วย pathname เพื่อเข้าถึงไฟล์ที่ระบุบนระบบไฟล์จากโปรแกรม

```dart
var myFile = File('test.txt');
```

ตอนนี้เราสามารถอ่านไฟล์นี้ได้โดยใช้คลาส File และเมธอด **readAsStringSync()** หรือ **readAsString()** ได้เลย

 #### `ตัวอย่างที่ 1`
  >อ่านเนื้อหาทั้งหมดจากไฟล์เป็นสตริงโดยใช้เมธอด readAsStringSync() แบบซิงโครนัสและจะ return เนื้อหาของไฟล์เป็นสตริง: 
```dart
// dart program to read from file
import 'dart:io';

void main() {
  // creating file object
  File file = File('test.txt');
  // read file
  String contents = file.readAsStringSync();
  // print file
  print(contents);
}
 ```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

#### `ตัวอย่างที่ 2`
```dart
import 'dart:io';
 
void main() {
  var contents = File('resources/file.txt').readAsStringSync();
  print('File Contents\n---------------');
  print(contents);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File Contents
---------------
Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

#### `ตัวอย่างที่ 3`
  >อ่านเนื้อหาทั้งหมดจากไฟล์เป็นสตริงโดยใช้เมธอด readAsString() แบบอะซิงโครนัสและจะ return Future< String > ในฟังก์ชันcallback จะได้รับ String พร้อมเนื้อหาของไฟล์: 
```dart
import 'dart:io';
 
void main() {
  File('resources/test.txt').readAsString().then((String contents) {
    print('File Contents\n---------------');
    print(contents);
  });
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File Contents
---------------
Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

## Get File Information
ในตัวอย่างต่อไปนี้ จะเรียนรู้วิธีการรับข้อมูลไฟล์ เช่น ตำแหน่งไฟล์ ขนาดไฟล์ และเวลาที่แก้ไขล่าสุด

```dart
import 'dart:io';

void main() {
  // open file
  File file = File('test.txt');
  // get file location
  print('File path: ${file.path}');
  // get absolute path
  print('File absolute path: ${file.absolute.path}');
  // get file size
  print('File size: ${file.lengthSync()} bytes');
  // get last modified time
  print('Last modified: ${file.lastModifiedSync()}');
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>File path: test.txt
File absolute path: /home/iambrp/Desktop/Dart Practice/test.txt
File size: 25 bytes
Last modified: 2023-01-28 11:00:32.000</code>
</pre>
</details>

**! NOTE**
ถ้าเราพยายามรับข้อมูลของไฟล์ที่ไม่มีอยู่ ไฟล์นั้นจะทำให้เกิดข้อยกเว้น

## CSV File
ไฟล์CSV (Comma Separated Values) คือไฟล์ข้อความที่มีข้อมูลอยู่ในรูปแบบตาราง โดยคอลัมน์จะถูกแบ่งด้วยเครื่องหมายcomma และแถวจะถูกแบ่งด้วยการขึ้นบรรทัดใหม่ ไฟล์ CSV ใช้สำหรับ:

 - การแลกเปลี่ยนข้อมูลระหว่างแอพพลิเคชั่นต่างๆ
 - การสำรองและกู้คืนข้อมูล
 - การนำเข้าและส่งออกข้อมูลจากฐานข้อมูล
 - ระบบอัตโนมัติของงานการประมวลผลข้อมูล

## Read CSV File In Dart
สันนิษฐานว่ามีไฟล์ที่ชื่อ test.csv อยู่ในdirectoryเดียวกันกับโปรแกรมdart

**test.csv**
```dart
Name,Email,Phone
John, john@gmail.com, 1234567890
Smith, smith@gmail.com, 0987654321
```

ตอนนี้เราสามารถอ่านไฟล์นี้ได้โดยใช้คลาส File และเมธอด **readAsStringSync()** เราจะใช้เมธอด **split()** เพื่อแยกสตริงออกเป็นlistของสตริง

```dart
// dart program to read from csv file
import 'dart:io';

void main() {
  // open file
  File file = File('test.csv');
  // read file
  String contents = file.readAsStringSync();
  // split file using new line
  List<String> lines = contents.split('\n');
  // print file
  print('---------------------');
  for (var line in lines) {
    print(line);
  }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>---------------------
Name,Email,Phone
John, john@gmail.com, 1234567890
Smith, smith@gmail.com, 0987654321</code>
</pre>
</details>

## Read Only Part Of File
เราสามารถอ่านแค่บางส่วนของไฟล์ได้โดยการใช้เมธอด **substring()** 
ตัวอย่างต่อไปนี้จะอ่านเฉพาะตัวอักขระ 10 ตัวแรกของไฟล์ โดยที่ไฟล์ชื่อว่า **test.txt** อยู่ในdirectoryเดียวกันกับโปรแกรมdart

```dart
Welcome to test.txt file
This is a test file.
```

```dart
// dart program to read from file
import 'dart:io';

void main() {
  // open file
  File file = new File('test.txt');
  // read only first 10 characters
  String contents = file.readAsStringSync().substring(0, 10);
  // print file
  print(contents);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to</code>
</pre>
</details>

## Read File From Specific Directory
หากต้องการอ่านไฟล์จากspecific directory จะต้องระบุpathแบบเต็มของไฟล์นั้น

```dart
// dart program to read from file
import 'dart:io';

void main() {
  // open file
  File file = File('C:\\Users\\test.txt');
  // read file
  String contents = file.readAsStringSync();
  // print file
  print(contents);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to test.txt file.
This is a test file.</code>
</pre>
</details>

## การอ่านไฟล์ในภาษาอื่นๆ
- Python

  ในการเปิดอ่านไฟล์ของPython จะใช้ฟังก์ชันbuilt-in **open()**
  ฟังก์ชัน **open()** ต้องรับพารามิเตอร์ 2 ตัว (filenameและmode)
  โดย **mode "r"** คือ อักขระ "r" ตัวเดียว ซึ่งแสดงถึงการอ่านไฟล์
  ฟังก์ชัน **open()** จะreturnวัตถุไฟล์ ซึ่งมีเมธอด **read()** สำหรับการอ่านเนื้อหาในไฟล์

  ```python
  f = open("test.txt", "r")
  print(f.read())
  ```
  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Welcome to test.txt file.
  This is a test file.</code>
  </pre>
  </details>

  หากไฟล์อยู่ในตำแหน่งอื่น เราต้องระบุไฟล์path

  #### `ตัวอย่าง`
  >เปิดไฟล์ในตำแหน่งอื่น:
  ```python
  f = open("D:\\myfiles\test.txt", "r")
  print(f.read())
  ```

  ### Read Only Parts of the File
  ตามค่าเริ่มต้นแล้วเมธอด **read()** จะreturnข้อความทั้งหมด แต่เราสามารถระบุจำนวนอักขระที่จะส่งคืนได้
  
  #### `ตัวอย่าง`
  >Returnอักขระ 7 ตัวแรกของไฟล์:
  ```python
  f = open("test.txt", "r")
  print(f.read(7))
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Welcome</code>
  </pre>
  </details>

  ### Read CSV File In Python
  เราจะimport pandas ซึ่งเป็นไลบรารี Python ที่ใช้ในการจัดการและวิเคราะห์ข้อมูล จะมีเมธอด **.read_csv()** ที่เราต้องการเพื่ออ่านไฟล์csv

  ```python
  import pandas as pd
  data = pd.read_csv("test.csv")
  data
  ```

- C

  การเปิดอ่านไฟล์ของภาษา C จะใช้ฟังก์ชัน **fopen()** ซึ่งรับพารามิเตอร์ 2 ตัว ก็คือ **filename** และ **mode "r"**

  #### `ตัวอย่างที่ 1`
  ```c
  FILE *fptr;

  // Open a file in read mode
  fptr = fopen("filename.txt", "r");
  ```
  
  #### `ตัวอย่างที่ 2`
  > mode "rb" ใช้ในเปิดการอ่านไฟล์ในโหมดไบนารี
  ```c
  FILE *fptr;

  // Open for reading in binary mode
  fptr = fopen("filename.txt", "rb");
  ```

  หากไฟล์อยู่ในตำแหน่งอื่น เราต้องระบุไฟล์pathแบบเต็มไปยังไฟล์รวมถึงdirectoryด้วย

  ```c
  #include <stdio.h>

  int main() {
    FILE *file;
    char filepath[] = "/path/to/your/directory/yourfile.txt";
    
    file = fopen(filepath, "r");
    
    if (file == NULL) {
        perror("Error opening file");
        return 1;
    }
    
    char buffer[1024];
    while (fgets(buffer, sizeof(buffer), file) != NULL) {
        printf("%s", buffer);
    }
    
    fclose(file);
    return 0;
    }
  ```

  แทนที่ "/path/to/your/directory/yourfile.txt" ด้วยpathไปยังไฟล์ที่ต้องการอ่าน ฟังก์ชัน **fopen** จะเปิดไฟล์สำหรับการอ่าน (mode "r") และฟังก์ชัน fgets ใช้เพื่ออ่านไฟล์ทีละบรรทัดลงในบัฟเฟอร์

- Java

  การเปิดอ่านไฟล์ของภาษา Java จะใช้คลาส **Scanner** เพื่ออ่านเนื้อหาของไฟล์

  #### `ตัวอย่างที่ 1`
  >ใช้คลาส Scanner ในการอ่านไฟล์
  ```java
   import java.io.File;  // Import the File class
   import java.io.FileNotFoundException;  // Import this class to handle errors
   import java.util.Scanner; // Import the Scanner class to read text files

   public class ReadFile {
    public static void main(String[] args) {
     try {
       File myObj = new File("filename.txt");
       Scanner myReader = new Scanner(myObj);
       while (myReader.hasNextLine()) {
         String data = myReader.nextLine();
         System.out.println(data);
       }
       myReader.close();
     } catch (FileNotFoundException e) {
       System.out.println("An error occurred.");
       e.printStackTrace();
      }
    }
  }
  ```
  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Files in Java might be tricky, but it is fun enough!</code>
  </pre>
  </details>

  #### `ตัวอย่างที่ 2`
  >ใช้คลาส BufferedReader ในการอ่านจากไฟล์ทีละบรรทัดและแสดงผลออกทางหน้าจอ
  ```java
  import java.io.BufferedReader;
  import java.io.IOException;
  import java.nio.charset.StandardCharsets;
  import java.nio.file.Files;
  import java.nio.file.Path;
  import java.nio.file.Paths;

  public class ReadFromFile {
      public static void main(String[] args) {  
          try {
              Path file = Paths.get("D:\\example.txt");  //ตัวแปร file เป็นพาธของไฟล์ในการอ่าน
              BufferedReader reader = Files.newBufferedReader(file ,   
                      StandardCharsets.UTF_8); //reader เป็นตัวแปรที่ใช้สำหรับอ่านไฟล์
              String line = null;  //line เป็นตัวแปรเก็บค่าชั่วคราวที่ผ่านมากจากไฟล์

              while ((line = reader.readLine()) != null) {
                  System.out.println(line);
              }  //เมธอด reader.readLine() จะอ่านข้อมูลจากไฟล์ที่ละบรรทัด จนกว่าค่าที่ส่งกลับมาจะเป็น null

              reader.close();  //ต้องทำการปิดไฟล์เสมอโดยการใช้เมธอด close() เพื่อให้ไฟล์สามารถนำไปใช้ในโปรแกรมอื่นต่อ
          } catch (IOException e) {
              System.err.println("IOException: " + e.getMessage());
          }
      }
  }
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>Hello,
  Welcome to MarcusCode tutorial
  This is reading from text file example
  This file has 4 lines</code>
  </pre>
  </details>

  ### Get File Information
  ถ้าการข้อมูลเพิ่มเติมเกี่ยวกับไฟล์ ให้ใช้ File methods ใดๆ:
  
  #### `ตัวอย่าง`
  ```java
  import java.io.File;  // Import the File class

  public class GetFileInfo { 
    public static void main(String[] args) {
      File myObj = new File("filename.txt");
      if (myObj.exists()) {
        System.out.println("File name: " + myObj.getName());
        System.out.println("Absolute path: " + myObj.getAbsolutePath());
        System.out.println("Writeable: " + myObj.canWrite());
        System.out.println("Readable " + myObj.canRead());
        System.out.println("File size in bytes " + myObj.length());
      } else {
        System.out.println("The file does not exist.");
      }
    }
  }
  ```

  <details>
  <summary><strong>Output</strong></summary>
  <pre>
  <code>File name: filename.txt
  Absolute path: C:\Users\MyName\filename.txt
  Writeable: true
  Readable: true
  File size in bytes: 0</code>
  </pre>
  </details>

  **! NOTE**
  มีคลาสอื่นๆอีกมากมายใน Java API ที่สามารถใช้เพื่ออ่านและเขียนไฟล์ใน **Java: FileReader, BufferedReader, Files, Scanner, FileInputStream, FileWriter, BufferedWriter, FileOutputStream** ,etc. ถ้าจะใช้อันไหนขึ้นอยู่กับเวอร์ชันของ Java ที่ใช้งานอยู่และไม่ว่าคุณจำเป็นต้องอ่านไบต์หรืออักขระ และขนาดของไฟล์/บรรทัด และอื่นๆ

   ### Read CSV file in Java
  มีอยู่ 3 วิธีในการอ่านไฟล์ CSV ใน Java
  - **Scanner** class
  - **String.split()** method
  - การใช้ **OpenCSV** API
 
    ### Scanner class
    คลาส Scanner จะจัดเตรียม constructor ที่สร้างค่าที่สแกนจากไฟล์ที่ระบุ และแบ่งข้อมูลอยู่ในรูปแบบของ token จะใช้ delimiter pattern โดยค่าเริ่มต้นจะตรงกับช่องว่าง จากนั้นผลลัพธ์ token จะแปลงเป็นค่าประเภทต่างๆ โดยใช้เมธอด next()

    #### `ตัวอย่าง`
    ```java
    import java.io.*;  
    import java.util.Scanner;  
    public class ReadCSVExample1{  
      public static void main(String[] args) throws Exception{  
      //parsing a CSV file into Scanner class constructor  
        Scanner sc = new Scanner(new File("F:\\CSVDemo.csv"));  
        sc.useDelimiter(",");   //sets the delimiter pattern  
       while (sc.hasNext())  //returns a boolean value {  
         System.out.print(sc.next());  //find and returns the next complete token from this scanner  
       }   
        sc.close();  //closes the scanner  
       }  
    }  
    ```

    <details>
    <summary><strong>Output</strong></summary>
    <pre>
    <code>Shashank, Mishra, Auditor, 909090090, 45000, Moti Vihar
    Naveen, Singh, Accountant, 213344455, 12000, Shastri Nagar
    Mahesh, Nigam, Sr. Manager, 787878878, 30000, Ashok Nagar
    Manish, Gupta, Manager, 999988765, 20000, Saket Nagar</code>
    </pre>
    </details>

    ### String.split() method
    **String.split()** ระบุตัวคั่นและแยกแถวออกเป็นtokens
 
    **Syntax**
    ```java
    public String[] split(String regex) 
    ```

    #### `ตัวอย่าง`
    >ใช้คลาส BufferedReader ในการอ่าน โดยจะอ่านไฟล์ทีละบรรทัดจนกระทั่งถึงอักขระ EOF (สิ้นสุดไฟล์)
    ```java
    import java.io.BufferedReader;  
    import java.io.FileReader;  
    import java.io.IOException;  
    public class ReadCSVExample2 {  
     public static void main(String[] args){  
      String line = "";  
      String splitBy = ",";  
    try {  
       //parsing a CSV file into BufferedReader class constructor  
      BufferedReader br = new BufferedReader(new FileReader("CSVDemo.csv"));  
      while ((line = br.readLine()) != null)   //returns a Boolean value {  
       String[] employee = line.split(splitBy);    // use comma as separator  
        System.out.println("Employee [First Name=" + employee[0] + ", Last Name=" + employee[1] + ", Designation=" + employee[2] + ", Contact=" + employee[3] + ", Salary= " + employee[4] + ", City= " + employee[5] +"]");  
          }  
        }   
        catch (IOException e) {  
         e.printStackTrace();  
        }  
      }  
    }  
    ```

    <details>
    <summary><strong>Output</strong></summary>
    <pre>
    <code>Employee [First Name= Shashank, Last Name= Mishra, Designation= Auditor, 
    Contact= 909090090, Salary= 45000, City= Moti Vihar]
    Employee [First Name= Naveen, Last Name=Singh, Designation= Accountant, 
    Contact=213344455, Salary= 12000, City= Shastri Nagar]
    Employee [First Name= Mahesh, Last Name=Nigam, Designation= Sr. Manager, 
    Contact=787878878, Salary= 30000, City= Ashok Nagar]
    Employee [First Name= Manish, Last Name=Gupta, Designation= Manager, 
    Contact=999988765, Salary= 20000, City= Saket Nagar]</code>
    </pre>
    </details>

    ### การใช้ OpenCSV API
    OpenCSV เป็น API ของบุคคลที่สามซึ่งมีไลบรารีมาตรฐานสำหรับอ่านไฟล์ CSV หลากหลายเวอร์ชัน ไลบรารีให้การควบคุมที่ดีกว่าในการจัดการไฟล์ CSV และยังสามารถอ่านรูปแบบไฟล์ TDF (Tab-Delimited File) ได้

    **Syntax**
    ```java
    public CSVReder(Reader reader, char separator)  
    //OR  
    public CSVReder(Reader reader)  
    ```

    #### `ตัวอย่าง`
    ```java
    import java.io.FileReader;  
    import com.opencsv.CSVReader;  
    public class ReadCSVExample3  {    
     public static void main(String[] args)  {  
      CSVReader reader = null;  
     try  {  
      //parsing a CSV file into CSVReader class constructor  
        reader = new CSVReader(new FileReader("F:\\CSVDemo.csv"));  
        String [] nextLine;  
        //reads one line at a time  
        while ((nextLine = reader.readNext()) != null)  {  
         for(String token : nextLine)  {  
          System.out.print(token);  
          }  
        System.out.print("\n");  
        }  
       }  
       catch (Exception e)  {  
        e.printStackTrace();  
       }  
      }  
    }  
    ```

    <details>
    <summary><strong>Output</strong></summary>
    <pre>
    <code>Shashank Mishra Auditor 909090090 45000 Moti Vihar
    Naveen Singh Accountant 213344455 12000 Shastri Nagar
    Mahesh NigamSr. Manager 787878878 30000 Ashok Nagar
    Manish Gupta Manager 999988765 20000 Saket Nagar</code>
    </pre>
    </details>

## Reference
https://dart-tutorial.com/file-handling-in-dart/read-file-in-dart/<br>
https://api.dart.dev/stable/3.1.0/dart-io/File-class.html<br>
https://www.tutorialkart.com/dart/dart-read-file-as-string/#gsc.tab=0<br>
https://www.w3schools.com/python/python_file_open.asp<br>
https://www.w3schools.com/java/java_files_read.asp<br>
https://www.geeksforgeeks.org/different-ways-reading-text-file-java/<br>
https://www.w3schools.com/c/c_files_read.php<br>
https://earthly.dev/blog/csv-python/<br>
http://marcuscode.com/lang/java/files<br>
https://www.javatpoint.com/how-to-read-csv-file-in-java<br>

## Slide
[Read File In Dart.pdf](https://drive.google.com/file/d/1aToIgireZPNZWOCuhpNGwAi4lMeVsLiC/view?usp=sharing)<br>
[Read File In Dart v2.pdf](https://github.com/tmwwtcrrt/slide/blob/main/Read-file-in-Dart-v2.pdf?raw=true)<br>

## Video
https://www.youtube.com/watch?v=exkBzlr8bZ4<br>
