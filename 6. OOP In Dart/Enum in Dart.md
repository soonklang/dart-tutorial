# Enum in Dart

Enum  คือ type ประเภทหนึ่ง เหมือนกับ class ใช้สำหรับกำหนดค่า constant values ที่เรารู้หรือจะเป็นค่า status ต่างๆที่เรารู้อยู่ก่อนแล้วก็ได้  เมื่อเรารู้ค่าล่วงหน้าอยู่แล้ว ว่า values ของเรามีอะไรบ้าง เราก็กำหนดมันเข้าไปได้ตั้งแต่ต้นเลย  พูดง่ายๆคือกำหนดค่าไว้ใช้งาน ซึ่งเป็นการกำหนดไว้ล่วงหน้า ประโยชน์ของมันคือ ทำให้ code เราอ่านง่ายและเข้าใจได้ทัน


## Syntax Of Enum In Dart
```dart
enum enumName {
  constantName1,
  constantName2,
  constantName3,
  ...
  constantNameN
}
```
## ยกตัวอย่างการใช้ Syntax Of Enum In Dart
```dart
enum cars {  
  Toyota,
  Honda,
  Nissan,
  Ferrari,
  Bugatti,
  Benz,
  Volvo
}

```
## การเปรียบเทียบ รูปแบบการใช้งาน กับ ภาษาอื่น ๆ
 * ### รูปแบบในการใช้ ของ Enum ในภาษา Java และความแตกต่าง กับภาษา Dart
	* จะเห็นได้ว่า ความแตกต่างจาก Dart คือ java จะต้องประกาศ Enum ในคลาสเท่านั้น ส่วน รูปแบบมีลักษณะที่เหมือนกัน
```java
  class Car {
    // Enum Declared
   enum cars {  
        Toyota,
        Honda,
        Nissan,
        Ferrari,
        Bugatti,
        Benz,
        Volvo;
}
```
 * ### รูปแบบในการใช้ ของ Enum ในภาษา C    และความแตกต่าง กับภาษา Dart
	* มีรูปแบบที่คล้ายกัน
```c
 enum cars {
    Toyota,
    Honda,
    Nissan,
    Ferrari,
    Bugatti,
    Benz,
    Volvo
};
```
 * ### รูปแบบในการใช้ ของ Enum ในภาษา Python และความแตกต่าง กับภาษา Dart
   * การสร้าง Enum ใน Python ใช้ Enum class ภายใน enum module
   * ค่าใน Enum จะถูกกำหนดโดยค่าเริ่มต้นที่เป็นเลขจำนวนเต็มตั้งแต่ 1 เรื่อย ๆ ถ้าเราไม่ได้กำหนดค่าให้เอง
   ```python
   from enum import Enum
 
   class Season(Enum):
    SPRING = 1
    SUMMER = 2
    AUTUMN = 3
    WINTER = 4
   ```


## ตัวอย่างการใช้ Enum ใน Dart
```dart
enum cars {
  Toyota,
  Honda,
  Nissan,
  Ferrari,
  Bugatti,
  Benz,
  Volvo
}

void main() {
  var Mycartoday = cars.Volvo;
  switch (Mycartoday) {
    case cars.Toyota:
      print("Today I choose Toyota.");
      break;
    case cars.Honda:
      print("Today I choose Honda.");
      break;
    case cars.Nissan:
      print("Today I choose Nissan.");
      break;
    case cars.Ferrari:
      print("Today I choose Ferrari.");
      break;
    case cars.Bugatti:
      print("Today I choose Bugatti.");
      break;
    case cars.Benz:
      print("Today I choose Benz.");
      break;
    case cars.Volvo:
      print("Today I choose Volvo.");
      break;
  }
}
```

Output  
```
Today I choose Volvo.
```

## ตัวอย่างการใช้ Enum ใน Java
```java
 class Car {
    // Enum Declared
   enum cars {  
        Toyota,
        Honda,
        Nissan,
        Ferrari,
        Bugatti,
        Benz,
        Volvo;
}
 
    // Main Function
    public static void main(String[] args)
    {
          cars Mycartoday = cars.Volvo;
       
          // Switch case with Enum
    switch (Mycartoday) {
    case Toyota:
      System.out.println("Today I choose Toyota.");
      break;
    case Honda:
     System.out.println("Today I choose Honda.");
      break;
    case Nissan:
     System.out.println("Today I choose Nissan.");
      break;
    case Ferrari:
      System.out.println("Today I choose Ferrari.");
      break;
    case Bugatti:
    System.out.println("Today I choose Bugatti.");
      break;
    case Benz:
       System.out.println("Today I choose Benz.");
      break;
    case Volvo:
       System.out.println("Today I choose Volvo.");
      break;
      default:
			System.out.println("Not my cars");
  }
    }
}
```

Output  
```
Today I choose Volvo.
```

## ตัวอย่างการใช้ Enum ใน C
```c
 #include <stdio.h>

// Enum Declared
enum cars {
    Toyota,
    Honda,
    Nissan,
    Ferrari,
    Bugatti,
    Benz,
    Volvo
};

int main() {
    enum cars Mycartoday = Volvo;
    
    // Switch case with Enum
    switch (Mycartoday) {
        case Toyota:
            printf("Today I choose Toyota.\n");
            break;
        case Honda:
            printf("Today I choose Honda.\n");
            break;
        case Nissan:
            printf("Today I choose Nissan.\n");
            break;
        case Ferrari:
            printf("Today I choose Ferrari.\n");
            break;
        case Bugatti:
            printf("Today I choose Bugatti.\n");
            break;
        case Benz:
            printf("Today I choose Benz.\n");
            break;
        case Volvo:
            printf("Today I choose Volvo.\n");
            break;
        default:
            printf("Not my cars\n");
    }

    return 0;
}
```

