# Class and Objects in Dart


# Class คืออะไร ?
Class  จะเปรียบเสมือนกับ Blueprint หรือแบบแปลนสำหรับสร้าง Object แล้ว
Class ยังเป็นตัวกำหนด Properties และ Mehtods ของ Object
ถ้าอยากรู้เกี่ยวกับ Class มากขึ้นให้ไปที่หัวข้อ [Class in Dart](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Class%20in%20Dart.md)

# Object คืออะไร ?
Object คือตัวอย่างของ Class คุณสามารถสร้างได้หลาย Object ใน Class เดียวกัน
ถ้าอยากรู้เกี่ยวกับ Object มากขึ้นให้ไปที่หัวข้อ [Objects in Dart](https://github.com/soonklang/dart-tutorial/blob/main/6.%20OOP%20In%20Dart/Object%20in%20dart.md)

# ตัวอย่าง Class และ Object ในภาษา Dart
ตัวอย่างข้างล่างนี้จะมี Class Animal มี properties 3 อย่าง คือ
weight(น้ำหนัก) , height(ส่วนสูง) และ calbmi(ค่า bmi) และ Class จะมี method ชื่อ calculatorbmi
ซึ่งจะพิมพ์ว่าค่า bmi อยู่ในเกณฑ์ไหน

```dart
class Bmi{
  double? weight;
  double? height;
  double? calbmi;

  void calculatorbmi(){
     calbmi = weight!/(height!/100 * height!/100);
    if(calbmi! > 30){
     print("น้ำหนักอยู่ในเกณฑ์ อ้วนมาก"); 
    }else if(calbmi! >= 25){
      print("น้ำหนักอยู่ในเกณฑ์ อ้วน"); 
    }else if(calbmi! >=18.6){
      print("น้ำหนักอยู่ในเกณฑ์ สมส่วน");
    }else{
      print("น้ำหนักอยู่ในเกณฑ์ ผอมเกินไป");
    }
  }
}

void main() {
  Bmi bmi = Bmi(); 
  bmi.weight = 80;
  bmi.height = 180;
  bmi.calculatorbmi();
}


```

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>น้ำหนักอยู่ในเกณฑ์ สมส่วน</code></pre>
</details>

# ตัวอย่าง 2: หาพื้นที่สี่เหลี่ยมผืนผ้าโดยใช้ Class และ Objects
ตัวอย่างข้างล่างนี้จะมี Class Rectangle(สี่เหลี่ยมผืนผ้า) มี properties 2 อย่าง คือ
length(ความยาว) และ breadth(ความกว้าง) และ Class จะมี method ชื่อ area(พื้นที่)
ซึ่งจะพิมพ์ค่าพื้นของสี่เหลี่ยมผืนผ้า
```dart
class Rectangle{
  //properties of rectangle
  double? length;
  double? breadth;
  
  //functions of rectangle
  double area(){
    return length! * breadth!;
  }
}

void main(){
  //object of rectangle created
  Rectangle rectangle = Rectangle();
  
  //setting properties for rectangle
  rectangle.length=10;
  rectangle.breadth=5;
  
  //functions of rectangle called
  print("Area of rectangle is ${rectangle.area()}.");
}
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Area of rectangle is 50.</code></pre>
</details>

# ตัวอย่าง 2: หาค่าดอกเบี้ย แบบง่ายๆ โดยใช้ Class และ Objects
ตัวอย่างข้างล่างนี้จะมี Class SimpleInterest(คำนวนดอกเบี้ยง่ายๆ) มี properties 3 อย่าง คือ
principal(เงินต้น) ,rate(อัตราดอกเบี้ย) และtime(ระยะเวลา) และ Class จะมี method
interest(ดอกเบี้ย) ซึ่งจะพิมพ์ค่าคำนวนดอกเบี้ย แบบวิธีง่ายๆ
```dart 
class SimpleInterest{
  //properties of simple interest
  double? principal;
  double? rate;
  double? time;
  
  //functions of simple interest
  double interest(){
    return (principal! * rate! * time!)/100;
  }
}
void main(){
  //object of simple interest created
  SimpleInterest simpleInterest = SimpleInterest();
  
  //setting properties for simple interest
  simpleInterest.principal=1000;
  simpleInterest.rate=10;
  simpleInterest.time=2;
  
  //functions of simple interest called
  print("Simple Interest is ${simpleInterest.interest()}.");
  }
  ```
  
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Simple Interest is 200.</code></pre>
</details>


# ตัวอย่างของ Class กับ Object ในภาษา Python และ Java โดยจะใช้ชื่อ Class ว่า Bmi

# Python
```python
class Bmi:
  def __init__(self):
    self.calbmi = 0
    self.weight = 0
    self.height = 0

  def calculatorbmi(self):
    self.calbmi = self.weight/(self.height/100 * self.height/100)
    if self.calbmi > 30:
     print("น้ำหนักอยู่ในเกณฑ์ อ้วนมาก")
    elif self.calbmi >= 25:
      print("น้ำหนักอยู่ในเกณฑ์ อ้วน")
    elif self.calbmi >=18.6:
      print("น้ำหนักอยู่ในเกณฑ์ สมส่วน")
    else:
      print("น้ำหนักอยู่ในเกณฑ์ ผอมเกินไป")



bmi = Bmi()
bmi.weight = 80
bmi.height = 180
bmi.calculatorbmi()
```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>
     น้ำหนักอยู่ในเกณฑ์ สมส่วน </code></pre>
</details>

# Java
```java
class BMI {
        double weight;
        double height;
        double calbmi;
        void calculatorbmi(){
            calbmi = weight/((height/100) * (height/100));
            if(calbmi > 30){
                System.out.println("น้ำหนักอยู่ในเกณฑ์ อ้วนมาก");
            }else if(calbmi >= 25){
                System.out.println("น้ำหนักอยู่ในเกณฑ์ อ้วน");
            }else if(calbmi >= 18.6){
                System.out.println("น้ำหนักอยู่ในเกณฑ์ สมส่วน");
            }else{
                System.out.println("น้ำหนักอยู่ใน้เกณฑ์ ผอมเกินไป");    
                }
        }
}
class Main{
    public static void main(String[] args){
        BMI bmi = new BMI();
        bmi.weight = 80;
        bmi.height = 180;
        bmi.calculatorbmi();
    }
}

```
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>น้ำหนักอยู่ในเกณฑ์ สมส่วน </code></pre>
</details>

# Reference
https://dart-tutorial.com/object-oriented-programming/class-and-objects-in-dart/<br>
https://www.geeksforgeeks.org/<br>

# Video
[Video](https://www.youtube.com/watch?v=7nq2mcbd6xc)

# Slide
[Slide.pptx](https://github.com/soonklang/dart-tutorial/files/12889140/Slide.pptx)<br>

[SCSU-Slide-6.pdf](https://github.com/soonklang/dart-tutorial/files/12888573/SCSU-Slide-6.pdf)<br>


