
# GETTER IN DART
Getter ใน Dart ใช้ในการรับค่าของคุณสมบัติหรือ property นั้น ๆ โดยมักถูกใช้เพื่อเข้าถึงค่าของคุณสมบัติที่เป็นส่วนตัวหรือเรียก private  โดย Getter จะให้การเข้าถึงอ่านค่าของคุณสมบัติของอ็อบเจกต์เป็นอย่างชัดเจน
# Syntax
```
return_type get property_name {
  // Getter body
}
```
หมายเหตุ: แทนที่จะเขียน { } หลังชื่อ property คุณยังสามารถเขียน => (เครื่องหมายลูกศรหนา) หลังชื่อ property ได้เช่นกัน
```
class Person {
  String _name;
  
  Person(this._name);
  
  String get name => _name; // ใช้เครื่องหมายลูกศรแทนการใส่ { return ...; }
}
```
# Example 1: Getter In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ Person คลาสนี้มีคุณสมบัติสองอัน คือ firstName และ lastName นอกจากนี้ยังมี getter ชื่อ fullName ที่รับผิดชอบในการรับชื่อเต็มของบุคคล

* DART
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
## ในภาษาอื่นๆ
* java
```
public class Person {
    // Properties
    private String firstName;
    private String lastName;

    // Constructor
    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    // Getter
    public String getFullName() {
        return firstName + " " + lastName;
    }

    public static void main(String[] args) {
        Person p = new Person("John", "Doe");
        System.out.println(p.getFullName());
    }
}

```
* python
```
class Person:
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name

    @property
    def full_name(self):
        return f"{self.first_name} {self.last_name}"

if __name__ == "__main__":
    p = Person("John", "Doe")
    print(p.full_name)

```

# Example 2: Getter In Dart

ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ NoteBook คลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name และ _prize จึงต้องมี getter สองตัว คือ name และ prize เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้

* DART
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
## ในภาษาอื่นๆ
* java
```
public class NoteBook {
    // Private properties
    private String _name;
    private double _prize;

    // Constructor
    public NoteBook(String _name, double _prize) {
        this._name = _name;
        this._prize = _prize;
    }

    // Getter method to access private property _name
    public String getName() {
        return this._name;
    }

    // Getter method to access private property _prize
    public double getPrize() {
        return this._prize;
    }

    public static void main(String[] args) {
        // Create an object of NoteBook class
        NoteBook nb = new NoteBook("Dell", 500);
        // Display the values of the object
        System.out.println(nb.getName());
        System.out.println(nb.getPrize());
    }
}
```
* python

```
class NoteBook:
    # Private properties
    def __init__(self, name, prize):
        self._name = name
        self._prize = prize

    # Getter method to access private property _name
    def get_name(self):
        return self._name

    # Getter method to access private property _prize
    def get_prize(self):
        return self._prize

if __name__ == "__main__":
    # Create an object of NoteBook class
    nb = NoteBook("Dell", 500)
    # Display the values of the object
    print(nb.get_name())
    print(nb.get_prize())

```


# Example 3: Getter In Dart With Data Validation

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ NoteBook ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name และ _prize นอกจากนี้ยังมี getter อยู่สองตัว คือ name และ prize เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ ในส่วนของgetter _nameหากคุณระบุชื่อเป็นค่าว่างเปล่า จะคืนค่า "ไม่มีชื่อ" แต่ถ้ามีค่าก็จะคืนค่าแบบปกติ

* Dart
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
## ในภาษาอื่นๆ
* java
```
public class NoteBook {
    // Private properties
    private String _name;
    private double _prize;

    // Constructor
    public NoteBook(String _name, double _prize) {
        this._name = _name;
        this._prize = _prize;
    }

    // Getter to access private property _name
    public String getName() {
        if (_name.isEmpty()) {
            return "No Name";
        }
        return this._name;
    }

    // Getter to access private property _prize
    public double getPrize() {
        return this._prize;
    }

    public static void main(String[] args) {
        // Create an object of NoteBook class
        NoteBook nb = new NoteBook("Apple", 1000);
        System.out.println("First Notebook name: " + nb.getName());
        System.out.println("First Notebook prize: " + nb.getPrize());
        NoteBook nb2 = new NoteBook("", 500);
        System.out.println("Second Notebook name: " + nb2.getName());
        System.out.println("Second Notebook prize: " + nb2.getPrize());
    }
}
```
* python
```
class NoteBook:
    # Private properties
    def __init__(self, name, prize):
        self._name = name
        self._prize = prize

    # Getter to access private property _name
    @property
    def name(self):
        if self._name == "":
            return "No Name"
        return self._name

    # Getter to access private property _prize
    @property
    def prize(self):
        return self._prize

if __name__ == "__main__":
    # Create an object of NoteBook class
    nb = NoteBook("Apple", 1000)
    print(f"First Notebook name: {nb.name}")
    print(f"First Notebook prize: {nb.prize}")
    nb2 = NoteBook("", 500)
    print(f"Second Notebook name: {nb2.name}")
    print(f"Second Notebook prize: {nb2.prize}")

```

