# Function

1. Basic Function Declaration

```dart
void main(){
 printName();
}

// <dataTypes> functionName (){}
void printName(){
 print("Dart");
}
```

2. Functions with Return Values

```dart
void main() {
  print(printName());
}

String printName() {
  // return ("Dart".length).toString();
  return "Dart";
}
```

3. Function with Different Return Types

```dart
void main() {
  int number1 = getNumber();
  // final/var number1 = getNumber(); // but not const because not constant value
  // String number2 = getNumber2(); // runTime (UnCaught Error)
  print(number1);
  print(number2);
}

int getNumber() {
  return 12;
}

dynamic getNumber2() {
  return 12;
}

```

4. Functions Returning Tuples (Records)

```dart
void main() {
  var number1 = getNameAndAgeAndIsAdult();
  print(number1);       // (Dart, 12, true)
  print(number1.$1);    // Dart
  print(number1.$2);    // 12
  print(number1.$3);    // true
}

// returning 2 dataTypes
// dart 3 add support for `record` in other language its know as `tuple`
(String, int, bool) getNameAndAgeAndIsAdult() {
  return ("Dart", 12, true);
}
```

5. Destructuring Tuples (Records)

```dart
void main() {
  var (name, age, isAdult) = getNameAndAgeAndIsAdult();
  print('my name is $name and age is $age and above 18 is $isAdult');
}

(String, int, bool) getNameAndAgeAndIsAdult() {
  return ("Dart", 12, true);
}

```

6. Functions Returning Nullable Types

```dart
void main() {
  var name = printName();
  print(name);
}

// String printName() {
//   return "dart";
// }

String? printName() {
  return null;
}


```

7. Functions with Name Parameters and Arguments

```dart
void main() {
  String name = "Dart language";
  printName(name); // parameters
  print(name);
}

// arguments -> datatype variableName
void printName(String name) {
  name = 'dart';
  print(name);
}

```

```dart
void main() {
  String name = "Dart language";
  printName(name: name, age: 12, greeting: "hello");
  printName(age: 12, name: name, greeting: "hello");
  printName(greeting: "hello", age: 12, name: name);
}

void printName(
    {required String name,int? age, required String greeting}) {
  print('$name, $age, $greeting');
}
```

8. Functions with Positional and Named Parameters

```dart
void main() {
  printName(12, false, name: "Dart language", greeting: "hello");
}

void printName(int? age, bool isAdult,
    {required String name, required String greeting}) {
  print('$age, $isAdult, $name, $age, $greeting');
}

```

9. Functions Returning Tuples with Destructuring

```dart
void main() {
  final stuff = printStuff();
  var stuff1 = printStuff();
  (int, String) stuff2 = printStuff();
  final (age, name) = printStuff();

  print(stuff);         // (12, dart)
  print(stuff1);        // (12, dart)
  print(stuff2);        // (12, dart)
  print('$age, $name'); //  12, dart
}

(int, String) printStuff() {
  return (12, "dart");
}

```

10. Functions Returning Named Tuples (Records)

```dart
void main() {
  final stuff = printStuff();
  print(stuff);       // (age: 12, name: dart)
  print(stuff.age);   // 12
  print(stuff.name);  // dart
}

({int age, String name}) printStuff() {
  return (age: 12, name: "dart");
}
```

11. Anonymous Functions

```dart
void main() {
  final stuff = printStuff();

  print(stuff()); // null

//   print(() {
//     print(
//         "dart 2"); // Closure: () => Null from: () => {   core.print("dart 2"); }
//   });

  print(() {
    print("dart 2"); // dart 2
  }()); // null
}

Function printStuff() {
  return () {
    print("dart 1"); // dart 1
  };
}

// o/p :
        // dart 1
        // null
        // dart 2
        // null
```

12. Arrow Functions

```dart
void main() {
  final stuff = printStuff();
  print(stuff);
}

// void printStuff() => print("dart");
String printStuff() => "dart";
```