Output  
```
Today I choose Volvo.
```

## ตัวอย่างการใช้ Enum ใน Python
```python
from enum import Enum

class Cars(Enum):
    Toyota = 1
    Honda = 2
    Nissan = 3
    Ferrari = 4
    Bugatti = 5
    Benz = 6
    Volvo = 7

def main():
    Mycartoday = Cars.Volvo
    
    if Mycartoday == Cars.Toyota:
        print("Today I choose Toyota.")
    elif Mycartoday == Cars.Honda:
        print("Today I choose Honda.")
    elif Mycartoday == Cars.Nissan:
        print("Today I choose Nissan.")
    elif Mycartoday == Cars.Ferrari:
        print("Today I choose Ferrari.")
    elif Mycartoday == Cars.Bugatti:
        print("Today I choose Bugatti.")
    elif Mycartoday == Cars.Benz:
        print("Today I choose Benz.")
    elif Mycartoday == Cars.Volvo:
        print("Today I choose Volvo.")
    else:
        print("Not my cars")

if __name__ == "__main__":
    main()
```

Output  
```
Today I choose Volvo.
```

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum ในภาษา Dart


```dart
enum Colors { Green, Red, Blue, Yellow, Pink, Black, Rainbow }

void main() {
 // Colors.values: จะคืนค่าทั้งหมดที่อยู่ใน Enum(Colors).
  for (Colors color in Colors.values) {
    print(color);
  }
}

```
Output  
```
Colors.Green
Colors.Red
Colors.Blue
Colors.Yellow
Colors.Pink
Colors.Black
Colors.Rainbow
```

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum ในภาษา Java


```java
import java.io.*;
 
// Enum Declared
enum Color {
    Green,
    Red,
    Blue,
    Yellow,
    Pink,
    Black,
    Rainbow;
}
 
// Driver Class
 class GFG {
 
    // Main Function
    public static void main(String[] args)
    {
        // Iterating over all the values in
        // enum using for loop
        for (Color col : Color.values()) {
            System.out.println(col);
        }
    }
}
}
```
Output  
```
Green
Red
Blue
Yellow
Pink
Black
Rainbow

```

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum ในภาษา C
* จะเห็นได้ชัดว่า ภาษาอื่นๆ ทั้งDart Java และ Python มีท่าการเรียก วัน ต่างๆที่คล้ายกันมาก ด้วย Color.value() แต่ใน C นั้นไม่สามารถทำได้เราจึงสร้างโค้ดที่กำหนดตัวแปร colorNames เป็นอาร์เรย์ของ pointer ไปยัง char (const char *) เป็นการสร้างอาร์เรย์ของสตริง  ที่เก็บชื่อสีต่าง ๆ ภายใน enum Colors. อาร์เรย์นี้สร้างขึ้นเพื่อเป็นการแมปค่าของสีใน enum กับชื่อของสีที่เราต้องการให้เป็นผลลัพธ์เมื่อทำการพิมพ์ชื่อสีออกทางของโปรแกรม เพื่อเพิ่มความความยืดหยุ่นในการแก้ไขหรือเปลี่ยนแปลงชื่อสีในอนาคต โดยไม่ต้องแก้ไขโค้ดในส่วนอื่น ๆ ของโปรแกรมที่อาจจะใช้ชื่อสีเหล่านี้  ซึ่งจะทำให้เราสามารถเข้าถึงชื่อสีด้วยตำแหน่งที่เป็นตัวแปรใน enum ได้, คือ colorNames[Green] จะได้ "Green", colorNames[Red] จะได้ "Red", และเช่นไปเรื่อย ๆ ตามลำดับของ enum Colors.
```c
#include <stdio.h>

enum Colors { Green, Red, Blue, Yellow, Pink, Black, Rainbow };

int main() {
    const char *colorNames[] = {
        "Green", "Red", "Blue", "Yellow", "Pink", "Black", "Rainbow"
    };
    
    for (int color = Green; color <= Rainbow; color++) {
        printf("%s\n", colorNames[color]);
    }

    return 0;
}

```
Output  
```
Green
Red
Blue
Yellow
Pink
Black
Rainbow
```

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum ในภาษา Python


```python
from enum import Enum
 
class Color(Enum):
    Green =1 
    Red=2 
    Blue =3 
    Yellow=4 
    Pink=4 
    Black=5 
    Rainbow=6
 
for color in (Color):
    print(color.value,"-",color)

```
Output  
```
1 - Color.Green
2 - Color.Red
3 - Color.Blue
4 - Color.Yellow
5 - Color.Black
6 - Color.Rainbow
```

## link video
https://www.youtube.com/watch?v=Ik26T96waPE

## link slide
https://drive.google.com/file/d/1whcD2uMeb9mJV4Oh-Bbpr4E1WDIYo6Cc/view?usp=drive_link

## อ้างอิง
https://dart-tutorial.com/introduction-and-basics/   
https://www.geeksforgeeks.org/enum-in-java/
