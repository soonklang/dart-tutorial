# Practice 6
## เเบบฝึกหัด เรี่อง Object-oriented programming (OOP) In Dart
--------------------------------------------------------------------------------
## 1.Write a dart program to create a class Laptop with properties [id, name, ram] and create 3 objects of it and print all details.
### - Dart
 ```dart
class Laptop {
  int? id;
  String? name;
  int? ram;

  void printDetails() {
    print('Laptop ID: $id');
    print('Laptop Name: $name');
    print('Laptop RAM: $ram');
    print("");
    
  }
}

void main() {
  // สร้าง 3 objects ของ Class Laptop
  Laptop Asus = Laptop();
  Laptop Lenovo = Laptop();
  Laptop Acer = Laptop();

  // Set the properties ของ Laptop objects
  Asus.id = 1;
  Asus.name = 'Asus';
  Asus.ram = 8;

  Lenovo.id = 2;
  Lenovo.name = 'Lenovo';
  Lenovo.ram = 16;

  Acer.id = 3;
  Acer.name = 'Acer';
  Acer.ram = 32;

  // Print the details.
  Asus.printDetails();
  Lenovo.printDetails();
  Acer.printDetails();
}

   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Laptop ID: 1
Laptop Name: Asus
Laptop RAM: 8
</n>
Laptop ID: 2
Laptop Name: Lenovo
Laptop RAM: 16
</n>
Laptop ID: 2
Laptop Name: Acer
Laptop RAM: 32</code>
</pre>
</details>

### - Java
```java
class Laptop {
    public int id;
    public String name;
    public int ram;


    public void printDetails() {
        System.out.println("Laptop ID: " + id);
        System.out.println("Laptop Name: " + name);
        System.out.println("Laptop RAM: " + ram);
        System.out.println("");
    }
}

public class Main {
    public static void main(String[] args) {
        Laptop Asus = new Laptop();
        Laptop Lenovo = new Laptop();
        Laptop Acer = new Laptop();

        Asus.id = 1;
        Asus.name = "Asus";
        Asus.ram = 8;

        Lenovo.id = 2;
        Lenovo.name = "Lenovo";
        Lenovo.ram = 16;

        Acer.id = 3;
        Acer.name = "Acer";
        Acer.ram = 32;

        Asus.printDetails();
        Lenovo.printDetails();
        Acer.printDetails();
    }
}


   ```
## 2.Write a dart program to create a class House with properties [id, name, prize]. Create a constructor of it and create 3 objects of it. Add them to the list and print all details.
### - Dart
 ```dart
class House {
  int id;
  String name;
  double price;

  House(this.id, this.name, this.price);
}

void main() {
  // สร้าง list
  List<House> house = [];

  House house_1 = House(1, "House A", 200000.0);
  House house_2 = House(2, "House B", 300000.0);
  House house_3 = House(3, "House C", 400000.0);
  // Add them
  house.add(house_1);
  house.add(house_2);
  house.add(house_3);

  for (House house in house) {
    print("House ID: ${house.id}");
    print("House Name: ${house.name}");
    print("House Price: ${house.price}");
    print("");
  }
}

   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>House ID: 1
House Name: House A
House Price: 200000.0
</n>
House ID: 2
House Name: House B
House Price: 300000.0
</n>
House ID: 3
House Name: House C
House Price: 400000.0</code>
</pre>
</details>

### - Java
```java
import java.util.ArrayList;
class House {
    int id;
    String name;
    double price;

    House(int id, String name, double price) {
        this.id = id;
        this.name = name;
        this.price = price;
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<House> houses = new ArrayList<House>();

        House house_1 = new House(1, "House A", 200000.0);
        House house_2 = new House(2, "House B", 300000.0);
        House house_3 = new House(3, "House C", 400000.0);

        houses.add(house_1);
        houses.add(house_2);
        houses.add(house_3);
        
        for (House house : houses) {
            System.out.println("House ID: " + house.id);
            System.out.println("House Name: " + house.name);
            System.out.println("House Price: " + house.price);
            System.out.println("");
        }
    }
}


   ```

## 3.Write a dart program to create an enum class for gender [male, female, others] and print all values.
### - Dart
 ```dart
// Create enum
enum Gender { male, female, others }

void main() {
  // Print all values
  for (Gender gender in Gender.values) {
    print(gender);
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Gender.male
Gender.female
Gender.others</code>
</pre>
</details>

### - C
```c
#include <stdio.h>

// Create enum
enum Gender {
    male,
    female,
    others
};

int main() {
    // Print all values
    for (enum Gender gender = male; gender <= others; gender++) {
        switch (gender) {
            case male:
                printf("male\n");
                break;
            case female:
                printf("female\n");
                break;
            case others:
                printf("others\n");
                break;
        }
    }

    return 0;
}

   ```
### - Java
```java
// Create enum
enum Gender {
  male,
  female,
  others
}

