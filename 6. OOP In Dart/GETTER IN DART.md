
# GETTER IN DART
Getter ใน Dart ใช้ในการรับค่าของคุณสมบัติหรือ property นั้น ๆ โดยมักถูกใช้เพื่อเข้าถึงค่าของคุณสมบัติที่เป็นส่วนตัวหรือเรียก private  โดย Getter จะให้การเข้าถึงอ่านค่าของคุณสมบัติของอ็อบเจกต์เป็นอย่างชัดเจน
# Syntax
```
return_type get property_name {
  // Getter body
}
```
# Example 1: Getter In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Person คลาสนี้มีคุณสมบัติสองอัน คือ firstName และ lastName นอกจากนี้ยังมี getter ชื่อ fullName ที่รับผิดชอบในการรับชื่อเต็มของบุคคล
```
class Person {
  // Properties
  String? firstName;
  String? lastName;

  // Constructor
  Person(this.firstName, this.lastName);

  // Getter
  String get fullName => "$firstName $lastName";
}

void main() {
  Person p = Person("John", "Doe");
  print(p.fullName);
}
```

# Example 2: Getter In Dart

ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ NoteBook คลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name และ _prize จึงต้องมี getter สองตัว คือ name และ prize เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้
```
class NoteBook {
  // Private properties
  String? _name;
  double? _prize;

  // Constructor
  NoteBook(this._name, this._prize);

  // Getter method to access private property _name
  String get name => this._name!;

  // Getter method to access private property _prize
  double get prize => this._prize!;
}

void main() {
  // Create an object of NoteBook class
  NoteBook nb = new NoteBook("Dell", 500);
  // Display the values of the object
  print(nb.name);
  print(nb.prize);
}
```

# Example 3: Getter In Dart With Data Validation

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ NoteBook ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name และ _prize นอกจากนี้ยังมี getter อยู่สองตัว คือ name และ prize เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ ในส่วนของgetter _nameหากคุณระบุชื่อเป็นค่าว่างเปล่า จะคืนค่า "ไม่มีชื่อ" แต่ถ้ามีค่าก็จะคืนค่าแบบปกติ
```
   class NoteBook {
  // Private properties
  String _name;
  double _prize;

  // Constructor
  NoteBook(this._name, this._prize);

  // Getter to access private property _name
  String get name {
    if (_name == "") {
      return "No Name";
    }
    return this._name;
  }

  // Getter to access private property _prize
  double get prize {
    return this._prize;
  }
}

void main() {
  // Create an object of NoteBook class
  NoteBook nb = new NoteBook("Apple", 1000);
  print("First Notebook name: ${nb.name}");
  print("First Notebook prize: ${nb.prize}");
  NoteBook nb2 = new NoteBook("", 500);
  print("Second Notebook name: ${nb2.name}");
  print("Second Notebook prize: ${nb2.prize}");
}
```
# Example 4: Getter In Dart

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ Doctor ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name, _age และ _gender นอกจากนี้ยังมี getter อยู่สามตัว คือ name, age และ gender เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ นอกจากนี้ยังมี getter ชื่อ [map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ที่ใช้ในการรับ [Map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ของอ็อบเจกต์
```
class Doctor {
// Private properties
  String _name;
  int _age;
  String _gender;

// Constructor
  Doctor(this._name, this._age, this._gender);

// Getters
  String get name => _name;
  int get age => _age;
  String get gender => _gender;

// Map Getter
  Map<String, dynamic> get map {
    return {"name": _name, "age": _age, "gender": _gender};
  }
}

void main() {
// Create an object of Doctor class
  Doctor d = Doctor("John", 41, "Male");
  print(d.map);
}
```
# ความแตกต่าง Dart and Java and Python

### Dart
```
class Person {
  String _name;

  Person(this._name);

  String get name {
    return _name;
  }
}

```
### Java
```
public class Person {
    private String name;

    public String getName() {
        return name;
    }
}
```
### Python
```
class Person:
    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

```

# ทำไม Getter มีความสำคัญใน Dart?

1.เพื่อเข้าถึงค่าของคุณสมบัติที่เป็นส่วนตัว

2.เพื่อจำกัดการเข้าถึงสมาชิกข้อมูลในคลาส

# สรุป
Getter เป็นเมธตอดในค่าที่การเข้าถึงแบบ private แต่ถ้าหากต้องการเข้าไปแก้ไขค่าจะต้องใช่ [Setter](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/setter%20in%20Dart.md) แทน
