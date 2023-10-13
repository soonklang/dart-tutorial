# Map in Dart
**Map** หรือที่เรียกกันทั่วไปว่า Dictionary หรือ Hash คือชุดของคู่ **Key-Value** ที่ไม่มีการเรียงลำดับ Maps เชื่อมโยงคีย์เข้ากับค่าบางค่าเพื่อให้เรียกค้นได้ง่าย

>**การใช้ Map ในภาษาอื่น ๆ**
> - ภาษา C ใช้อาร์เรย์เป็นองค์ประกอบและจัดเก็บคู่ Key-Value
> - ภาษา Java มี implementation ต่างๆ มากมายให้เลือกใช้ เช่น HashMap, TreeMap, CachMap, EnumMap ฯลฯ
> - ภาษา Python สามารถใช้ dictionary เพื่อให้ได้ฟังก์ชันการทำงานของคู่ Key-Value
> 
## วิธีการสร้าง Map ในภาษา Dart

สำหรับตัวอย่างนี้จะสร้าง Map สำหรับ String และ String หมายความว่า Key และ Value จะต้องเป็นประเภทของสตริง ซึ่งเราสามารถ Map ที่มีชนิดข้อมูลใดก็ได้ตามที่ต้องการ
```dart
void main(){
	Map<String, String> countryCapital = {
		'USA': 'Washington, D.C.',
		'India': 'New Delhi',
		'China': 'Beijing'
	};
	print(countryCapital);
} 
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing}.</code>
</pre>
</details>

> ***Note*** : *USA, India, China เป็น Key จะต้องไม่ซ้ำกัน*

### วิธีการสร้าง Map ในภาษาอื่น ๆ

 - ภาษา C ตัวอย่างนี้จะใช้อาร์เรย์เพื่อแสดงชื่อประเทศและเมืองหลวง โค้ดจะวนซ้ำอาร์เรย์และแสดงผลประเทศ-เมืองหลวง
```c
#include <stdio.h>
#include <string.h>

