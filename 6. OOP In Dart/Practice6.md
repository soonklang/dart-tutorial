# Practice 6
## เเบบฝึกหัด เรี่อง Object-oriented programming (OOP) In Dart
--------------------------------------------------------------------------------
## 1.Write a dart program to create a class Laptop with properties [id, name, ram] and create 3 objects of it and print all details.
### - Dart
 ```dart
class Laptop {
  int id;
  String name;
  int ram;
  // สร้าง 3 Object ใน Laptop
  Laptop(this.id, this.name, this.ram);

  // print ข้อมูลใน Laptop
  void printDetails() {
    print('Laptop ID: $id');
    print('Laptop Name: $name');
    print('Laptop Ram: $ram');
    print("");
  }
}

void main() {
  Laptop Asus = Laptop(1, 'Asus', 16);
  Laptop Lenovo = Laptop(2, 'Lenovo', 8);
  Laptop Acer = Laptop(3, 'Acer', 32);

  Asus.printDetails();
  Lenovo.printDetails();
  Acer.printDetails();
}

   ```
### - C
```c
#include <stdio.h>
#include <string.h>

struct Laptop {
    int id;
    char name[50];
    int ram;
};

void printLaptopDetails(struct Laptop laptop) {
    printf("Laptop Id: %d\n", laptop.id);
    printf("Laptop Name: %s\n", laptop.name);
    printf("Laptop Ram: %d GB\n", laptop.ram);
    printf("\n");
}

int main() {
    struct Laptop laptop1 = {1, "Asus", 16};
    struct Laptop laptop2 = {2, "Lenovo", 8};
    struct Laptop laptop3 = {3, "Acer", 32};

    printLaptopDetails(laptop1);
    printLaptopDetails(laptop2);
    printLaptopDetails(laptop3);

    return 0;
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
### - C
```c
#include <stdio.h>
#include <stdlib.h>

struct House {
    int id;
    char name[50];
    double price;
};

int main() {
    struct House houses[3];

    struct House house_1 = {1, "House A", 200000.0};
    struct House house_2 = {2, "House B", 300000.0};
    struct House house_3 = {3, "House C", 400000.0};

    houses[0] = house_1;
    houses[1] = house_2;
    houses[2] = house_3;

    for (int i = 0; i < 3; i++) {
        printf("House ID: %d\n", houses[i].id);
        printf("House Name: %s\n", houses[i].name);
        printf("House Price: $%.2f\n", houses[i].price);
        printf("\n");
    }

    return 0;
}

   ```
### - Java
```java
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
        House[] houses = new House[3];

        House house_1 = new House(1, "House A", 200000.0);
        House house_2 = new House(2, "House B", 300000.0);
        House house_3 = new House(3, "House C", 400000.0);

        houses[0] = house_1;
        houses[1] = house_2;
        houses[2] = house_3;

        for (House house : houses) {
            System.out.println("House ID: " + house.id);
            System.out.println("House Name: " + house.name);
            System.out.println("House Price: " + house.price));
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
### - C
```c
#include <stdio.h>
#include <string.h>

// Animal structure
struct Animal {
    int id;
    char name[50];
    char color[20];
};

// Cat inheriting from Animal
struct Cat {
    struct Animal animal;
    char sound[20];
};

int main() {
    struct Cat cat = {{1, "mali", "Gray"}, "Meow"};

    printf("Cat ID: %d\n", cat.animal.id);
    printf("Cat Name: %s\n", cat.animal.name);
    printf("Cat Color: %s\n", cat.animal.color);
    printf("Cat Sound: %s\n", cat.sound);

    return 0;
}

   ```
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
  int _id;
  String _brand;
  String _color;
  double _price;

  Camera(this._id, this._brand, this._color, this._price);
  // Create a getter and setter to get and set values
  int get id => _id;
  String get brand => _brand;
  String get color => _color;
  double get price => _price;

  set id(int value) {
    _id = value;
  }

  set brand(String value) {
    _brand = value;
  }

  set color(String value) {
    _color = value;
  }

  set price(double value) {
    _price = value;
  }
}