# Example 4: Getter In Dart

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ Doctor ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name, _age และ _gender นอกจากนี้ยังมี getter อยู่สามตัว คือ name, age และ gender เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ นอกจากนี้ยังมี getter ชื่อ [map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ที่ใช้ในการรับ [Map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ของอ็อบเจกต์
* Dart
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
## ในภาษาอื่นๆ
* java
```
import java.util.HashMap;
import java.util.Map;

public class Doctor {
    // Private properties
    private String _name;
    private int _age;
    private String _gender;

    // Constructor
    public Doctor(String _name, int _age, String _gender) {
        this._name = _name;
        this._age = _age;
        this._gender = _gender;
    }

    // Getters
    public String getName() {
        return _name;
    }

    public int getAge() {
        return _age;
    }

    public String getGender() {
        return _gender;
    }

    // Map Getter
    public Map<String, Object> getMap() {
        Map<String, Object> map = new HashMap<>();
        map.put("name", _name);
        map.put("age", _age);
        map.put("gender", _gender);
        return map;
    }

    public static void main(String[] args) {
        // Create an object of Doctor class
        Doctor d = new Doctor("John", 41, "Male");
        System.out.println(d.getMap());
    }
}

```
* Python
```
class Doctor:
    # Private properties
    def __init__(self, name, age, gender):
        self._name = name
        self._age = age
        self._gender = gender

    # Getters
    @property
    def name(self):
        return self._name

    @property
    def age(self):
        return self._age

    @property
    def gender(self):
        return self._gender

    # Map Getter
    @property
    def map(self):
        return {"name": self._name, "age": self._age, "gender": self._gender}

if __name__ == "__main__":
    # Create an object of Doctor class
    d = Doctor("John", 41, "Male")
    print(d.map)

```
# สรุปความแตกต่างของGetter ใน Dart and Java and Python
การเขียน Getter ใน Java, Python, และ Dart นั้นมีความแตกต่างกันเล็กน้อยในลักษณะการเขียนและไวยากรณ์ ดังนี้:

### Dart
ใน Dart, เราใช้คีย์เวิร์ด get ร่วมกับชื่อเมทอดเพื่อประกาศ getter ดังนี้:
```
class Person {
  String _name; // นี่คือ property ที่เก็บชื่อของบุคคล

  Person(this._name);

  String get name {
    return _name;
  }
}

```
### Java
ใน Java, เราต้องประกาศเมทอดเรียกอีกตัวชื่อเดียวกับ property แต่เติมคำว่า "get" ด้านหน้า และใช้งานในรูปแบบ getType getProperty()
```
public class Person {
    private String name; // นี่คือ property ที่เก็บชื่อของบุคคล

    public String getName() {
        return name;
    }
}
```
### Python
ใน Python, เราสามารถใช้ @property decorator เพื่อกำหนดเมทอด getter สำหรับ property ดังนี้:
```
class Person:
    def __init__(self, name):
        self._name = name # นี่คือ property ที่เก็บชื่อของบุคคล

    @property
    def name(self):
        return self._name

```

* สรุป:

    ใน Java, เราใช้ชื่อเมทอดที่เรียกว่า "get" ร่วมกับชื่อ property

    ใน Python, เราใช้ @property decorator ร่วมกับเมทอดที่มีชื่อเหมือนกับ property

    ใน Dart, เราใช้คีย์เวิร์ด get ร่วมกับชื่อเมทอดที่เป็นชื่อเดียวกับ property

# ทำไม Getter มีความสำคัญใน Dart?

    1.เพื่อเข้าถึงค่าของคุณสมบัติที่เป็นส่วนตัว

    2.เพื่อจำกัดการเข้าถึงสมาชิกข้อมูลในคลาส

# สรุป
Getter เป็นเมธตอดในค่าที่การเข้าถึงแบบ private แต่ถ้าหากต้องการเข้าไปแก้ไขค่าจะต้องใช่ [Setter](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/setter%20in%20Dart.md) แทน

# แหล่งอ้างอิง

https://dart-tutorial.com/

https://dart.dev/tutorials
