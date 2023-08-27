# Assert in Dart
## Assert
เป็นคำสั่งที่ใช้ในการตรวจสอบข้อผิดพลาด (Debug) หากเงื่อนไข boolean ในการทดสอบเป็นเท็จ (flase) จะหยุดการทำงาน
## Syntax
  **1) assert(condition);**
  
  ```dart
  void main(){
    int x = 20;
    int y = 10;
    assert(x>y);
  }
```

>จากตัวอย่าง assert ตรวจสอบว่า x>y เป็นจริง

<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Uncaught Error: Assertion failed</code></pre>
</details>

**2) assert(condition, "message");**

```dart
void main(){
  int x = 5;
  int y = 10;
  assert(x>y, "x should be greater then y");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x>y เป็นเท็จ

<details>
  <summary><strong>Output1</strong></summary>
  <pre><code>Uncaught Error: Assertion failed: "x should be greater then y"</code></pre>
</details>

```dart
void main(){
  int x = 20;
  int y = 10;
  assert(x>y, "x should be greater then y");
print("Program continues after then assert");
}
```

>จากตัวอย่าง assert ตรวจสอบว่า x>y เป็นจริง

<details>
  <summary><strong>Output2</strong></summary>
  <pre><code>Program continues after then assert</code></pre>
</details>

### หมายเหตุ;

**condition:** ค่าที่ต้องเป็นจริงเพื่อให้โปรแกรมทำงานต่อไป ถ้าเงื่อนไขเป็นเท็จจะหยุดทำงาน

**message:** ข้อความที่สามารถระบุได้ เพื่ออธิบายเงื่อนไขที่ถูกตรวจสอบ ถ้าเงื่อนไขเป็นเท็จจึงถูกแสดง



















