# Factory Constructor in Dart (factory)
```dart
class MyClass {
  // Regular instance variables
  
  // Regular constructor
  MyClass(/* parameters */) {
    // Constructor logic
  }
  
  // Factory constructor
  factory MyClass.factoryConstructor(/* parameters */) {
    // Factory constructor logic
    return MyClass(/* initialize instance */);
  }
  
  // Other methods and members
```
