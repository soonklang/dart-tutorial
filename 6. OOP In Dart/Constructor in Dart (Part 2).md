# Constructor in Dart (Part 2)
## ตัวอย่างที่ 5 : การเขียน Constructor แบบย่อ
*ในตัวอย่างก่อนหน้านี้คุณจำเป็นต้องเขียน Constructor แบบเต็ม เเต่คุณสามารถเขียนแบบย่อให้สั้นลงเหลือเพียงบรรทัด โดยการ Assign ค่าลงไปในพารามิเตอร์ได้เลย

  ```class Person{
  String? name;
  int? age;
  String? subject;
  double? salary;

  // Constructor in short form
  Person(this.name, this.age, this.subject, this.salary);

  // display method
  void display(){
    print("Name: ${this.name}");
    print("Age: ${this.age}");
    print("Subject: ${this.subject}");
    print("Salary: ${this.salary}");
  }
}

void main(){
  Person person = Person("John", 30, "Maths", 50000.0);
  person.display();
}
```
