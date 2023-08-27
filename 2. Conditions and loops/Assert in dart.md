# Assert in Dart
## Assert
  เป็นคำสั่งที่ใช้ในการตรวจสอบข้อผิดพลาด(Debug) หากเงื่อนไข boolean ในการทดสอบเป็นเท็จ(flase)จะหยุดการทำงาน
## Syntax
  **1) assert(condition);**
  
  ```dart
  void main(){
    int x = 20;
    int y = 10;
    assert(x>y);
  }
```

>จากตัวอย่าง assert จะใช้ตรวจสอบว่า x>y เป็นจริง จึงไม่แสดงอะไรออกมา
<details>
  <summary><strong>Output</strong></summary>
  <pre><code>Uncaught Error: Assertion failed</code></pre>
</details>
