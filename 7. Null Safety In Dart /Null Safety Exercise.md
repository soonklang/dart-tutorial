# Null Safety Exercises
ฝึกฝนแบบฝึกหัดเหล่านี้เพื่อให้เกิดความเชี่ยวชาญใน **Dart Null Safety** เพื่อฝึกฝน คุณสามารถกดปุุ่ม **ลองทำแบบฝึกหัด** และลองแก้ปัญหา

## Exercise 1: Null Safety In Dart
- ในการที่เราจะทำให้ตัวแปร **age** มีค่าเป็น **null** ได้ให้เราใช้เครื่องหมาย **'?'**
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

#### Correct Output

```
Age is null
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' (int? age;) code จะรันผ่านและขึ้นผลลัพธ์
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

#### Correct Output
```
[1, 2, null, 4]
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '?' (List<int?> items = [1, 2, null, 4];) code จะรันผ่านและขึ้นผลลัพธ์
```


</details>

<details>
  <summary><strong>การประกาศ List<> กับ Nullable เพิ่มเติม</strong></summary>

### การประกาศ List<> กับ Nullable เพิ่มเติม : 
- ความแตกต่างในการประกาศ List<> กับ Nullable ซึ่งเราประกาศได้ 4 แบบ


  
```dart
void main() {
  List<String> aListOfStrings = ['one', 'two', 'three']; //แบบที่ 1 List ห้าม null และ ห้าม push null ใส่ List ด้วย
  List<String>? aNullableListOfStrings; //แบบที่ 2 List เป็น null ได้ แต่ไม่สามารถ push null ใส่ List ได้
  List<String?> aListOfNullableStrings = ['one', null, 'three']; //แบบที่ 3 List ห้าม null แต่สามารถ push null ใส่ List ได้
  List<String?>? aNullableListOfStrings2; //แบบที่ 4 List เป็น null ได้ และสามารถ push null ใส่ List ได้

  aNullableListOfStrings = ['one'];
  //aNullableListOfStrings?.add(null) หากเราใส่ null เข้าไปในแบบที่ 2 จะ error ทันที
  aNullableListOfStrings2 = ['one','two'];
  aNullableListOfStrings2?.add(null);  // กลับกันในแบบที่ 4 จะใส่ null ได้

  print('aListOfStrings is $aListOfStrings.');
  print('aNullableListOfStrings is $aNullableListOfStrings.');
  print('aListOfNullableStrings is $aListOfNullableStrings.');
  print('aNullableListOfStrings2 is $aNullableListOfStrings2.');
}
```
#### Correct Output
```
aListOfStrings is [one, two, three]. //แบบที่ 1 
aNullableListOfStrings is [one]. //แบบที่ 2 สามารถประกาศ List null ได้แต่ add ไม่ได้
aListOfNullableStrings is [one, null, three]. //แบบที่ 3 List เป็น null ไม่ได้ แต่ add ได้
aNullableListOfStrings2 is [one, two, null]. //แบบที่ 4 List null ได้และ add ได้ด้วย
 
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

#### Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม (String name1 = name!;) ในกรณีนี้ name เป็น null จึงทำให้เกิด NullError
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
#### Correct Output
```
a
//จะเห็นว่าถ้าหาก name ไม่เป็น null มันก็จะปริ้นค่านั้นออกมา 
```


</details>


## Exercise 4: Null Assertion Operator (!) For Generics
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

#### Correct Output
```
1
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม (int firstItem = items.first!;)
ในกรณีนี้ code จะรันผ่านและขึ้นผลลัพธ์ 1 เพราตัวแรกใน List มีค่า 1
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
#### Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ตัวแรกใน List เป็น null จะทำให้เกิด NullError
  
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

#### Correct Output
```
5
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม (int result = returnNullButSometimesNot()!.abs();)
ในกรณีนี้ค่า return ไม่ใช่ null จึงแสดงผลลัพธ์ 5
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
#### Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ ค่า return เป็น null จะทำให้เกิด NullError
  
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

#### Correct Output
```
The length of the string is 5
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม (return name!.length;) ในกรณีนี้ค่า length ของ 'name' = 5 ก็จะแสดง 5 ออกมา
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
#### Correct Output
```
Uncaught TypeError: Cannot read properties of null (reading 'toString')Error: TypeError: Cannot read properties of null (reading 'toString')
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '!' ที่เป็นตัวยืนยันว่าค่าเป็น null ไหม ในกรณีนี้ ค่าตัวแปร 'name' เป็น null จะทำให้เกิด NullError
  
```

</details>

## Exercise 7: Null Coalescing Operator (??)
- หากคุณต้องการกำหนดค่า default ให้กับตัวแปรหากเป็น null คุณสามารถใช้ coalescing operator **'??'**
ลองใช้ null coaslescing operator **'??'** เพื่อกำหนดค่า default **name** หากเป็น null
```dart
// Try to use null coalescing operator(??) to assign a default value to name if it is null
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

