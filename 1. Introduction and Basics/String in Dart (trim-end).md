# STRING IN DART

## Methods Of String
*	trim(): ส่งกลับสตริงโดยไม่มีช่องว่างนำหน้าและต่อท้าย
* compareTo(): เปรียบเทียบวัตถุนี้กับวัตถุอื่น
*  replaceAll(): แทนที่สตริงย่อยทั้งหมดที่ตรงกับรูปแบบที่ระบุด้วยค่าที่กำหนด
*   split(): แยกสตริงที่ตรงกับตัวคั่นที่ระบุและส่งคืนรายการสตริงย่อย
*    toString(): ส่งกลับการแสดงสตริงของวัตถุนี้
* substring(): ส่งกลับสตริงย่อยของสตริงนี้ที่ขยายจาก startIndex แบบรวม ถึง endIndex แบบเอกสิทธิ์เฉพาะบุคคล
*  Reverse(): หากต้องการย้อนกลับสตริงใน Dart สามารถย้อนกลับได้โดยใช้วิธีแก้ไขปัญหาอื่น
  
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

#### ตัวอย่าง trim() ในภาษา C
```dart
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

char *trimString(char *str)
{
    char *end;
    while(isspace((unsigned char)*str)) str++;
    if(*str == 0)
        return str;
    end = str + strlen(str) - 1;

    while(end > str && isspace((unsigned char)*end)) end--;
    end[1] = '\0';
    return str;
}

int main(void) {
    const char *str1 = "  temporary string     ";
    printf("%s\n", str1);

    char *tmp = strdup(str1);
    printf("%s\n", trimString(tmp));

    free(tmp);
    exit(EXIT_SUCCESS);
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>  temporary string     
temporary string</code></pre>
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

#### ตัวอย่าง compareTo() ในภาษา C
```dart
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

int main() {
    const char* str1 = "hello there 1";
    const char* str2 = "hello there 2";
    const char* str3 = "Hello there 2";

    !strcmp(str1, str2) ?
        printf("strings are equal\n") :
        printf("strings are not equal\n");

    !strcmp(str1, str3) ?
        printf("strings are equal\n") :
        printf("strings are not equal\n");

    exit(EXIT_SUCCESS);
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>strings are not equal
strings are not equal</code></pre>
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

#### ตัวอย่าง replaceAll() ในภาษา C
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
 
// Function to replace a string with another
// string
char* replaceWord(const char* s, const char* oldW,
                const char* newW)
{
    char* result;
    int i, cnt = 0;
    int newWlen = strlen(newW);
    int oldWlen = strlen(oldW);
 
    // Counting the number of times old word
    // occur in the string
    for (i = 0; s[i] != '\0'; i++) {
        if (strstr(&s[i], oldW) == &s[i]) {
            cnt++;
 
            // Jumping to index after the old word.
            i += oldWlen - 1;
        }
    }
 
    // Making new string of enough length
    result = (char*)malloc(i + cnt * (newWlen - oldWlen) + 1);
 
    i = 0;
    while (*s) {
        // compare the substring with the result
        if (strstr(s, oldW) == s) {
            strcpy(&result[i], newW);
            i += newWlen;
            s += oldWlen;
        }
        else
            result[i++] = *s++;
    }
 
    result[i] = '\0';
    return result;
}
 
// Driver Program
int main()
{
    char str[] = "xxforxx xx for xx";
    char c[] = "xx";
    char d[] = "Geeks";
 
    char* result = NULL;
 
    // oldW string
    printf("Old string: %s\n", str);
 
    result = replaceWord(str, c, d);
    printf("New String: %s\n", result);
 
    free(result);
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Old string: xxforxx xx for xx
New String: GeeksforGeeks Geeks for Geeks</code></pre>
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

  #### ตัวอย่าง split() ในภาษา C
```c
#include <stdio.h>
#include <string.h>
 
int main()
{
    char str[] = "Geeks-for-Geeks";
 
    // Returns first token
    char *token = strtok(str, "-");
   
    // Keep printing tokens while one of the
    // delimiters present in str[].
    while (token != NULL)
    {
        printf("%s\n", token);
        token = strtok(NULL, "-");
    }
 
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code> Geeks
    for
    Geeks</code></pre>
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

#### ตัวอย่าง toString() ในภาษา C
```c
#include<stdio.h>

int main() {
  int num = 123;
  char str[5];
  sprintf(str, "%d", num); // integer to string
  printf("%s\n", str);
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>"123"</code></pre>
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

#### ตัวอย่าง toString() ในภาษา Python
 ```python
dict1 = {"first name": "Mickey", "last name": "Mouse"}
print(dict1)
print(str(dict1))
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>{'first name': 'Mickey', 'last name': 'Mouse'}
{'first name': 'Mickey', 'last name': 'Mouse'}</code></pre>
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

  #### ตัวอย่าง substring() ในภาษา C
```c
#include <stdio.h>
char* substring(char *destination, const char *source, int beg, int n)
{

    while (n > 0)
    {
        *destination = *(source + beg);
 
        destination++;
        source++;
        n--;
    }
 
    *destination = '\0';
 
    return destination;
}
 
int main()
{
    char source[] = "Techie Delight – Ace the Technical Interviews";
    char destination[25];
 
    int start = 7;
    int len = 7;
 
    substring(destination, source, start, len);
 
    printf("%s\n", destination);
 
    return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Delight
 </code></pre>
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

#### ตัวอย่าง reverse() ในภาษา C
```c
#include <stdio.h>  
#include <string.h>  
int main()  
{  
    char str[40]; // declare the size of character string  
    printf (" \n Enter a string to be reversed: ");  
    scanf ("%s", str);  
      
    // use strrev() function to reverse a string  
    printf (" \n After the reverse of a string: %s ", strrev(str));  
    return 0;  
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Enter a string to be reversed: AMBULANCE
 After the reverse of a string: ECNALUBMA</code></pre>
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

#### ตัวอย่างการใช้อักษรตัวแรกของ String ให้เป็นตัวพิมพ์ใหญ่ ในภาษา C
```c
#include<stdio.h>
#include<conio.h>
#include <ctype.h>
#include<string.h>
int main() 
{
  //Initializing variables
  char str[100] = "str ing";
  int length = 0;
  
  //Calculating length.
  length = strlen(str);
  for(int i=0;i<length;i++)
  {
      if(i==0||i==(length-1)) //Converting character at first and last index to uppercase.
      {
          str[i]=toupper(str[i]);
      }
      else if(str[i]==' ') //Converting characters present before and after space to uppercase.
      {
          str[i-1]=toupper(str[i-1]);
          str[i+1]=toupper(str[i+1]);
      }
  }
  
  //Printing result.
  printf("String after capitalizing first and last letter of each word:\n%s", str);
  return 0;
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>String after capitalizing first and last letter of each word:
StR InG</code></pre>
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
https://www.tutorialspoint.com/dart_programming/dart_programming_string.htm <br>
https://www.w3schools.com/python/python_ref_string.asp <br>
https://www.programiz.com/python-programming/methods/string <br>
https://www.programiz.com/java-programming/library/string <br>
https://www.delftstack.com/tags/c-string/ <br>

## Link Video

https://youtu.be/iPKQW0uKcbw?feature=shared

## Slide

[String In Dart (trim-end).pptx](https://github.com/soonklang/dart-tutorial/files/12884859/String.In.Dart.trim-end.pptx)<br>
[String In Dart (trim-end).pdf](https://github.com/soonklang/dart-tutorial/files/12884817/String.In.Dart.trim-end.pdf)