public class Main { 
  public static void main(String[] args) {
    // Print All values
    for (Gender gender : Gender.values()) {
      System.out.println(gender);
    }
  } 
}


   ```

## 4.Write a dart program to create a class Animal with properties [id, name, color]. Create another class called Cat and extends it from Animal. Add new properties sound in String. Create an object of a Cat and print all details.
### - Dart
 ```dart
class Animal {
  int id;
  String name;
  String color;

  Animal(this.id, this.name, this.color);
}
// Class Cat extends Class Animal เเละ เพื่ม String Sound
class Cat extends Animal {
  String sound;

  Cat(int id, String name, String color, this.sound) : super(id, name, color);

  void printDetails() {
   print('Cat ID: $id');
   print('Cat Name: $name');
   print('Cat Color: $color');
   print('Cat sound: $sound');
   print("");
  }
}

void main() {
  Cat cat = Cat(1, "mali", "Gray", "Meow");

  cat.printDetails();
}

   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Cat ID: 1
Cat Name: mali
Cat Color: Gray
Cat sound: Meow</code>
</pre>
</details>

### - Java
```java
class Animal {
    int id;
    String name;
    String color;

    Animal(int id, String name, String color) {
        this.id = id;
        this.name = name;
        this.color = color;
    }
}

class Cat extends Animal {
    String sound;

    Cat(int id, String name, String color, String sound) {
        super(id, name, color);
        this.sound = sound;
    }
}

public class Main {
    public static void main(String[] args) {
        Cat cat = new Cat(1, "mali", "Gray", "Meow");

        System.out.println("Cat ID: " + cat.id);
        System.out.println("Cat Name: " + cat.name);
        System.out.println("Cat Color: " + cat.color);
        System.out.println("Cat Sound: " + cat.sound);
    }
}

   ```

## 5.Write a dart program to create a class Camera with private properties [id, brand, color, prize]. Create a getter and setter to get and set values. Also, create 3 objects of it and print all details.
### - Dart
 ```dart
class Camera {
 int? _id;
 String? _brand;
 String? _color;
 double? _price;

 // สร้าง getter and setter to get and set values
 int get id => this._id!;
 String get brand => this._brand!;
 String get color => this._color!;
 double get price => this._price!;

 set id(int value) => this._id = value;

 set brand(String value) => this._brand = value;

 set color(String value) => this._color = value;

 set price(double value) => this._price = value;
}

void main() {
 Camera camera1 = new Camera();
 Camera camera2 = new Camera();
 Camera camera3 = new Camera();
  camera1.id = 1;
  camera2.id = 2;
  camera3.id = 3;
  camera1.brand = "Canon";
  camera2.brand = "Sony";
  camera3.brand = "Nikon";
  camera1.color = "Black";
  camera2.color = "While";
  camera3.color = "Silver";
  camera1.price = 500.0;
  camera2.price = 600.0;
  camera3.price = 700.0;

 print("Camera 1 - ID: ${camera1.id}, Brand: ${camera1.brand}, Color: ${camera1.color}, Price: ${camera1.price}");
 print("Camera 2 - ID: ${camera2.id}, Brand: ${camera2.brand}, Color: ${camera2.color}, Price: ${camera2.price}");
 print("Camera 3 - ID: ${camera3.id}, Brand: ${camera3.brand}, Color: ${camera3.color}, Price: ${camera3.price}");
  }
   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Camera 1 - ID: 1, Brand: Canon, Color: Black, Price: 500
Camera 2 - ID: 2, Brand: Sony, Color: While, Price: 600
Camera 3 - ID: 3, Brand: Nikon, Color: Silver, Price: 700</code>
</pre>
</details>

### - Java
```java
class Camera {
    private int id;
    private String brand;
    private String color;
    private double price;

    // Getter and setter
    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }
}

public class Main {
    public static void main(String[] args) {
        Camera camera1 = new Camera();
        Camera camera2 = new Camera();
        Camera camera3 = new Camera();
        camera1.setId(1);
        camera2.setId(2);
        camera3.setId(3);
        camera1.setBrand("Canon");
        camera2.setBrand("Sony");
        camera3.setBrand("Nikon");
        camera1.setColor("Black");
        camera2.setColor("White");
        camera3.setColor("Silver");
        camera1.setPrice(500.0);
        camera2.setPrice(600.0);
        camera3.setPrice(700.0);
        System.out.println("Camera 1 - ID: " + camera1.getId() + ", Brand: " + camera1.getBrand() +
                ", Color: " + camera1.getColor() + ", Price: " + camera1.getPrice());
        System.out.println("Camera 2 - ID: " + camera2.getId() + ", Brand: " + camera2.getBrand() +
                ", Color: " + camera2.getColor() + ", Price: " + camera2.getPrice());
        System.out.println("Camera 3 - ID: " + camera3.getId() + ", Brand: " + camera3.getBrand() +
                ", Color: " + camera3.getColor() + ", Price: " + camera3.getPrice());
    }
}



   ```

## 6.Create an interface called Bottle and add a method to it called open(). Create a class called CokeBottle and implement the Bottle and print the message “Coke bottle is opened”. Add a factory constructor to Bottle and return the object of CokeBottle. Instantiate CokeBottle using the factory constructor and call the open() on the object.
### - Dart
 ```dart
