# STRING IN DART

## Methods Of String
*	trim(): ส่งกลับสตริงโดยไม่มีช่องว่างนำหน้าและต่อท้าย
* compareTo(): เปรียบเทียบวัตถุนี้กับวัตถุอื่น
*  replaceAll(): แทนที่สตริงย่อยทั้งหมดที่ตรงกับรูปแบบที่ระบุด้วยค่าที่กำหนด
*   split(): แยกสตริงที่ตรงกับตัวคั่นที่ระบุและส่งคืนรายการสตริงย่อย
*    toString(): ส่งกลับการแสดงสตริงของวัตถุนี้
* substring(): ส่งกลับสตริงย่อยของสตริงนี้ที่ขยายจาก startIndex แบบรวม ถึง endIndex แบบเอกสิทธิ์เฉพาะบุคคล
*  codeUnitAt(): ส่งกลับหน่วยรหัส UTF-16 16 บิตที่ดัชนีที่กำหนด

## Trim String In Dart

   Return สตริงใหม่โดยการลบช่องว่างนำหน้าและต่อท้ายทั้งหมด และยังสามารถใช้เมธอด trimLeft() และ trimRight() เพื่อลบช่องว่างจากซ้ายและขวาตามลำดับ

> หมายเหตุ: วิธีการ trim() ใน Dart จะไม่ลบช่องว่างตรงกลาง 

#### Return Type
   Return ค่า String

