
# GETTER IN DART
Getter ใน Dart ใช้ในการรับค่าหรือคุณสมบัติ(property)ของคลาส โดยมักถูกใช้เพื่อเข้าถึงค่าของคุณสมบัติที่เป็นส่วนตัวหรือที่เรียก private  โดย Getter จะให้การเข้าถึงอ่านหรือรับข้อมูลค่าของคุณสมบัติของอ็อบเจกต์


Getter ใช้ในการดึงข้อมูลของฟิลด์คลาสตามที่กำหนดแล้วเก็บไว้ในตัวแปร ทุกคลาสมีเมทอด getter เริ่มต้นอยู่แล้ว แต่สามารถถูกโอเวอร์ไรด์ได้โดยชัดเจน Getter method สามารถนิยามได้โดยใช้คีย์เวิร์ด get ดังนี้

# Syntax
```dart
return_type get property_name {
  // Getter body
}
```
นอกจากนี้ แทนที่จะเขียน { } หลังชื่อ property คุณยังสามารถเขียน => (เครื่องหมายลูกศร) หลังชื่อ property แทนที่ได้
```dart
class Person {
  String _name;
  
  Person(this._name);
  
  String get name => _name; // ใช้เครื่องหมายลูกศรแทนการใส่ { return ...; }
}
```
# ตัวอย่างที่ 1: Getter In Dart
ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ employee คลาสนี้มีคุณสมบัติสองอัน คือ firstName และ lastName และในโค้ดนี้ getter นอกจากจะเข้าถึงอ่านค่าของคุณสมบัติ ยังนำค่ามารวมกันที่ตัวแปรชื่อ fullName ที่รับค่ามารวมกันมาเป็นชื่อเต็ม

* DART
```dart
class employee {
  // Properties
  String? firstName;
  String? lastName;

  // Constructor
  employee(this.firstName, this.lastName);

  // Getter
  String get fullName => "$firstName $lastName";
}

void main() {
  employee e = employee("Max", "inwza007");
  print(e.fullName);
}
```
<details>
  <summary><strong>Show Output</strong></summary>
  
```
Max inwza007
```

</details>

## ในภาษาอื่นๆ

* java

```java
public class Employee {
    // Properties
    private String firstName;
    private String lastName;

    // Constructor
    public Employee(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    // Getter
    public String getFullName() {
        return firstName + " " + lastName;
    }

    public static void main(String[] args) {
        Employee e = new Employee("Max", "inwza007");
        System.out.println(e.getFullName());
    }
}


```
* python
```python
class Employee:
    # Properties
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name

    # Getter
    @property
    def full_name(self):
        return f"{self.first_name} {self.last_name}"

if __name__ == "__main__":
    e = Employee("Max", "inwza007")
    print(e.full_name)

```

# ตัวอย่างที่ 2: Getter In Dart

ในตัวอย่างด้านล่างนี้ มีคลาสชื่อ employeeName คลาสนี้มีคุณสมบัติสองอันที่เป็น private คือ _name และ _ID จึงต้องมี getter สองตัว คือ name และ ID เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้

* DART
```dart
class employee {
  // Private properties
  String? _name;
  String? _ID;

  // Constructor
  employee(this._name, this._ID);

  // Getter method to access private property _name
  String get name => this._name!;

  // Getter method to access private property _ID
  String get ID => this._ID!;
}

void main() {
  // Create an object of employee class
  employee nb = new employee("max", "777");
  // Display the values of the object
  print(nb.name);
  print(nb.ID);
}
 
```

<details>
  <summary><strong>Show Output</strong></summary>
  
```
Name: max
ID: 777.0
```
  
</details>

## ในภาษาอื่นๆ
* java
```java
public class Employee {
    // Private properties
    private String _name;
    private String _ID;

    // Constructor
    public Employee(String _name, String _ID) {
        this._name = _name;
        this._ID = _ID;
    }

    // Getter method to access private property _name
    public String getName() {
        return this._name;
    }

    // Getter method to access private property _ID
    public String getID() {
        return this._ID;
    }

    public static void main(String[] args) {
        // Create an object of Employee class
        Employee nb = new Employee("max", "777");
        // Display the values of the object
        System.out.println(nb.getName());
        System.out.println(nb.getID());
    }
}


```
* python

```python
class Employee:
    # Private properties
    def __init__(self, name, ID):
        self._name = name
        self._ID = ID

    # Getter method to access private property _name
    def get_name(self):
        return self._name

    # Getter method to access private property _ID
    def get_ID(self):
        return self._ID

if __name__ == "__main__":
    # Create an object of Employee class
    nb = Employee("max", "777")
    # Display the values of the object
    print(nb.get_name())
    print(nb.get_ID())

```


# ตัวอย่างที่ 3: Getter In Dart With Data Validation

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ employee ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name และ _id นอกจากนี้ยังมี getter อยู่สองตัว คือ name และ id เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ ในส่วนของgetter _nameหากคุณระบุชื่อเป็นค่าว่างเปล่า จะคืนค่า "ไม่มีชื่อ" แต่ถ้ามีค่าก็จะคืนค่าแบบปกติ

* Dart
```dart
   class employee {
  // Private properties
  String _name;
  String _id;

  // Constructor
  employee(this._name, this._id);

  // Getter to access private property _name
  String get name {
    if (_name == "") {
      return "No Name";
    }
    return this._name;
  }

  // Getter to access private property _prize
  String get id {
    return this._id;
  }

}

void main() {
  // Create an object of employee class
  employee nb = new employee("john", "1423");
  print("First employee name: ${nb.name}");
  print("First employee id: ${nb.id}");
  employee nb2 = new employee("", "9999");
  print("Second employee name: ${nb2.name}");
  print("Second employee id: ${nb2.id}");
}


  
```
<details>
  <summary><strong>Show Output</strong></summary>
  