// สร้าง interface bottle
abstract class Bottle {
 void open();

 //สร้าง factory constructor ที่ return CokeBottle
 factory Bottle.bottle() {
   return CokeBottle();
 }
}

// สร้าง Class CokeBottle implements Bottle
class CokeBottle implements Bottle {
 @override
 void open() {
   print("Coke bottle is opened");
 }
}

void main() {
 final cokeBottle = Bottle.bottle();
 cokeBottle.open();
}


   ```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Coke bottle is opened</code>
</pre>
</details>

### - Java
```java
interface Bottle {
     void open();

    public static Bottle bottle() {
        return new CokeBottle();
    }
}

class CokeBottle implements Bottle {
    @Override
    public void open() {
        System.out.println("Coke bottle is opened");
    }
}

public class Main {
    public static void main(String[] args) {
        Bottle cokeBottle = Bottle.bottle();
        cokeBottle.open();
    }
}

   ```

## 7.Create a simple quiz application using oop that allows users to play and view their score.
### - Dart
 ```dart
import 'dart:io';

class Question {
 String text;
 List<String> options;
 int correctOption;

 Question(this.text, this.options, this.correctOption);
}

class Quiz {
 List<Question> questions = [];
 int score = 0;

 void addQuestion(String text, List<String> options, int correctOption) {
   Question question = Question(text, options, correctOption);
   questions.add(question);
 }

 void startQuiz() {
   for (var question in questions) {
     print(question.text);
     String ans = "";
     for (var i = 0; i < question.options.length; i++) {
       if(i+1 == question.correctOption){
         ans = question.options[i];
       }
       print("${i + 1}. ${question.options[i]}");
     }

     print("Enter your answer: ");
     int userAnswer = int.parse(stdin.readLineSync()!);
     

     if (userAnswer == question.correctOption) {
       print("Correct!\n");
       score++;
     } else {
       print("Incorrect. The correct answer is: " + ans + "\n");
     }
   }

   print("Score: $score/${questions.length}");
 }
}


void main() {
  Quiz quiz = Quiz();
  quiz.addQuestion("12 * 23 = ?",["207", "216", "257", "276"],4);
  quiz.addQuestion("540/6 = ?",["70", "85", "90", "95"],3);
  quiz.addQuestion("102+(11*10) = ?",["212", "221", "313", "331"],1);

  print("Welcome to the Quiz");
  print("Answer the questions:\n");

  quiz.startQuiz();
}



   ```
<details>
<summary><strong>Output Correct</strong></summary>
<pre>
<code>Welcome to the Quiz
Answer the questions using the number in front of the answer:
</n>
12 * 23 = ?
1. 207
2. 216
3. 257
4. 276
Enter your answer: 
4
Correct!
</n>
540/6 = ?
1. 70
2. 85
3. 90
4. 95
Enter your answer: 
3
Correct!
</n>
102+(11*10) = ?
1. 212
2. 221
3. 313
4. 331
Enter your answer: 
1
Correct!
</n>
Score: 3/3</code>
</pre>
</details>

<details>
<summary><strong>Output Incorrect</strong></summary>
<pre>
<code>Welcome to the Quiz
Answer the questions using the number in front of the answer:
</n>
12 * 23 = ?
1. 207
2. 216
3. 257
4. 276
Enter your answer: 
1
Incorrect. The correct answer is: 276
</n>
540/6 = ?
1. 70
2. 85
3. 90
4. 95
Enter your answer: 
2
Incorrect. The correct answer is: 90
</n>
102+(11*10) = ?
1. 212
2. 221
3. 313
4. 331
Enter your answer: 
3
Incorrect. The correct answer is: 212
</n>
Score: 0/3</code>
</pre>
</details>

## Link Video

https://youtu.be/M2g2VdWVMG4

## Slide

[Practice6.pdf](https://github.com/soonklang/dart-tutorial/files/12890760/Present.Dart.pdf)

## Reference
https://dart-tutorial.com/object-oriented-programming/<br>
https://www.w3schools.com/java/java_oop.asp<br>
https://www.w3schools.com/c/c_enums.php
