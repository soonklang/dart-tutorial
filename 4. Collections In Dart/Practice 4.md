# Practice 4

## แบบฝึกหัดบทที่ 4 : Collections In Dart

### 1. สร้าง List ของชื่อ และแสดงชื่อทั้งหมด โดยใช้ List
###### Create a list of names and print all names using list.

#### • Dart
```Dart
void main()
{  
   List<String> namesList = ["Christopher Nolan","Denis Villeneuve",
                         "Francis Ford Coppola","James Cameron",
                         "Martin Scorsese","Quentin Tarantino",
                         "Ridley Scott","Stanley Kubrick",
                         "Steven Spielberg","Tim Burton"];
   print(namesList);
 }
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Christopher Nolan, Denis Villeneuve, Francis Ford Coppola, James Cameron, Martin Scorsese, Quentin Tarantino, Ridley Scott, Stanley Kubrick, Steven Spielberg, Tim Burton]</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>

int main()
{
    char names[10][25] = {"Christopher Nolan","Denis Villeneuve",
                         "Francis Ford Coppola",
                         "James Cameron","Martin Scorsese",
                         "Quentin Tarantino","Ridley Scott",
                         "Stanley Kubrick",
                         "Steven Spielberg","Tim Burton"};
    printf("Show names in Array :\n");
    for(int i=0;i<10;i++){
        printf("%s\n", names[i]);
    }
    
    //สามารถเขียนได้อีกแบบคือเป็น Pointer ได้
    char *namesAsPointers[] = {"Christopher Nolan","Denis Villeneuve",
                         "Francis Ford Coppola",
                         "James Cameron","Martin Scorsese",
                         "Quentin Tarantino","Ridley Scott",
                         "Stanley Kubrick",
                         "Steven Spielberg","Tim Burton"};
    printf("Show names in Pointer Array :\n");
    for(int i=0;i<10;i++){
        printf("%s\n", namesAsPointers[i]);
    }

    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Show names in Array :
Christopher Nolan
Denis Villeneuve
Francis Ford Coppola
James Cameron
Martin Scorsese
Quentin Tarantino
Ridley Scott
Stanley Kubrick
Steven Spielberg
Tim Burton
Show names in Pointer Array :
Christopher Nolan
Denis Villeneuve
Francis Ford Coppola
James Cameron
Martin Scorsese
Quentin Tarantino
Ridley Scott
Stanley Kubrick
Steven Spielberg
Tim Burton</code>
</pre>
</details>
###### NOTE : จะเห็นได้ว่าเนื่องจากในภาษา C ไม่มีตัวแปรชนิด String จึงต้องทำการประกาศใช้เป็น อาเรย์ 2 มิติ หรือ Pointer แทน

#### • Java
```Java
import java.util.ArrayList;
import java.util.List;