int main() {
	char *countryNames[] = {"USA", "India", "China"};
	char *countryCapitals[] = {"Washington, D.C.", "New Delhi", "Beijing"};

	int numCountries = sizeof(countryNames) / sizeof(countryNames[0]);

	for (int i = 0; i < numCountries; i++) {
		printf("%s: %s\n", countryNames[i], countryCapitals[i]);
	}

	return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>USA: Washington, D.C.
India: New Delhi
China: Beijing
</code>
</pre>
</details>

 - ภาษา Java ในตัวอย่างนี้จะใช้คลาส java.util.HashMap เพื่อสร้าง Key-Value Map ซึ่งสามารถเพิ่ม Key-Value โดยใช้ put method

```java
import java.util.HashMap;
import java.util.Map;

public class Main {
	public static void main(String[] args) {
		Map<String, String> countryCapital = new HashMap<>();
		countryCapital.put("USA", "Washington, D.C.");
		countryCapital.put("India", "New Delhi");
		countryCapital.put("China", "Beijing");

		System.out.println(countryCapital);
	}
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA=Washington, D.C., China=Beijing, India=New Delhi}</code>
</pre>
</details>

 - ภาษา Python ในตัวอย่างนี้จะใช้ Dictionary เพื่อให้ได้ฟังก์ชันการทำงานของคู่ Key-Value

```python
	    def main():
		    countryCapital = {
		        'USA': 'Washington, D.C.',
		        'India': 'New Delhi',
		        'China': 'Beijing'
		    }
		    print(countryCapital)

		if __name__ == "__main__":
			main()
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{'USA': 'Washington, D.C.', 'India': 'New Delhi', 'China': 'Beijing'}</code>
</pre>
</details>

## การเข้าถึงค่าจาก Key
เราสามารถค้นหาค่าของ Map ได้จาก Key ของมัน ตัวอย่างต่อไปนี้เราจะแสดงผล Washington, D.C. จาก Key ของมันคือ USA
```dart
    void main(){
		Map<String, String> countryCapital = {
		  'USA': 'Washington, D.C.',
		  'India': 'New Delhi',
		  'China': 'Beijing'
		};
		print(countryCapital["USA"]);
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Washington, D.C.</code>
</pre>
</details>

### วิธีการเข้าถึงค่าในภาษาอื่น ๆ
 - ภาษา C ใช้อาร์เรย์เพื่อจัดเก็บคู่ประเทศ-เมืองหลวง จากนั้นวนซ้ำอาร์เรย์เพื่อค้นหาเมืองหลวงที่สอดคล้องกับประเทศที่ต้องการ
 
```c
#include <stdio.h>
#include <string.h>

struct CountryCapital {
	const char *country;
	const char *capital;
};
int main() {
	struct CountryCapital countryCapitals[] = {
		{"USA", "Washington, D.C."},
		{"India", "New Delhi"},
		{"China", "Beijing"}
	};
	int numCountries = sizeof(countryCapitals) / sizeof(countryCapitals[0]);

	const char *searchCountry = "USA";
	const char *foundCapital = NULL;

	for (int i = 0; i < numCountries; i++) {
		if (strcmp(countryCapitals[i].country, searchCountry) == 0) {
		    foundCapital = countryCapitals[i].capital;
	        break;
		}
	}

	if (foundCapital) {
		printf("%s\n", foundCapital);
	} else {
		printf("Country not found.\n");
	}

	return 0;
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Washington, D.C.</code>
</pre>
</details>

 - ภาษา Java จะใช้ get method เพื่อดึงค่าที่ต้องการ
 
```java
import java.util.HashMap;
import java.util.Map;

public class Main {
	public static void main(String[] args) {
		Map<String, String> countryCapital = new HashMap<>();
		countryCapital.put("USA", "Washington, D.C.");
		countryCapital.put("India", "New Delhi");
		countryCapital.put("China", "Beijing");
        
		System.out.println(countryCapital.get("USA"));
	}
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Washington, D.C.</code>
</pre>
</details>

 - ภาษา Python มีวิธีการเข้าถึงค่าจาก Key คล้ายกับภาษา Dart
 
```python
def main():
	countryCapital = {
		'USA': 'Washington, D.C.',
		'India': 'New Delhi',
		'China': 'Beijing'
	}
	print(countryCapital["USA"])

if __name__ == "__main__":
	main()
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Washington, D.C.</code>
</pre>
</details>

## คุณสมบัติของ Map ในภาษา Dart
| คุณสมบัติ |การทำงาน  |
|--|--|
| **keys** | เพื่อรับ Key ทั้งหมด |
|**values**| เพื่อรับ Value ทั้งหมด |
|**isEmpty**| return ค่า True หรือ False |
|**isNotEmpty**| return ค่า True หรือ False |
|**length**| มันจะ return ความยาวของ map |

### ตัวอย่างคุณสมบัติ Map ในภาษา Dart
ตัวอย่างนี้ค้นหา Key/Value ทั้งหมดของ Map องค์ประกอบแรกและองค์ประกอบสุดท้าย ตรวจสอบว่าว่างเปล่าหรือไม่ และค้นหาความยาวขององค์ประกอบ

```dart
void main() {
	Map<String, double> expenses = {
		'sun': 3000.0,
		'mon': 3000.0,
		'tue': 3234.0,
	};
	print("All keys of Map: ${expenses.keys}");
	print("All values of Map: ${expenses.values}");
	print("Is Map empty: ${expenses.isEmpty}");
	print("Is Map not empty: ${expenses.isNotEmpty}");
	print("Length of map is: ${expenses.length}");
}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>All keys of Map: (sun, mon, tue)
All values of Map: (3000, 3000, 3234)
Is Map empty: false
Is Map empty: true
Length of map is: 3</code>
</pre>
</details>

## การเพิ่มองค์ประกอบลงใน Map
ตัวอย่างนี้จะเพิ่ม Key เป็น 'Japan' และ Value เป็น 'Tokio'

```dart
	void main(){
		Map<String, String> countryCapital = {
			'USA': 'Washington, D.C.',
			'India': 'New Delhi',
			'China': 'Beijing'
	};
		// Adding New Item
		countryCapital['Japan'] = 'Tokio';
		print(countryCapital);
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing, Japan: Tokio}</code>
</pre>
</details>

### การเพิ่มองค์ประกอบในภาษาอื่น ๆ

 - ภาษา C จะเพิ่มรายการใหม่ ("Japan", "Tokio") โดยการขยายอาร์เรย์
 
```c
	    #include <stdio.h>
		#include <string.h>

		struct CountryCapital {
		    const char *country;
		    const char *capital;
		};

		int main() {
		    struct CountryCapital countryCapitals[] = {
		        {"USA", "Washington, D.C."},
		        {"India", "New Delhi"},
		        {"China", "Beijing"}
	    };

	    int numCountries = sizeof(countryCapitals) / sizeof(countryCapitals[0]);

	    // Adding a new item
	    struct CountryCapital newCountryCapital = {"Japan", "Tokio"};
	    countryCapitals[numCountries] = newCountryCapital;
	    numCountries++;

	    printf("Updated Country-Capital List:\n");
	    for (int i = 0; i < numCountries; i++) {
	        printf("%s: %s\n", countryCapitals[i].country,countryCapitals[i].capital);
	    }

	    return 0;
		}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing, Japan: Tokio}</code>
</pre>
</details>

 - ภาษา Java จะใช้ put method เพื่อเพิ่มคู่ Key-Value

```java
	    import java.util.HashMap;
		import java.util.Map;

		public class Main {
		    public static void main(String[] args) {
		        Map<String, String> countryCapital = new HashMap<>();
		        countryCapital.put("USA", "Washington, D.C.");
		        countryCapital.put("India", "New Delhi");
		        countryCapital.put("China", "Beijing");

		        // Adding a new item
		        countryCapital.put("Japan", "Tokio");
		        System.out.println(countryCapital);
		    }
		}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing, Japan: Tokio}</code>
</pre>
</details>

 - ภาษา Python

```python
	    def main():
		    countryCapital = {
	        'USA': 'Washington, D.C.',
	        'India': 'New Delhi',
	        'China': 'Beijing'
	    }
		    #Adding a new item
		    countryCapital['Japan'] = 'Tokio'
		    print(countryCapital)

		if __name__ == "__main__":
		    main()
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing, Japan: Tokio}</code>
</pre>
</details>

## การอัปเดตองค์ประกอบของ Map
ตัวอย่างนี้ เราต้องการอัปเดต ค่า Value ของ Key 'USA' จาก Value 'Nothing' เป็น 'Washington, D.C.'

```dart
    void main(){
		Map<String, String> countryCapital = {
		  'USA': 'Nothing',
		  'India': 'New Delhi',
		  'China': 'Beijing'
		};
		  // Updating Item
		  countryCapital['USA'] = 'Washington, D.C.';
		  print(countryCapital);
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing}</code>
</pre>
</details>

### การอัปเดตองค์ประกอบในภาษาอื่น ๆ

 - ภาษา C
 
```c
	    #include <stdio.h>
		#include <string.h>

		struct CountryCapital {
			const char *country;
		    const char *capital;
		};

		int main() {
		    struct CountryCapital countryCapitals[] = {
		        {"USA", "Nothing"},
		        {"India", "New Delhi"},
		        {"China", "Beijing"}
		    };

		    int numCountries = sizeof(countryCapitals) / sizeof(countryCapitals[0]);

		    // Updating an item
		    const char *targetCountry = "USA";
		    const char *newCapital = "Washington, D.C.";

		    for (int i = 0; i < numCountries; i++) {
				 if (strcmp(countryCapitals[i].country, targetCountry) == 0) {
	            countryCapitals[i].capital = newCapital;
	            break;
		    }
	    }

		    printf("Updated Country-Capital List:\n");
		    for (int i = 0; i < numCountries; i++) {
		        printf("%s: %s\n", countryCapitals[i].country,countryCapitals[i].capital);
		    }

		    return 0;
		}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing}</code>
</pre>
</details>

- ภาษา Java

```java
	    import java.util.HashMap;
		import java.util.Map;

		public class Main {
		    public static void main(String[] args) {
		        Map<String, String> countryCapital = new HashMap<>();
		        countryCapital.put("USA", "Nothing");
		        countryCapital.put("India", "New Delhi");
		        countryCapital.put("China", "Beijing");

		        // Updating an item
		        countryCapital.put("USA", "Washington, D.C.");

		        System.out.println(countryCapital);
		    }
		}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing}</code>
