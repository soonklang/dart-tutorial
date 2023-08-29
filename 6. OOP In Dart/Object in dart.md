# Object in dart
**การเขียนโปรแกรมเชิงวัตถุ** Object(วัตถุ) คือ หน่วยของcode และข้อมูลในตัวเอง โดยจะถูกสร้างขึ้นจากเทมเพลสที่เรียกว่า Class(คลาส)  **object** ประกอบด้วย **properties(ตัวแปร)** และ**methods(ฟังก์ชัน)** วัตถุ คือ instanceของclass  
**ตัวอย่าง** objectจักรยาน อาจมีattributes(คุณลักษณะ)ต่างๆ เช่น **color(สี)** , **size(ขนาด)** , **current speed(ความเร็วปัจจุบัน)** อาจมีmethod เช่น changeGear , PadalFaster และ Brake

# Instantiation
การเขียนโปรแกรมเชิงวัตถุ **การสร้าง instantiation** คือ กระบวนการสร้างinstanceของclass หรือจะบอกได้ว่าการสร้าง instantiation เป็นกระบวนการสร้างobjectของclass เช่น หากคุณมีclassชื่อ **Bicycle** จะสามารถสร้างobjectของclassชื่อ **Bicycle** ได้

# Declaring Object In Dart
เมื่อทำการสร้าง class แล้วจะต้องประกาศobject คุณสามารถประกาศ object โดยใช้ syntax ต่อไปนี้:

# Syntax
```
ClassName objectName = ClassName();
```

# ตัวอย่างที่ 1: Declaring An Objet In Dart
ตัวอย่างด้านล่างนี้ มีจะมี class **Bicycle** มี properties 3 ประการ: **color** , **size** และ**currentSpeed** ใน class จะมี 2 method คือ **changeGear** ซึ่งเป็นการเปลี่ยนเกียร์ของจักรยาน และ **display** จะพิมพ์ค่า properties ทั้งสามออกมา นอกจจากนี้ยังมี object ของ class**Bicycle** ที่calledเรียก**bicycle**
```
    class Bicycle {
      String? color;
      int? size;
      int? currentSpeed;
    
      void changeGear(int newValue) {
        currentSpeed = newValue;
      }
    
      void display() {
        print("Color: $color");
        print("Size: $size");
        print("Current Speed: $currentSpeed");
      }
    }

    void main(){
        // Here bicycle is object of class Bicycle. 
        Bicycle bicycle = Bicycle();
        bicycle.color = "Red";
        bicycle.size = 26;
        bicycle.currentSpeed = 0;
        bicycle.changeGear(5);
        bicycle.display();
    }
```

# ตัวอย่างที่ 2: Declaring Animal Class Object In dart


# ตัวอย่างที่ 3: Declaring Car Class Object In dart


# Keypoint


# Difference Between Dart and Java and Python


# Reference