public class ListNamesJava{
    public static void main(String[] args){
        List<String> names = new ArrayList<String>();
        names.add("Christopher Nolan");
        names.add("Denis Villeneuve");
        names.add("Francis Ford Coppola");
        names.add("James Cameron");
        names.add("Martin Scorsese");
        names.add("Quentin Tarantino");
        names.add("Ridley Scott");
        names.add("Stanley Kubrick");
        names.add("Steven Spielberg");
        names.add("Tim Burton");

        System.out.println(names);
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Christopher Nolan, Denis Villeneuve, Francis Ford Coppola, James Cameron, Martin Scorsese, Quentin Tarantino, Ridley Scott, Stanley Kubrick, Steven Spielberg, Tim Burton]</code>
</pre>
</details>

#### • Python
```Python
namesList = ["Christopher Nolan","Denis Villeneuve",
         "Francis Ford Coppola","James Cameron",
         "Martin Scorsese","Quentin Tarantino",
         "Ridley Scott","Stanley Kubrick",
         "Steven Spielberg","Tim Burton"]
print(namesList)
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>['Christopher Nolan', 'Denis Villeneuve', 'Francis Ford Coppola', 'James Cameron', 'Martin Scorsese', 'Quentin Tarantino', 'Ridley Scott', 'Stanley Kubrick', 'Steven Spielberg', 'Tim Burton']</code>
</pre>
</details>

### 2. สร้าง Set ของผลไม้ และแสดงผลทั้งหมด โดยใช้ Loop
###### Create a set of fruits and print all fruits using loop.

#### • Dart
```Dart
void main()
{
  Set<String> fruitsSet = {"Apple","Orange","Mango"};
  for(int i=0;i<3;i++){
    print(fruitsSet.elementAt(i));
  }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Apple
Orange
Mango</code>
</pre>
</details>

#### • C
```C
เนื่องจากในภาษา C ไม่มีฟังก์ชัน Set โดยตรง จึงอาจจะต้องมีการเขียนฟังก์ชันขึ้นมาเอง
โดยทุกครั้งที่มีการรับค่าใหม่เข้ามาใน Array จะมีการนำไปตรวจสอบว่ามีค่านั้นอยู่ภายใน Array หรือไม่
หากซ้ำจะไม่มีการเก็บค่าเข้าไปใน Array ซึ่งเป็นคุณสมบัติของ Set
```
#### • Java
```Java
import java.util.HashSet;

public class SetJava {
    public static void main(String[] args) {
        HashSet<String> fruits = new HashSet<String>();
        fruits.add("apple");
        fruits.add("banana");
        fruits.add("cherry");
        for (String i : fruits) {
            System.out.println(i);
        }
    }
}

```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>banana
apple 
cherry</code>
</pre>
</details>

#### • Python
```Python
fruitsSet = {"apple", "banana", "cherry"}
for f in fruitsSet:
    print(f)
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>banana
cherry
apple</code>
</pre>
</details>

### 3. สร้างโปรแกรมที่อ่าน List ของค่าใช้จ่าย โดยรับข้อมูลมาจากผู้ใช้ และแสดงผลรวมทั้งหมดออกมา
###### Create a program thats reads list of expenses amount using user input and print total.

#### • Dart
```Dart
import 'dart:io';
 
void main()
{
    List<int> list_expense = [];
    print("Enter rent expense : ");
    int? n1 = int.parse(stdin.readLineSync()!);
    list_expense.add(n1);

    print("Enter wage expense : ");
    int? n2 = int.parse(stdin.readLineSync()!);
    list_expense.add(n2);

    print("Enter maintenance expense : ");
    int? n3 = int.parse(stdin.readLineSync()!);
    list_expense.add(n3);

    print("Your rent expense : ${list_expense[0]}");
    print("Your wage expense : ${list_expense[1]}");
    print("Your maintenance expense : ${list_expense[2]}");
    int sum = list_expense.reduce((a, b) => a + b);
    print("Total expense : $sum");
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Enter rent expense : 
4500
Enter wage expense : 
15000
Enter maintenance expense : 
3650
Your rent expense : 4500
Your wage expense : 15000
Your maintenance expense : 3650
Total expense : 23150</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>

int main()
{
    int expense[3];
    printf("Enter rent expense : ");
    scanf("%d", &expense[0]);

    printf("Enter wage expense : ");
    scanf("%d", &expense[1]);

    printf("Enter maintenance expense : ");
    scanf("%d", &expense[2]);

    printf("Your rent expense : %d\n", expense[0]);
    printf("Your wage expense : %d\n", expense[1]);
    printf("Your maintenance expense : %d\n", expense[2]);
    int sum = 0;
    for(int i=0;i<3;i++){
        sum+=expense[i];
    }
    printf("Total expense : %d", sum);

    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Enter rent expense : 5400
Enter wage expense : 21000
Enter maintenance expense : 5320
Your rent expense : 5400
Your wage expense : 21000
Your maintenance expense : 5320
Total expense : 31720</code>
</pre>
</details>

#### • Java
```Java
import java.util.List;
import java.util.ArrayList;
import java.util.Scanner;

public class ListExpenseJava {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        List<Integer> list_expense = new ArrayList<Integer>();
        System.out.println("Enter rent expense : ");
        int n1 = scan.nextInt();
        list_expense.add(n1); 

        System.out.println("Enter wage expense : ");
        int n2 = scan.nextInt();
        list_expense.add(n2);

        System.out.println("Enter maintenance expense : ");
        int n3 = scan.nextInt();
        list_expense.add(n3);

        System.out.println("Your rent expense : "+list_expense.get(0).toString());
        System.out.println("Your wage expense : "+list_expense.get(1).toString());
        System.out.println("Your maintenance expense : "+list_expense.get(2).toString());
        int sum = 0;
        for(int i=0;i<3;i++){
            sum+=list_expense.get(i);
        }
        System.out.println("Total expense : "+sum);
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Enter rent expense : 
5500
Enter wage expense : 
18900
Enter maintenance expense : 
4360
Your rent expense : 5500       
Your wage expense : 18900      
Your maintenance expense : 4360
Total expense : 28760</code>
</pre>
</details>

#### • Python
```Python
list_expense = []
rent = input("Enter rent expense : ")
list_expense.append(int(rent))

wage = input("Enter wage expense : ")
list_expense.append(int(wage))

maintenance = input("Enter maintenance expense : ")
list_expense.append(int(maintenance))

print(f"Your rent expense : {list_expense[0]}")
print(f"Your wage expense : {list_expense[1]}")
print(f"Your maintenance expense : {list_expense[2]}")

summary = sum(list_expense)
print(f"Total expense : {summary}")
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Enter rent expense : 5000
Enter wage expense : 16700
Enter maintenance expense : 4590
Your rent expense : 5000
Your wage expense : 16700
Your maintenance expense : 4590
Total expense : 26290</code>
</pre>
</details>

### 4. สร้าง List ว่างชนิด String ให้มีชื่อว่า days ใช้เมทธอด add เพื่อเพิ่มชื่อของวัน 7 วันลงไป และแสดงผลวันทั้งหมด
###### Create an empty list of type string called days. Use the add method to add names of 7 days and print all days.

#### • Dart
```Dart
void main()
{
    List<String> days = [];
    days.add("Sunday");
    days.add("Monday");
    days.add("Tueday");
    days.add("Wednesday");
    days.add("Thurday");
    days.add("Friday");
    days.add("Saturday");

    print(days);
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Sunday, Monday, Tueday, Wednesday, Thurday, Friday, Saturday]</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>

void add(char *array_day[],int n,char *string_day)
{
    array_day[n]= string_day;
}

int main()
{
    char *days[7];
    add(days,0,"Sunday");
    add(days,1,"Monday");
    add(days,2,"Tueday");
    add(days,3,"Wednesday");
    add(days,4,"Thurday");
    add(days,5,"Friday");
    add(days,6,"Saturday");
    for(int i=0;i<7;i++){
        printf("%s\n", days[i]);
    }

    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Sunday
Monday
Tueday
Wednesday
Thurday
Friday
Saturday</code>
</pre>
</details>

#### • Java
```Java
import java.util.List;
import java.util.ArrayList;

public class ListDaysJava {
    public static void main(String[] args) {
        List<String> days = new ArrayList<String>();
        
        days.add("Sunday"); 
        days.add("Monday"); 
        days.add("Tueday"); 
        days.add("Wednesday"); 
        days.add("Thurday"); 
        days.add("Friday"); 
        days.add("Saturday"); 

        System.out.println(days);
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Sunday, Monday, Tueday, Wednesday, Thurday, Friday, Saturday]</code>
</pre>
</details>

#### • Python
```Python
list_days = []
list_days.append("Sunday")
list_days.append("Monday")
list_days.append("Tueday")
list_days.append("Wednesday")
list_days.append("Thurday")
list_days.append("Friday")
list_days.append("Saturday")

print(list_days)
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>['Sunday', 'Monday', 'Tueday', 'Wednesday', 'Thurday', 'Friday', 'Saturday']</code>
</pre>
</details>

### 5. เพิ่มชื่อเพื่อน 7 คนลงไปใน List ใช้ Where เพื่อหาชื่อเพื่อนที่ขึ้นต้นด้วยตัวอักษร A
###### Add your 7 friend names to the list. Use where to find a name that starts with alphabet A.

#### • Dart
```Dart
void main()
{
  List<String> friend_names = [];
  friend_names.add("Taksin Shin");
  friend_names.add("Abhisit Vej");
  friend_names.add("Adam Lev");
  friend_names.add("Chuan Leek");
  friend_names.add("Donald Trump");
  friend_names.add("Joe Biden");
  friend_names.add("Vladimir Putin");

  List<String> startWithA =
      friend_names.where((element) => element.startsWith("A")).toList();

  print(startWithA);
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Abhisit Vej, Adam Lev]</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>

int main()
{
  char friend_names[7][20] = {"Taksin Shin","Abhisit Vej","Adam Lev",
                              "Chuan Leek","Donald Trump","Joe Biden","Vladimir Putin"};

  for(int i=0;i<7;i++){
    if (friend_names[i][0]=='A')
    {
        printf("%s\n", friend_names[i]);
    }
  }

  return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Abhisit Vej
Adam Lev</code>
</pre>
</details>

#### • Java
```Java
import java.util.List;
import java.util.ArrayList;

public class ListWhereJava {
    public static void main(String[] args) {
        List<String> friend_names = new ArrayList<String>();
        friend_names.add("Taksin Shin");
        friend_names.add("Abhisit Vej");
        friend_names.add("Adam Lev");
        friend_names.add("Chuan Leek");
        friend_names.add("Donald Trump");
        friend_names.add("Joe Biden");
        friend_names.add("Vladimir Putin");
        List<String> names = new ArrayList<String>();
        for(int i=0;i<friend_names.size();i++){
            char first_letter = friend_names.get(i).charAt(0);
            if(first_letter=='A'){
                names.add(friend_names.get(i));
            }
        }
        System.out.println(names.toString());
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>[Abhisit Vej, Adam Lev]</code>
</pre>
</details>

#### • Python
```Python
friend_names = []
add_names = ["Taksin Shin","Abhisit Vej","Adam Lev","Chuan Leek",
                    "Donald Trump","Joe Biden","Vladimir Putin"]
friend_names.extend(add_names)
for name in friend_names:
    if(name[0]=='A'): 
        print(name)
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Abhisit Vej
Adam Lev</code>
</pre>
</details>

### 6. สร้าง Map ด้วย name, address, age, country เป็น keys และป้อนค่าเก็บไว้ อัพเดทชื่อประเทศลงบน country และแสดงผล Keys กับค่าทั้งหมด
###### Create a map with name, address, age, country keys and store values to it. Update country name to other country and print all keys and values.

#### • Dart
```Dart
void main()
{
  Map<String, dynamic> map_citizen = {
    'name': 'Sherlock Holmes',
    'address': '221B Baker Street',
    'age': '35',
    'country': 'USA'
  };
  print("Before : $map_citizen");
  map_citizen.update('country', (value) => 'England');
  print("All keys of Map: ${map_citizen.keys}");
  print("All values of Map: ${map_citizen.values}");
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Before : {name: Sherlock Holmes, address: 221B Baker Street, age: 35, country: USA}
All keys of Map: (name, address, age, country)
All values of Map: (Sherlock Holmes, 221B Baker Street, 35, England)</code>
</pre>
</details>

#### • C
```C
#include <stdio.h>

void update(char *keyOrValue[],int i,char *data)
{
    keyOrValue[i] = data;
}

int main() 
{
	char *keys[] = {"name", "address", "age", "country"};
	char *values[] = {"Sherlock Holmes", "221B Baker Street", "35", "USA"};

   printf("Before :\n");
	for (int i = 0; i < sizeof(keys)/sizeof(keys[0]); i++) {
		printf("%s: %s\n", keys[i], values[i]);
	}

   update(values,3,"England");
   printf("%s\n", values[3]);
   printf("After :\n");
   for (int i = 0; i < sizeof(keys)/sizeof(keys[0]); i++) {
		printf("%s: %s\n", keys[i], values[i]);
   }

	return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Before :
name: Sherlock Holmes     
address: 221B Baker Street
age: 35
country: USA
England
After :
name: Sherlock Holmes     
address: 221B Baker Street
age: 35
country: England</code>
</pre>
</details>

#### • Java
```Java
import java.util.HashMap;
import java.util.Map;

public class MapCountryJava {

    public static void main(String[] args) {
        Map<String,String> country_map = new HashMap<>();
        country_map.put("name", "Sherlock Holmes");
        country_map.put("address", "221B Baker Street");
        country_map.put("age", "35");
        country_map.put("country", "USA");
        System.out.println("Before : "+country_map);

        country_map.computeIfPresent("country", (k,v) -> v="England");
        System.out.println("After : "+country_map);
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Before : {country=USA, address=221B Baker Street, name=Sherlock Holmes, age=35}
After : {country=England, address=221B Baker Street, name=Sherlock Holmes, age=35}</code>
</pre>
</details>

#### • Python
```Python
dict_country = {
    "name": "Sherlock Holmes",
    "address": "221B Baker Street",
    "age": 35, 
    "country": "USA"
}
print(f"Before : {dict_country}")

dict_country.update({"country": "England"})
print(f"After : {dict_country}")
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Before : {'name': 'Sherlock Holmes', 'address': '221B Baker Street', 'age': 35, 'country': 'USA'}
After : {'name': 'Sherlock Holmes', 'address': '221B Baker Street', 'age': 35, 'country': 'England'}</code>
</pre>
</details>

### 7. สร้าง Map ด้วย name, phone เป็น keys และทำการป้อนค่าไว้ ใช้ Where เพื่อหา keys ทั้งหมดที่มีความยาว 4 
###### Create a map with name, phone keys and store some values to it. Use where to find all keys that have length 4.

#### • Dart
```Dart
void main()
{
  Map<String, dynamic> map_citizen = {
    'name': 'Albus Dumbledore',
    'phone': '+44 7911 123456',
    //ขอเพิ่มเติม keys จากโจทย์เพื่อให้เห็นภาพมากขึ้น ให้มี keys ที่มี 4 มากกว่า 1 ค่า
    'date': '13/03/1895',
    'address': 'England',
  };

  print(map_citizen.keys.where((e) => e.length==4));
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>(name, date)</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>

int string_length(char str[])
{
    int count;
    for(count=0;str[count]!='\0';count++);
    return count;
}

int main()
{
    char *keys[] = {"name", "phone", "date", "address"};
	char *values[] = {"Albus Dumbledore", "+44 7911 123456", "13/03/1895", "England"};

    for(int i=0;i<sizeof(keys)/sizeof(keys[0]);i++){
        int length = string_length(keys[i]);
        if(length==4){
            printf("%s\n", keys[i]);
        }
    }

    return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>name
date</code>
</pre>
</details>

#### • Java
```Java
import java.util.HashMap;
import java.util.Map;

public class MapKey4Java {
    public static void main(String[] args) {
        Map<String,String> map_citizen = new HashMap<>();
        map_citizen.put("name", "Albus Dumbledore");
        map_citizen.put("phone", "+44 7911 123456");
        map_citizen.put("date", "13/03/1895");
        map_citizen.put("address", "England");
        for(String key: map_citizen.keySet()){
            if(key.length()==4)
                System.out.println(key);
        }
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>date
name</code>
</pre>
</details>

#### • Python
```Python
dict_citizen = {
    'name': 'Albus Dumbledore',
    'phone': '+44 7911 123456',
    'date': '13/03/1895',
    'address': 'England',
}
for k in dict_citizen.keys():
    if(len(k)==4): 
        print(k)
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>name
date</code>
</pre>
</details>

### 8. สร้าง simple to-do แอพพลิเคชั่น ที่อนุญาตให้ผู้ใช้ add, remove และ view task ได้
###### Create a simple to-do application that allows user to add, remove, and view their task.

#### • Dart
```Dart
import 'dart:io';

void main() {
  print("Welcome to To-Do List \nChoose you want to do..");
  List<String?> toDoList = [];
  while (true) {
    print("Press 1 : add To-Do List \nPress 2 : remove To-Do List \nPress 3 : view task");
    print("Press other button to exit");
    int? n = int.parse(stdin.readLineSync()!);
    if (n == 1) {
      print("add task : ");
      String? task = stdin.readLineSync();
      toDoList.add(task);
    } else if (n == 2) {
      print("remove task : ");
      String? taskRemove = stdin.readLineSync();
      toDoList.removeWhere((element) => element==taskRemove);
    } else if (n == 3) {
      print(toDoList);
    } else{
      break;
    }
  }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to To-Do List  
Choose you want to do..
Press 1 : add To-Do List    
Press 2 : remove To-Do List 
Press 3 : view task
Press other button to exit  
1
add task : 
work
Press 1 : add To-Do List    
Press 2 : remove To-Do List 
Press 3 : view task
Press other button to exit  
1
add task : 
eat
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
1    
add task : 
sleep
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
1
add task : 
wake up
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
3
[work, eat, sleep, wake up]
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
2
remove task : 
work
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
3
[eat, sleep, wake up]
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other button to exit
5</code>
</pre>
</details>

#### • C
```C
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

void choice_massage()
{
    printf("Choose you want to do..\n");
    printf("Press 1 : add To-Do List\n");
    printf("Press 2 : remove To-Do List\n");
    printf("Press 3 : view task\n");
    printf("Press other number to exit\n");
}

int main()
{
    char *to_do_list[20];
    printf("Welcome to To-Do List \n");
    int count_list=0;
    
    while (1)
    {
        choice_massage();
        int choose;
        scanf("%d", &choose);
        if (choose == 1)
        {
            char task[30];
            printf("add task : ");
            scanf("%30s", task);
            to_do_list[count_list] = malloc(strlen(task) + 1);
            strcpy(to_do_list[count_list], task);
            count_list++;          
        }
        else if (choose == 2)
        {
            char delete[30];
            printf("remove task : ");
            scanf("%30s", delete);
            for(int i=0;i<count_list;i++){
                if (strcmp(to_do_list[i],delete)==0)
                {
                    for (int j=i;j<count_list;j++)
                    {
                        strcpy(to_do_list[j], to_do_list[j+1]);
                    }
                    continue; 
                }
            }
            count_list--;
        }
        
        else if(choose == 3){
            printf("view task :\n");
            for(int i=0;i<count_list;i++){
                printf("%s\n", to_do_list[i]);
            }
        }
        else
        {
            break;
        }
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>
Welcome to To-Do List 
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : work
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : run
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : swim
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task :
work
run
swim
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
2
remove task : work
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task :
run
swim
Choose you want to do..
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
</code>
</pre>
</details>

#### • Java
```Java
import java.util.List;
import java.util.ArrayList;
import java.util.Scanner;

public class SimpleToDoListJava {
    public static void main(String[] args) {
        System.out.println("Welcome to To-Do List");
        System.out.println("Choose you want to do..");

        List<String> toDoListTask = new ArrayList<String>();
        Scanner scan = new Scanner(System.in);

        while(true){
            System.out.println("Press 1 : add To-Do List");
            System.out.println("Press 2 : remove To-Do List");
            System.out.println("Press 3 : view task");
            System.out.println("Press other number to exit");
            
            int choose = scan.nextInt();
            
            if(choose == 1){
                System.out.print("add task : ");
                String add_task = scan.next();
                toDoListTask.add(add_task.toString());
            }
            else if(choose == 2){
                System.out.println("remove task : ");
                String remove_task = scan.next();
                toDoListTask.remove(remove_task);
            }
            else if(choose == 3){
                System.out.println("view task : "+toDoListTask);
            }
            else {
                break;
            }
        }
    }
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to To-Do List
Choose you want to do..
Press 1 : add To-Do List   
Press 2 : remove To-Do List
Press 3 : view task        
Press other number to exit 
1
add task : work
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : eat
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : shop 
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : run
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task : [work, eat, shop, run]
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
2
remove task : 
eat
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task : [work, shop, run]
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
</code>
</pre>
</details>

#### • Python
```Python
print("Welcome to To-Do List \nChoose you want to do..")
toDoListTask = []
while True:
    print("Press 1 : add To-Do List \nPress 2 : remove To-Do List \nPress 3 : view task")
    print("Press other number to exit")
    choose = input()
    if int(choose) == 1:
        add_task = input("add task : ")
        toDoListTask.append(add_task)
    elif int(choose) == 2:
        remove_task = input("remove task : ")
        toDoListTask.remove(remove_task)
    elif int(choose) == 3:
        print(f"view task : {toDoListTask}")
    else :
        break
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Welcome to To-Do List  
Choose you want to do..
Press 1 : add To-Do List    
Press 2 : remove To-Do List 
Press 3 : view task
Press other number to exit  
1
add task : work
Press 1 : add To-Do List    
Press 2 : remove To-Do List 
Press 3 : view task
Press other number to exit  
1
add task : eat
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
1
add task : run
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task : ['work', 'eat', 'run']
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
2
remove task : work
Press 1 : add To-Do List 
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit
3
view task : ['eat', 'run']
Press 1 : add To-Do List
Press 2 : remove To-Do List
Press 3 : view task
Press other number to exit</code>
</pre>
</details>

## อ้างอิง
>https://dart-tutorial.com/collections/
>https://www.w3schools.com/java/
>https://www.w3schools.com/python/
>https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/
>https://www.scaler.com/topics/string-length-in-c/
>https://stackoverflow.com/questions/29568297/c-how-to-store-multiple-strings-in-an-array/
>http://zerocontroller.blogspot.com/2017/05/c.html

## VDO
>https://www.youtube.com/watch?v=SeFhrsoDRbM

## Slide
[Programming-LanguagePresentation-Practice-4-Collections-In-Dart.pptx](https://github.com/soonklang/dart-tutorial/files/12883324/Programming-LanguagePresentation-Practice-4-Collections-In-Dart.pptx)

## นายธนวัต ศิลป์สะอาด 630710654
