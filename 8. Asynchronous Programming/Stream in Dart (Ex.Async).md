# Stream in Dart (Ex.Async)😧
## Dart
### Example Of async
```dart
Future<int> doSomeLongTask() async {
  await Future.delayed(const Duration(seconds: 2));
  return 21;
}main() async {
  int result = await doSomeLongTask();
  print(result); // prints '42' after waiting 2 second
}
   ```
Output

```dart
21
   ```

### Example Of sync

```dart
Stream<int> countForOneMinute() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
} main() async {
  await for (int i in countForOneMinute()) {
    print(i); // prints 1 to 5, one integer per second
  }
}
   ```
Output

```dart
1
2
3
4
5
   ```

## C

### Example Of async

ในภาษา C แท้จริงไม่มีระบบ Asynchronous แบบ Native อย่างที่มีในภาษาอื่น ๆ เช่น Dart หรือ Java โดยตรง ดังนั้นการจัดการกับ Asynchronous ใน C จะต้องใช้เทคนิคและเครื่องมือที่อยู่นอกเหนือจากภาษามาช่วย โดยทั่วไปแล้วจะใช้การทำงานแบบ Thread และการจัดการกับเวลาเพื่อจำลองการทำงานแบบ Asynchronous

## Java

### Example Of async

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
Output

```dart
Thread is running
   ```

## Python

### Example Of async

```dart
import asyncio
async def do_task(task_name):
    print(f"Start {task_name}")
    await asyncio.sleep(2)  # Simulate some asynchronous task
    print(f"End {task_name}")
async def main():
    task1 = do_task("Task 1")
    task2 = do_task("Task 2")
    await asyncio.gather(task1, task2)
asyncio.run(main())
```
Output
```dart
Start Task 1
End Task 1
```