#### Correct Output
```
Hello
//จะเห็นว่าเมื่อเราใส่เครื่องหมาย '??' ต่อหลัง 'name' (String name1 = name ?? 'Hello';)
จะเป็นการกำหนดค่า default ให้กับตัวแปรที่เป็น null ทำให้เราจะสามารถแสดงผลลัพธ์ออกมาได้โดยที่ไม่ error
```
</details>

## Exercise 8: Type Promotion
- แก้ไข error ด้วยการใช้ promotion (general types to specific subtypes)
```dart
// Try to solve the error using type promotion
Object name = "Mark";
print("The length of name is ${name.length}");
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=b7fa99e858705bc1cf05a94514a7f95e)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
// Code after using type promotion
void main(){
Object name = "Mark";
if(name is String){
  print("The length of name is ${name.length}");
}
}
```

#### Correct Output
```
4
//จะเห็นว่าเมื่อเราใช้ type promotion if(name is String) จะปรับปรุงชนิดของตัวแปรโดยอัตโนมัติ ในตัวแปร 'name'
การที่เราประกาศตัวแปรเป็น Object ไม่สามารถใช้ .length ได้ เมื่อเราทำการ promoted แล้ว จะปรับปรุงให้ 'name' เป็น String โดยอัตโนมัติ

```
</details>

## Exercise 9: Type Promotion
- แก้ไข error ด้วยการใช้ promotion (nullable types to non-nullable types)
```dart
// Try to solve the error using type promotion
import 'dart:math';
class DataProvider{
    String? get stringorNull => Random().nextBool() ? "Hello" : null;

    void myMethod(){
        if(stringorNull is String){
            print("The length of value is ${stringorNull.length}");
        }else{
            print("The value is not string.");
        }

    }
}

void main() {
    DataProvider().myMethod();
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=fe82354a868ce0200cc928387296d52b)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
// Code after using type promotion
import 'dart:math';
class DataProvider{
    String? get stringorNull => Random().nextBool() ? "Hello" : null;

    void myMethod(){
        String? value = stringorNull; 
        if(value is String){
            print("The length of value is ${value.length}");
        }else{
            print("The value is not string.");
        }

    }
}

void main() {
    DataProvider().myMethod();
}

```

#### Correct Output
```
The length of value is 5 or The value is not string.
//ใน code นี้ เรากำหนดตัวแปร 'value' เพื่อจะสุ่มเก็บค่า String (true) หรือไม่ก็ null(false) ตอน random boolean
แล้วเราจะ type promoted เป็น non-nullalbe type String ตรง  if(value is String)
ถ้าสุ่มค่า 'value' เป็น null(false) จะแสดงผลลัพธ์ The value is not string. ถ้าเป็น String(true) ก็จะแสดง The length of value is 5
```
</details>

## Exercise 10: Late Keyword
- ลองใช้ **late** keyword เพื่อแก้ไข error
```dart
// Try to solve the error using late keyword
class Person{
    String _name;

    void setName(String name){
        _name = name;
    }

    String get name => _name;
}

void main() {
    Person person = Person();
    person.setName("Mark");
    print(person.name);
}
```

[ลองทำแบบฝึกหัด](https://dartpad.dev/?id=30f4779d30a8f00cc2178cc9662dc8e3)

<details>
  <summary><strong>Correct Code</strong></summary>
  
```dart
// Code after using late keyword
class Person{
    late String _name;

    void setName(String name){
        _name = name;
    }

    String get name => _name;
}

void main() {
    Person person = Person();
    person.setName("Mark");
    print(person.name);
}

```

#### Correct Output
```
Mark
//เมื่อเราใส่คำสั่ง late ไปตอนประกาศตัวแปร late String _name; จะเป็นการบอกว่าจะกำหนดค่าให้ภายหลัง ใช้ในการประกาศ non-nullable
หากเราไม่ใส่คำสั่ง late จะเกิด NullError เพราะตอนประกาศค่าเป็น null 
```
</details>

## References
- https://dart.dev/codelabs/null-safety
- https://dart-tutorial.com/null-safety/null-safety-exercise-in-dart/
- https://benzneststudios.com/blog/dart/hello-sound-null-safety-in-dart/


## Slide
- [Null Safety Exercise (Dart).pptx](https://github.com/soonklang/dart-tutorial/files/12752742/Null.Safety.Exercise.Dart.pptx)
- [Null Safety Exercise (Dart) new version.pptx](https://github.com/soonklang/dart-tutorial/files/12877299/Null.Safety.Exercise.Dart.new.version.pptx)
- [Null Safety Exercise (Dart) new version.pdf](https://github.com/soonklang/dart-tutorial/files/12877248/Null.Safety.Exercise.Dart.new.version.pdf)




## Link Vdo
[Null Safety Exercise Vdo](https://youtu.be/103jXEsbooo)
