# Null Safety Exercises
ฝึกฝนแบบฝึกหัดเหล่านี้เพื่อให้เกิดความเชี่ยวชาญใน **Dart Null Safety** เพื่อฝึกฝน คุณสามารถกดปุุ่ม **ลองทำแบบฝึกหัด** และลองแก้ปัญหา

## Exercise 1: Null Safety In Dart
- ในการทำให้ชื่อตัวแปร **age** มีค่าเป็น **null** ให้เราใช้เครื่องหมาย **'?'**
```dart
// Try to assign a null value to age variable using '?'
void main() {
  int age;
  age = null;
  print("Age is $age");
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=d5947f463c719ff9667c6af855376536)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '?'
void main() {
  int? age; //or you can do int ?age;
  age = null;
  print("Age is $age");
}
```

<details>
  <summary><strong>Correct Output</strong></summary>
  <pre>
<code>Age is null
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' code จะรันผ่านและขึ้นผลลัพธ์
  </code></pre>
</details>
</details>

## Exercise 2: Nullable Type Parameter For Generics
- ลองใช้เครื่องหมาย **'?'** เพื่อทำให้ parameter ใน **List** สามารถเป็น null ได้
```dart
// Try to make the type parameter of List nullable
void main() {
  List<int> items = [1, 2, null, 4];
  print(items);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=3ed4aec39a483738d18cca44944be8e8)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '?'
void main() {
  List<int?> items = [1, 2, null, 4];
  print(items);
}
```

<details>
  <summary><strong>Correct Output</strong></summary>
  <pre>
<code>[1, 2, null, 4]
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' code จะรันผ่านและขึ้นผลลัพธ์
  </code></pre>
</details>
</details>

## Exercise 3: Null Assertion Operator (!)
- ลองใช้เครื่องหมายที่เป็นตัวยืนยันค่า null นั่นคือ **'!'** เพื่อแสดงค่า null หากตัวแปรมีค่าเป็น null
```dart
// Try to use null assertion operator(!) to print null if the variable is null
void main() {
  String? name;
  name = null;
  String name1 = name;
  print(name1);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=c244f5fee631d9426d1004a20f7c01c3)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '!'
void main() {
  String? name;
  name = null;
  String name1 = name!;
  print(name1);
}
```

<details>
  <summary><strong>Correct Output</strong></summary>
  <pre>
<code>Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ name เป็น null จึงทำให้เกิด <strong>NullError</strong>
  </code></pre>

<details>
  <summary><strong>Code if 'name' is not null</strong></summary>
  
```dart
//Code if name is not null
void main() {
  String? name;
  name = a;
  String name1 = name!;
  print(name1);
}
```
<details>
  <summary><strong>Output if name is not null</strong></summary>
  <pre>
<code>a
//จะเห็นว่าถ้าหาก name ไม่เป็น null มันก็จะปริ้นค่านั้นออกมา
  </code></pre>

</details>
</details>
</details>
</details>

## Exercise 4: Nullable Assertion Operator (!) For Generics
- ลองใช้เครื่องหมายที่เป็นตัวยืนยันค่า null นั่นคือ **'!'** เพื่อแสดงค่า null หากตัวแปรมีค่าเป็น null
```dart
// Try to use null assertion operator(!) to print null if the variable is null
void main() {
  List<int?> items = [1, 2, null, 4];
 
  int firstItem = items.first;
  
  print(firstItem);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=c1bcc0544dcb955a8d2e69373f88617b)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '!'
void main() {
  List<int?> items = [1, 2, null, 4];
 
  int firstItem = items.first!; // .first แสดงตัวแรกใน List
  
  print(firstItem);
}
```

<details>
  <summary><strong>Correct Output</strong></summary>
  <pre>
<code>1
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ code จะรันผ่านและขึ้นผลลัพธ์ 1 เพราตัวแรกใน List มีค่า 1
  </code></pre>

<details>
  <summary><strong>Code if null is in the first element</strong></summary>
  
```dart
//Code if null is in the first element
void main() {
  List<int?> items = [null, 2, 3, 4];
 
  int firstItem = items.first!; // .first แสดงตัวแรกใน List
  
  print(firstItem);
}
```
<details>
  <summary><strong>Output if null is in the first element</strong></summary>
  <pre>
<code>Runtime Error
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ตัวแรกใน List เป็น null จะทำให้เกิด <strong>NullError</strong>
  </code></pre>
</details>
</details>
</details>
</details>