void main() {
  Camera camera1 = Camera(1, "Sony", "Black", 500.0);
  Camera camera2 = Camera(2, "Canon", "Silver", 600.0);
  Camera camera3 = Camera(3, "Nikon", "Red", 550.0);

  print("Camera 1 - ID: ${camera1.id}, Brand: ${camera1.brand}, Color: ${camera1.color}, Price: ${camera1.price}");
  print("Camera 2 - ID: ${camera2.id}, Brand: ${camera2.brand}, Color: ${camera2.color}, Price: ${camera2.price}");
  print("Camera 3 - ID: ${camera3.id}, Brand: ${camera3.brand}, Color: ${camera3.color}, Price: ${camera3.price}");
}
   ```
### - C
```c
#include <stdio.h>
#include <string.h>

struct Camera {
    int id;
    char brand[50];
    char color[20];
    double price;
};

int main() {
    struct Camera camera1 = {1, "Sony", "Black", 500.0};
    struct Camera camera2 = {2, "Canon", "Silver", 600.0};
    struct Camera camera3 = {3, "Nikon", "Red", 550.0};

    printf("Camera Details:\n");
    printf("Camera 1 - ID: %d, Brand: %s, Color: %s, Price: $%.2f\n", camera1.id, camera1.brand, camera1.color, camera1.price);
    printf("Camera 2 - ID: %d, Brand: %s, Color: %s, Price: $%.2f\n", camera2.id, camera2.brand, camera2.color, camera2.price);
    printf("Camera 3 - ID: %d, Brand: %s, Color: %s, Price: $%.2f\n", camera3.id, camera3.brand, camera3.color, camera3.price);

    return 0;
}

   ```
### - Java
```java
class Camera {
    int id;
    String brand;
    String color;
    double price;

    public Camera(int id, String brand, String color, double price) {
        this.id = id;
        this.brand = brand;
        this.color = color;
        this.price = price;
    }
    //สร้าง method เพื่อให้สามารถเข้าถีงเเต่ละวัตถุได้
    public int getId() {
        return id;
    }

    public String getBrand() {
        return brand;
    }

    public String getColor() {
        return color;
    }

    public double getPrice() {
        return price;
    }

    public void setId(int id) {
        this.id = id;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setColor(String color) {
        this.color = color;
    }

    public void setPrice(double price) {
        this.price = price;
    }
}

public class Main {
    public static void main(String[] args) {
        Camera camera1 = new Camera(1, "Sony", "Black", 500.0);
        Camera camera2 = new Camera(2, "Canon", "Silver", 600.0);
        Camera camera3 = new Camera(3, "Nikon", "Red", 550.0);

        System.out.println("Camera Details:");
        System.out.println("Camera 1 - ID: " + camera1.getId() + ", Brand: " + camera1.getBrand() + ", Color: " + camera1.getColor() + ", Price: " + camera1.getPrice());
        System.out.println("Camera 2 - ID: " + camera2.getId() + ", Brand: " + camera2.getBrand() + ", Color: " + camera2.getColor() + ", Price: " + camera2.getPrice());
        System.out.println("Camera 3 - ID: " + camera3.getId() + ", Brand: " + camera3.getBrand() + ", Color: " + camera3.getColor() + ", Price: " + camera3.getPrice());
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
  factory Bottle() {
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
  Bottle cokeBottle = Bottle();
  cokeBottle.open();
}

   ```
### - Java
```java
interface Bottle {
    void open();
}

class CokeBottle implements Bottle {
    @Override
    public void open() {
        System.out.println("Coke bottle is opened");
    }
}

public class Main {
    public static void main(String[] args) {
        // สร้าง CokeBottle โดยใช้ Bottle factory constructor
        Bottle cokeBottle = new CokeBottle();

        cokeBottle.open();
    }
}

   ```

## 7.Create a simple quiz application using oop that allows users to play and view their score.
### - Dart
 ```dart

   ```

## Reference
https://dart-tutorial.com/object-oriented-programming/<br>
https://www.w3schools.com/java/java_oop.asp<br>
https://www.w3schools.com/c/c_structs.php<br>
