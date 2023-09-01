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

int main(){
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
###### NOTE : จะเห็นได้ว่าเนื่องจากในภาษา C ไม่มีตัวแปรชนิด String จึงต้องทำการประกาศใช้เป็น อาเรย์ 2 มิติแทน

#### • Java
```Java
public class ArrayNameJava {
    public static void main(String[] args) {
        String[] names = {"Christopher Nolan","Denis Villeneuve",
                          "Francis Ford Coppola","James Cameron","Martin Scorsese",
                          "Quentin Tarantino","Ridley Scott","Stanley Kubrick",
                          "Steven Spielberg","Tim Burton"};

        for(int i=0;i<10;i++){
            System.out.println(names[i]);
        }
    }
}
```

#### • Python
```Python
namesList = ["Christopher Nolan","Denis Villeneuve",
         "Francis Ford Coppola","James Cameron",
         "Martin Scorsese","Quentin Tarantino",
         "Ridley Scott","Stanley Kubrick",
         "Steven Spielberg","Tim Burton"]
print(namesList)
```

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
หากซ้ำจะไม่มีการเก็บค่าเข้าไปใน Array
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
#### • Python
```Python
fruitsSet = {"apple", "banana", "cherry"}
for f in fruitsSet:
    print(f)
```

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
    print("Your maintenance expense : ${list_expense[0]}");
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
Your maintenance expense : 4500
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

#### • Java
```Java
```

#### • Python
```Python
```

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

int main(){
    
    char *days[7];
    days[0]="Sunday";
    days[1]="Monday";
    days[2]="Tueday";
    days[3]="Wednesday";
    days[4]="Thurday";
    days[5]="Friday";
    days[6]="Saturday";
    for(int i=0;i<7;i++){
        printf("%s\n", days[i]);
    }

    return 0;
}
```

#### • Java
```Java
```

#### • Python
```Python
```

### 5. เพิ่มชื่อเพื่อน 7 คนลงไปใน List ใช้ Where เพื่อหาชื่อเพื่อนที่ขึ้นต้นด้วยตัวอักษร a
###### Add your 7 friend names to the list. Use where to find a name that starts with alphabet a.

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

#### • Java
```Java
```

#### • Python
```Python
```

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
```

#### • Java
```Java
```

#### • Python
```Python
```

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
```

#### • Java
```Java
```

#### • Python
```Python
```

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
```

#### • Java
```Java
```

#### • Python
```Python
```

## อ้างอิง
>https://dart-tutorial.com/collections
>https://www.w3schools.com/java
>https://www.w3schools.com/python