#### ตัวอย่าง trim() ในภาษา Dart
```dart
void main() { 
   String str1 = "hello"; 
   String str2 = "hello world"; 
   String str3 = "hello"; 
   
   print(str1.trim()); 
   print(str2.trim()); 
   print(str3.trim()); 
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>hello 
hello world 
hello</code></pre>
</details>
<br>

#### ตัวอย่าง trim() ในภาษา Java
```java
public class Main {
  public static void main(String[] args) {
    String myStr = "       Hello World!        ";
    System.out.println(myStr);
    System.out.println(myStr.trim());
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>       Hello World!              
Hello World!</code></pre>
</details>
<br>


#### ตัวอย่าง trim() ในภาษา Python
Python มีวิธีการ 3 วิธีสำหรับการตัดช่องว่างและอักขระที่นำหน้าและต่อท้ายจากสตริง
> วิธีที่ 1 strip()
```
greeting = "     Hello!  "

stripped_greeting = greeting.strip()

print(stripped_greeting,"How are you?")
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Hello! How are you?</code></pre>
</details>
<br>

> วิธีที่ 2 lstrip()
```
greeting = "     Hello!  "

stripped_greeting = greeting.lstrip()

print(stripped_greeting,"How are you?" )

```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Hello!   How are you?</code></pre>
</details>
<br>

> วิธีที่ 3 rstrip()
```
greeting = "     Hello!  "

stripped_greeting = greeting.rstrip()

print(stripped_greeting,"How are you?")
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>     Hello! How are you?</code></pre>
</details>
<br>

## Compare String In Dart

  Return สตริงใหม่โดยการลบช่องว่างนำหน้าและต่อท้ายทั้งหมด วิธีการนี้สามารถเปรียบเทียบสตริงสองสตริงได้ 

#### Return Type
   Return จำนวนเต็มที่แสดงถึงความสัมพันธ์ระหว่าง String สองอัน
      0 - เมื่อสตริงเท่ากัน
      1 - เมื่อสตริงแรกมากกว่าสตริงที่สอง
      -1 - เมื่อสตริงแรกมีขนาดเล็กกว่าสตริงที่สอง

   #### ตัวอย่าง compareTo() ในภาษา Dart
```dart
void main() { 
   String str1 = "A"; 
   String str2 = "A"; 
   String str3 = "B"; 
   
   print("str1.compareTo(str2): ${str1.compareTo(str2)}"); 
   print("str1.compareTo(str3): ${str1.compareTo(str3)}"); 
   print("str3.compareTo(str2): ${str3.compareTo(str2)}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>str1.compareTo(str2): 0 
str1.compareTo(str3): -1 
str3.compareTo(str2): 1 </code></pre>
</details>
<br>

 #### ตัวอย่าง compareTo() ในภาษา Java
 ```java
public class Main {
  public static void main(String[] args) {
    String myStr1 = "Hello";
    String myStr2 = "Hello";
    System.out.println(myStr1.compareTo(myStr2)); // Returns 0 because they are equal
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>0 </code></pre>
</details>
<br>

#### ตัวอย่าง compareTo() ในภาษา Python
```
string1 = "Hello"
string2 = "Hello"

if string1 == string2:
    print("Both strings are equal")
else:
    print("Both strings are not equal")
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Both strings are equal</code></pre>
</details>
<br>

## Replace String In Dart

   สามารถแแทนที่ค่าหนึ่งด้วยอีกค่าหนึ่งด้วยวิธีแทนที่ทั้งหมด("เก่า", "ใหม่") ใน Dart มันจะแทนที่คำ "เก่า" ทั้งหมดด้วย "ใหม่" 

#### Return Type
   Return ค่า String


  #### ตัวอย่าง replaceAll() ในภาษา Dart
```dart
void main() { 
   String str1 = "Hello World"; 
   print("New String: ${str1.replaceAll('World','ALL')}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>New String: Hello ALL </code></pre>
</details>
<br>

 #### ตัวอย่าง replaceAll() ในภาษา Java
 ```java
public class Main {
  public static void main(String[] args) {
    String myStr = "Hello";
    System.out.println(myStr.replace('l', 'p'));
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Heppo </code></pre>
</details>
<br>

 #### ตัวอย่าง replaceAll() ในภาษา Python
 ```python
txt = "one one was a race horse, two two was one too."
x = txt.replace("one", "three")
print(x)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>three three was a race horse, two two was three too." </code></pre>
</details>
<br>


## Split String In Dart

สามารถแยกสตริงที่คั่นด้วยช่องว่าง เครื่องหมายต่างๆ หรือข้อความอื่นๆ และreturn สตริงย่อย

#### Return Type
   Return ค่า String objects.


  #### ตัวอย่าง split() ในภาษา Dart
```dart
void main() { 
   String str1 = "Today, is, Thursday"; 
   print("New String: ${str1.split(',')}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>New String: [Today,  is,  Thursday]</code></pre>
</details>
<br>

#### ตัวอย่าง split() ในภาษา Java
 ```java
import java.util.Arrays;
class Main {
  public static void main(String[] args) {
    String vowels = "a::b::c::d:e";

    String[] result = vowels.split("::");
    System.out.println("result = " + Arrays.toString(result));
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>result = [a, b, c, d:e]</code></pre>
</details>
<br>

#### ตัวอย่าง split() ในภาษา Python
 ```java
txt = "welcome to the jungle"
x = txt.split()
print(x)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>['welcome', 'to', 'the', 'jungle']</code></pre>
</details>
<br>

## ToString In Dart

Return การแสดงสตริงของค่า/วัตถุ

#### Return Type
   Return ค่า String objects.


  #### ตัวอย่าง toString() ในภาษา Dart
```dart
void main() { 
   int n = 12; 
   var res = n.toString(); 
   print("New String: ${res}");
}   
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>New String: 12</code></pre>
</details>
<br>

#### ตัวอย่าง toString() ในภาษา Java
 ```java
public class Test { 

   public static void main(String args[]) {
      Integer x = 5;

      System.out.println(x.toString());  
      System.out.println(Integer.toString(12)); 
   }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>5
12</code></pre>
</details>
<br>

## SubString In Dart

สามารถใช้สตริงย่อยใน Dart เมื่อคุณต้องการรับข้อความจากตำแหน่งใดก็ได้

> หมายเหตุ - ดัชนีจะเป็นศูนย์ กล่าวคือ อักขระตัวแรกจะมีดัชนีเป็น 0 ไปเรื่อยๆ

#### Return Type
   Return ค่า String objects.


  #### ตัวอย่าง substring() ในภาษา Dart
```dart
void main() { 
   String str1 = "Hello World"; 
   print("New String: ${str1.substring(6)}"); 
   
   // from index 6 to the last index 
   print("New String: ${str1.substring(2,6)}"); 
   
   // from index 2 to the 6th index 
   } 
}   
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>New String: World 
New String: llo </code></pre>
</details>
<br>

#### ตัวอย่าง substring() ในภาษา Java
 ```java
class Main {
  public static void main(String[] args) {
    String str1 = "java is fun";

    System.out.println(str1.substring(0, 4));
  }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>java</code></pre>
</details>
<br>

#### ตัวอย่าง substring() ในภาษา Python
 ```python
s = 'My Name is Pankaj'

# create substring using slice
name = s[11:]
print(name)

# list of substrings using split
l1 = s.split()
print(l1)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Pankaj
['My', 'Name', 'is', 'Pankaj']</code></pre>
</details>
<br>

## Reverse String In Dart

หากต้องการย้อนกลับสตริงใน Dart สามารถย้อนกลับได้โดยใช้วิธีแก้ไขปัญหาอื่น 

#### ตัวอย่าง reverse() ในภาษา Dart
```dart
void main() { 
  String input = "Hello"; 
  print("$input Reverse is ${input.split('').reversed.join()}"); 
} 
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Hello Reverse is olleH </code></pre>
</details>
<br>

#### ตัวอย่าง reverse() ในภาษา Java
 ```java
import java.io.*;
import java.util.Scanner;
 
class GFG {
    public static void main (String[] args) {
       
        String str= "Geeks", nstr="";
        char ch;
       
      System.out.print("Original word: ");
      System.out.println("Geeks"); //Example word
       
      for (int i=0; i<str.length(); i++)
      {
        ch= str.charAt(i); //extracts each character
        nstr= ch+nstr; //adds each character in front of the existing string
      }
      System.out.println("Reversed word: "+ nstr);
    }
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Original word: Geeks
Reversed word: skeeG</code></pre>
</details>
<br>

#### ตัวอย่าง reverse() ในภาษา Python
```python
txt = "Hello World"[::-1]
print(txt)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>dlroW olleH</code></pre>
</details>
<br>


## วิธีการใช้ตัวอักษรตัวแรกของสตริงเป็นตัวพิมพ์ใหญ่ใน Dart

หากคุณต้องการใช้อักษรตัวแรกของ String ใน Dart ให้เป็นตัวพิมพ์ใหญ่ คุณสามารถใช้โค้ดต่อไปนี้

#### ตัวอย่างการใช้อักษรตัวแรกของ String ให้เป็นตัวพิมพ์ใหญ่ ในภาษา Dart
```dart
void main() { 
  String text = "hello world"; 
  print("Capitalized first letter of String: ${text[0].toUpperCase()}${text.substring(1)}"); 
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Capitalized first letter of String: Hello world</code></pre>
</details>
<br>

#### ตัวอย่างการใช้อักษรตัวแรกของ String ให้เป็นตัวพิมพ์ใหญ่ ในภาษา Java
```java
public class FirstLetterCapital1  
{  
public static void main(String args[])   
{  
System.out.println(capitalize("javatpoint"));     
System.out.println(capitalize("website"));          
System.out.println(capitalize("@javatpoint"));    
System.out.println(capitalize("it is the best website to learn technology."));   
}  
//user-defined function to capitalize the first letter also check for null string  
public static final String capitalize(String str)   
{  
if (str == null || str.length() == 0) return str;  
return str.substring(0, 1).toUpperCase() + str.substring(1);  
}  
}  
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Javatpoint
Website
@javatpoint
It is the best website to learn technology.</code></pre>
</details>
<br>

#### ตัวอย่างการใช้อักษรตัวแรกของ String ให้เป็นตัวพิมพ์ใหญ่ ในภาษา Python
Python มีวิธีการ 2 วิธี
> วิธีที่ 1
```
my_string = "programiz is Lit"

print(my_string[0].upper() + my_string[1:])
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Programiz is Lit</code></pre>
</details>
<br>

> วิธีที่ 2
```
my_string = "programiz is Lit"

cap_string = my_string.capitalize()

print(cap_string)
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Programiz is lit</code></pre>
</details>
<br>


## Reference

https://dart-tutorial.com/introduction-and-basics/string-in-dart/
https://www.tutorialspoint.com/dart_programming/dart_programming_string.htm
https://www.w3schools.com/python/python_ref_string.asp
https://www.programiz.com/python-programming/methods/string

https://www.freecodecamp.org/news/python-strip-how-to-trim-a-string-or-line/
