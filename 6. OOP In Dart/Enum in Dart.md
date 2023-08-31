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
 * รูปแบบในการใช้ ของ Enum ในภาษา Java 

 * รูปแบบในการใช้ ของ Enum ในภาษา C

 * รูปแบบในการใช้ ของ Enum ในภาษา Python


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

## วิธี Print ค่าทั้งหมดที่อยู่ใน Enum


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

## อ้างอิง
https://dart-tutorial.com/introduction-and-basics/   
https://www.geeksforgeeks.org/enum-in-java/