```
    First employee name: john
    First employee id: 1423
    Second employee name: No Name
    Second employee id: 9999
```
</details>

## ในภาษาอื่นๆ
* java
```java
public class Employee {
    // Private properties
    private String _name;
    private String _id;

    // Constructor
    public Employee(String _name, String _id) {
        this._name = _name;
        this._id = _id;
    }

    // Getter to access private property _name
    public String getName() {
        if (_name.isEmpty()) {
            return "No Name";
        }
        return this._name;
    }

    // Getter to access private property _id
    public String getId() {
        return this._id;
    }

    public static void main(String[] args) {
        // Create an object of Employee class
        Employee nb = new Employee("john", "1423");
        System.out.println("First employee name: " + nb.getName());
        System.out.println("First employee id: " + nb.getId());
        Employee nb2 = new Employee("", "9999");
        System.out.println("Second employee name: " + nb2.getName());
    }
}

```
* python
```python
class Employee:
    # Private properties
    def __init__(self, name, id):
        self._name = name
        self._id = id

    # Getter to access private property _name
    @property
    def name(self):
        if self._name == "":
            return "No Name"
        return self._name

    # Getter to access private property _id
    @property
    def id(self):
        return self._id

if __name__ == "__main__":
    # Create an object of Employee class
    nb = Employee("john", "1423")
    print(f"First employee name: {nb.name}")
    print(f"First employee id: {nb.id}")
    nb2 = Employee("", "9999")
    print(f"Second employee name: {nb2.name}")

```

# ตัวอย่างที่ 4: Getter In Dart

ในตัวอย่างด้านล่างนี้, มีคลาสชื่อ employee ในคลาสนี้มีคุณสมบัติสองอันที่เป็นส่วนตัว คือ _name, _age และ _gender นอกจากนี้ยังมี getter อยู่สามตัว คือ name, age และ gender เพื่อใช้ในการเข้าถึงค่าของคุณสมบัติเหล่านี้ นอกจากนี้ยังมี getter ชื่อ [map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ที่ใช้ในการรับ [Map](https://github.com/soonklang/dart-tutorial/blob/main/4.%20Collections%20In%20Dart/Map%20in%20Dart.md) ของอ็อบเจกต์
* Dart
```dart
class employee {
// Private properties
  String _name;
  int _age;
  String _gender;

// Constructor
  employee(this._name, this._age, this._gender);

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
// Create an object of employee class
  employee d = employee("John", 41, "Male");
  print(d.map);
}


  
```
<details>
  <summary><strong>Show Output</strong></summary>
  
```
  {name: John, age: 41, gender: Male}
```
</details>

## ในภาษาอื่นๆ
* java
```java
import java.util.HashMap;
import java.util.Map;

public class Employee {
    // Private properties
    private String _name;
    private int _age;
    private String _gender;

    // Constructor
    public Employee(String _name, int _age, String _gender) {
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
        // Create an object of Employee class
        Employee d = new Employee("John", 41, "Male");
        System.out.println(d.getMap());
    }
}


```
* Python
```python
class Employee:
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
    # Create an object of Employee class
    d = Employee("John", 41, "Male")
    print(d.map)

```
# สรุปความแตกต่างของGetter ใน Dart and Java and Python
การเขียน Getter ใน Java, Python, และ Dart นั้นมีความแตกต่างกันเล็กน้อยในลักษณะการเขียนและไวยากรณ์ ดังนี้:

### Dart
ใน Dart, เราใช้คีย์เวิร์ด get ร่วมกับชื่อเมทอดเพื่อประกาศ getter ดังนี้:
```dart
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
```java
public class Person {
    private String name; // นี่คือ property ที่เก็บชื่อของบุคคล

     // Constructor
    public Person(String name) {
        this._name = name;
    }
    public String getName() {
        return name;
    }
}
```
### Python
ใน Python, เราสามารถใช้ @property decorator เพื่อกำหนดเมทอด getter สำหรับ property ดังนี้:
```python
class Person:
    def __init__(self, name):
        self._name = name # นี่คือ property ที่เก็บชื่อของบุคคล

    @property
    def name(self):
        return self._name

```

* สรุป:
  
    ใน Dart, จะการเขียนต่อนข้างคล้าย javaแต่มีการเขียนที่ง่ายกว่า

    ใน Java, จะการเขียนค่อนข้างยากกว่า Dart เล็กน้อย

    ใน Python, เขียนได้ง่ายกว่าแต่อ่านได้ยากกว่าทั้งสองภาษา

   



# สรุป
Getter เป็นเมธตอดในค่าที่ส่วนใหญ่จะเป็นการเข้าถึงแบบ private แต่ถ้าหากต้องการเข้าไปแก้ไขค่าจะต้องใช่ [Setter](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/setter%20in%20Dart.md) แทน

* คลิปสอนและสไลด์:

  https://youtu.be/TEqHg_ZWAfI

  https://drive.google.com/file/d/15Twp_qixtOJHiNdF-8Kv8AaT1J77peAS/view?usp=sharing

# แหล่งอ้างอิง

https://dart-tutorial.com/object-oriented-programming/getter-in-dart/

https://dart.dev/language/methods

https://www.geeksforgeeks.org/getter-and-setter-methods-in-dart/?ref=lbp
