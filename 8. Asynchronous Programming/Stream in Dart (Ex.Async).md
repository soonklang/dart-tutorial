# Stream in Dart (Ex.Async)😧
<h2>Example Of async</h2>

## Dart

```dart
Future<int> doSomeLongTask() async {
  await Future.delayed(const Duration(seconds: 2));
  return 21;
}main() async {
  int result = await doSomeLongTask();
  print(result); // prints '42' after waiting 2 second
}
   ```
<h3>Output</h3>

```dart
21
   ```

## C
ในภาษา C แท้จริงไม่มีระบบ Asynchronous แบบ Native อย่างที่มีในภาษาอื่น ๆ เช่น Dart หรือ Java โดยตรง ดังนั้นการจัดการกับ Asynchronous ใน C จะต้องใช้เทคนิคและเครื่องมือที่อยู่นอกเหนือจากภาษามาช่วย โดยทั่วไปแล้วจะใช้การทำงานแบบ Thread และการจัดการกับเวลาเพื่อจำลองการทำงานแบบ Asynchronous

## Java
```dart
class ThreadClass extends Thread{
    public void run(){
    System.out.println("Thread is running");
    }
}
class AsyncExample {
    public static void main(String[] args) {
        ThreadClass thread1 = new ThreadClass();
        thread1.start(); 
    }
}
```
<h3>Output</h3>

```dart
Thread is running
   ```