</pre>
</details>

- ภาษา Python

```python
	    def main():
		    countryCapital = {
		        'USA': 'Nothing',
		        'India': 'New Delhi',
		        'China': 'Beijing'
		    }

		    #Updating an item
		    countryCapital['USA'] = 'Washington, D.C.'

		    print(countryCapital)

		if __name__ == "__main__":
		    main()
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{USA: Washington, D.C., India: New Delhi, China: Beijing}</code>
</pre>
</details>

## Map Methods ในภาษา Dart
|คุณสมบัติ|การทำงาน  |
|--|--|
| **keys.toList()** | แปลง Key Maps ทั้งหมดเป็น List |
| **values.toList()** | แปลง Value Maps ทั้งหมดเป็น 	List|
| **containsKey(‘key’)** | Return ค่า true หรือ false|
| **containsValue(‘value’)** | Return ค่า true หรือ false|
| **clear()** | ลบองค์ประกอบทั้งหมดออกจาก Map|
| **removeWhere()** | ลบองค์ประกอบทั้งหมดออกจาก Map หากเงื่อนไขถูกต้อง|

### แปลง Keys & Values เป็น List

```dart
    void main() {
		Map<String, double> expenses = {
		    'sun': 3000.0,
		    'mon': 3000.0,
		    'tue': 3234.0,
		};
  
		// Without List
		print("All keys of Map: ${expenses.keys}");
		print("All values of Map: ${expenses.values}");
 
		// With List
		print("All keys of Map with List: ${expenses.keys.toList()}");
		print("All values of Map with List: ${expenses.values.toList()}");
  
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>All keys of Map: (sun, mon, tue)
All values of Map: (3000, 3000, 3234)
All keys of Map with List: [sun, mon, tue]
All values of Map with List: [3000, 3000, 3234
</code>
</pre>
</details>

### ตรวจสอบว่ามี Key/Value นั้นหรือไม่

```dart
    void main() {
 
	Map<String, double> expenses = {
	    'sun': 3000.0,
	    'mon': 3000.0,
	    'tue': 3234.0,
	};
  
	  // For Keys
	  print("Does Map contain key sun: ${expenses.containsKey("sun")}");
	  print("Does Map contain key abc: ${expenses.containsKey("abc")}");
 
	  // For Values
	  print("Does Map contain value 3000.0: ${expenses.containsValue(3000.0)}");
	  print("Does Map contain value 100.0: ${expenses.containsValue(100.0)}");
  
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Does Map contain key sun: true
Does Map contain key abc: false
Does Map contain value 3000.0: true
Does Map contain value 100.0: false
</code>
</pre>
</details>

### การลบ item ออกจาก Map

```dart
    void main(){
		Map<String, String> countryCapital = {
		  'USA': 'Nothing',
		  'India': 'New Delhi',
		  'China': 'Beijing'
		};
  
		countryCapital.remove("USA");
		print(countryCapital);
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{India: New Delhi, China: Beijing}
</code>
</pre>
</details>

### วนซ้ำองค์ประกอบของ Map

```dart
    void main(){
		Map<String, dynamic> book = {
		    'title': 'Misson Mangal',
		    'author': 'Kuber Singh',
		    'page': 233
		};
  
	 // Loop Through Map
	 for(MapEntry book in book.entries){
	    print('Key is ${book.key}, value ${book.value}');
	  }
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>Key is title, value Misson Mangal
Key is author, value Kuber Singh
Key is page, value 233
</code>
</pre>
</details>

### ลบ Where In Dart Map
ในตัวอย่างนี้ จะรับนักเรียนที่มีคะแนนมากกว่าหรือเท่ากับ 32 โดยใช้ where method

```dart
    void main() {
		Map<String, double> mathMarks = {
		    "ram": 30,
		    "mark": 32,
		    "harry": 88,
		    "raj": 69,
		    "john": 15,
		};
		mathMarks.removeWhere((key, value) => value < 32);
		print(mathMarks);
	}
```
<details>
<summary><strong>Output</strong></summary>
<pre>
<code>{mark: 32.0, harry: 88.0, raj: 69.0}
</code>
</pre>
</details>

## ตัวอย่างเพิ่มเติมการ Map ในภาษา Dart
 - สามารถประกาศ Map โดยใช้ไวยากรณ์ตัวอักษรสั้นๆ หรือคุณสามารถใช้ตัวสร้างแบบดั้งเดิม:
 
```dart
// Maps often use strings as keys.
var hawaiianBeaches = {
  'Oahu': ['Waikiki', 'Kailua', 'Waimanalo'],
  'Big Island': ['Wailea Bay', 'Pololu Beach'],
  'Kauai': ['Hanalei', 'Poipu']
};

// Maps can be built from a constructor.
var searchTerms = Map();

// Maps are parameterized types; you can specify what
// types the key and value should be.
var nobleGases = Map<int, String>();
```
- สามารถเพิ่ม รับ และตั้งค่ารายการ Map โดยใช้`remove()` เพื่อลบคีย์และค่าออกจาก Map

 ```dart
var nobleGases = {54: 'xenon'};

// Retrieve a value with a key.
assert(nobleGases[54] == 'xenon');

// Check whether a map contains a key.
assert(nobleGases.containsKey(54));

// Remove a key and its value.
nobleGases.remove(54);
assert(!nobleGases.containsKey(54));
```
- สามารถดึงค่าทั้งหมดหรือคีย์ทั้งหมดจาก Map:

 ```dart
var hawaiianBeaches = {
  'Oahu': ['Waikiki', 'Kailua', 'Waimanalo'],
  'Big Island': ['Wailea Bay', 'Pololu Beach'],
  'Kauai': ['Hanalei', 'Poipu']
};

// Get all the keys as an unordered collection
// (an Iterable).
var keys = hawaiianBeaches.keys;

assert(keys.length == 3);
assert(Set.from(keys).contains('Oahu'));

// Get all the values as an unordered collection
// (an Iterable of Lists).
var values = hawaiianBeaches.values;
assert(values.length == 3);
assert(values.any((v) => v.contains('Waikiki')));
```
- หากต้องการตรวจสอบว่ามี Key map หรือไม่ ให้ใช้`containsKey()` เนื่องจาก Value map อาจเป็นค่าว่างได้ จึงไม่สามารถพึ่งพาเพียงการรับค่าของคีย์และการตรวจสอบค่าว่างเพื่อพิจารณาว่ามีคีย์อยู่หรือไม่

 ```dart
var hawaiianBeaches = {
  'Oahu': ['Waikiki', 'Kailua', 'Waimanalo'],
  'Big Island': ['Wailea Bay', 'Pololu Beach'],
  'Kauai': ['Hanalei', 'Poipu']
};

assert(hawaiianBeaches.containsKey('Oahu'));
assert(!hawaiianBeaches.containsKey('Florida'));
```
- ใช้`putIfAbsent()`วิธีนี้เมื่อต้องการกำหนดค่าให้กับคีย์ก็ต่อเมื่อคีย์ไม่มีอยู่ใน Map เท่านั้น ต้องระบุฟังก์ชันที่ส่งคืนค่า

 ```dart
var teamAssignments = <String, String>{};
teamAssignments.putIfAbsent('Catcher', () => pickToughestKid());
assert(teamAssignments['Catcher'] != null);
```

## เปรียบเทียบการ Map ในภาษา Dart กับภาษาอื่น ๆ
> - **Dart** และ **Python** ให้โค้ดที่กระชับและอ่านง่าย มีการรองรับ Map/Dictionary ในตัว
> - **Java** มีความหลากหลายของคลาส `Map` เพื่อตอบสนองกับความต้องการในการจัดเก็บและจัดการข้อมูล.
> - **C** ขาดการรองรับ Map ในตัว ส่งผลให้มีการจัดการอาเรย์แบบ manual และมีแนวโน้มที่จะเกิดข้อผิดพลาดมากขึ้น

## อ้างอิง
- https://dart-tutorial.com/collections/map-in-dart/
- https://dart.dev/guides/libraries/library-tour#transforming-collections
- https://www.geeksforgeeks.org/dart-collections/
- https://www.tutorialspoint.com/dart_programming/dart_programming_collection.htm

## Link Video
https://www.youtube.com/watch?v=jPbbMs8yCWs

## Slide
- [Map in Dart.pdf](https://github.com/PraeJi/File/blob/main/Map%20in%20Dart.pdf?raw=true)
- [Map in Dart v2.pdf](https://github.com/PraeJi/File/blob/main/Map%20in%20Dart%20v2.pdf?raw=true)
