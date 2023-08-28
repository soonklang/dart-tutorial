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

Correct Output
```
Age is null
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' code จะรันผ่านและขึ้นผลลัพธ์
```

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

Correct Output
```
[1, 2, null, 4]
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' code จะรันผ่านและขึ้นผลลัพธ์
```

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

Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ name เป็น null จึงทำให้เกิด **NullError**
 ```


</details>

### Exercise 3.1 : 
- แล้วถ้าหากตัวแปร name ไม่ใช่ null จะเป็นยังไง ?

```dart
// Try to use null assertion operator(!) to print null if the variable is null
// Code if 'name' is not null
void main() {
  String? name;
  name = 'a';
  String name1 = name;
  print(name1);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=1d5b5705c27e5160bcbd1872655a26b8)


<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code if 'name' is not null
void main() {
  String? name;
  name = 'a';
  String name1 = name!; // เราจะมี '!' หรือไม่มี code ก็จะไม่ error
  print(name1);
}
```
Correct Output
```
a
//จะเห็นว่าถ้าหาก name ไม่เป็น null มันก็จะปริ้นค่านั้นออกมา 
```


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

Correct Output
```
1
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ code จะรันผ่านและขึ้นผลลัพธ์ 1 เพราตัวแรกใน List มีค่า 1
```

</details>

### Exercise 4.1 : 
- แล้วถ้าหากค่าแรกเป็น null จะเป็นยังไง ?

```dart
// Try to use null assertion operator(!) to print null if the variable is null
// Code if null is in the first element
void main() {
  List<int?> items = [null, 2, 3, 4];
 
  int firstItem = items.first; // .first แสดงตัวแรกใน List
  
  print(firstItem);
}
```
[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=6f9d3ccb17c09fa67fa7329cce464f37)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code if null is in the first element
void main() {
  List<int?> items = [null, 2, 3, 4];
 
  int firstItem = items.first!; // .first แสดงตัวแรกใน List
  
  print(firstItem);
}
```
Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ตัวแรกใน List เป็น null จะทำให้เกิด **NullError**
  
```
</details>

## Exercise 5: Null Assertion Operator (!) For Generics
- ลองใช้เครื่องหมายที่เป็นตัวยืนยันค่า null นั่นคือ **'!'** เพื่อแสดงค่า null หากตัวแปรมีค่าเป็น null
```dart
// Try to use null assertion operator(!) to print null if the variable is null
int? returnNullButSometimesNot() {
  return -5;
}

void main() {
 int result = returnNullButSometimesNot().abs();
 print(result);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=1b9b4febfbc21b23be8ae5bf146e95c1)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '!'
int? returnNullButSometimesNot() {
  return -5;
}

void main() {
 int result = returnNullButSometimesNot()!.abs();
 print(result);
}
```

Correct Output
```
5
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ค่า return ไม่ใช่ null จึงแสดงผลลัพธ์ 5
```
</details>

### Exercise 5.1 : 
- แล้วถ้าหากค่า return เป็น null จะเป็นยังไง ?

```dart
// Try to use null assertion operator(!) to print null if the variable is null
// Code if return is null
int? returnNullButSometimesNot() {
  return null;
}

void main() {
 int result = returnNullButSometimesNot().abs();
 print(result);
}
```
[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=0a70f601cabfa763d68a5e13bdbf62ae)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
// Code if return is null
int? returnNullButSometimesNot() {
  return null;
}

void main() {
 int result = returnNullButSometimesNot()!.abs();
 print(result);
}
```
Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ ค่า return เป็น null จะทำให้เกิด **NullError**
  
```

</details>

## Exercise 6: Null Assertion Operator (!)
- ลองใช้เครื่องหมายที่เป็นตัวยืนยันค่า null นั่นคือ **'!'** เพื่อแสดงค่าความยาวของ String หรือ return null ถ้าตัวแปรเป็น null
```dart
// Try to use null assertion operator(!) to print the length of the String or return null if the variable is null
int findLength(String? name) {
    // add null assertion operator here
  return name.length;
}

void main() {
  int? length = findLength("Hello");
  print("The length of the string is $length");
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=ae7997a085f35212078c2db830d3b673)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code after using '!'
int findLength(String? name) {
    // add null assertion operator here
  return name!.length;
}

void main() {
  int? length = findLength("Hello");
  print("The length of the string is $length");
}
```

Correct Output
```
The length of the string is 5
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ค่า length ของ 'name' = 5 ก็จะแสดง 5 ออกมา
```
</details>

### Exercise 6.1 : 
- แล้วถ้าหากค่า 'name' เป็น null จะเป็นยังไง ?

```dart
// Try to use null assertion operator(!) to print the length of the String or return null if the variable is null
// Code if 'name' is null
int findLength(String? name) {
    // add null assertion operator here
  return name.length;
}

void main() {
  int? length = findLength(null);
  print("The length of the string is $length");
}
```
[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=81fff84aec7bbb853094bcae06cbeea1)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
//Code if return is null
int findLength(String? name) {
    // add null assertion operator here
  return name!.length;
}

void main() {
  int? length = findLength(null);
  print("The length of the string is $length");
}
```
Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ ค่าตัวแปร 'name' เป็น null จะทำให้เกิด **NullError**
  
```

</details>

## Exercise 7: Null Coalescing Operator (??)
- หากคุณต้องการกำหนดค่า default ให้กับตัวแปรหากเป็น null คุณสามารถใช้ coalescing operator **'??'**
ลองใช้ null coaslescing operator **'??'** เพื่อกำหนดค่า default **Stranger** หากเป็น null
```dart
// Try to use null coalescing operator(??) to assign a default value to Stranger if it is null
void main() {
  String? name;
  name = null;
  String name1 = name;
  print(name1);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=ebddc5b4f402664e6c0439f2ac2fcce6)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
// Code after using null coalescing operator
void main() {
  String? name;
  name = null;
  String name1 = name ?? 'Hello';
  print(name1);
}
```

Correct Output
```
Hello
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '??' ต่อหลัง 'name' จะเป็นการกำหนดค่า default ให้กับตัวแปรที่เป็น null ทำให้เราจะสามารถแสดงผลลัพธ์ออกมาได้โดยที่ไม่ error
```
</details>
