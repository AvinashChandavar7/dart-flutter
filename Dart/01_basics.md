# DART

## Basics

### 1. Empty `main` Function

```dart
void main(){
}
```

- **No error**: This just defines an empty program.

### 2. `print()` Without Argument

```dart
void main(){
  print();
}

// 1 positional argument expect... line 2, col 7
// Try adding the missing argument.
```

- **Error**: `print` expects something to print (an argument).

### 3. Incorrect Usage of `print`

```dart
void main(){
  print(Hello,World);
}

//Undefined name 'Hello'.Try correcting the name to one that is defined, or defining the name.

//Undefined name 'World'.Try correcting the name to one that is defined, or defining the name.

//Too many positional arguments: 1 expected, but 2 found.Try removing the extra arguments.

```

- **Errors**:
  - `Hello` and `World` should be in quotes (`"Hello, World"`).
  - `print` only takes one argument.

### 4. Correct `print` Usage and Operations

```dart
 void main() {
  print("Hello, World");     // Hello,World
  print('Hello, World');     // Hello,World
  print(3);                // Prints the number 3.
  print(3 + 2 - 2 * 2 / 4); // Prints the result of the expression: 4.
  print('3' + '2');        // (+)Concatenates strings: "32".
  print('3' + 2);           // The argument type 'int' cant be assigned to the parameter type 'String'.
  print('3' * 2);          // 33 => 3 is printed 2 times
  print(75 / (5 + 2));     // Dart follows the BODMAS : 10.714285714285714.
}
```

---

## Variables

### without variables

```dart
void main() {
  // first value
  print(19);      // 19

  // second value
  print(5);       // 5

  print(19 * 5); // 95
  print(19 + 5); // 24
  print(19 - 5); // 14
}

```

### with variables

1. Integer (int)

- Storing integer values in variables for reuse

```dart
void main() {
  // <data types> <variablesName> = value;

  int firstValue = 19;
  int secondValue = 5;

  // first value
  print(firstValue);      // firstValue

  // second value
  print(secondValue);       // 5

  print(firstValue * secondValue); // 95
  print(firstValue + secondValue); // 24
  print(firstValue - secondValue); // 14
}
```

2. Double (double)

- Using double for decimal numbers.

```dart
void main() {
  // <data types> <variablesName> = value;

  double firstValue = 19.5;
  double secondValue = 5.5;

  // first value
  print(firstValue);      // 19.5

  // second value
  print(secondValue);       // 5.5

  print(firstValue * secondValue); // 107.25
  print(firstValue + secondValue); // 25
  print(firstValue - secondValue); // 14
}
```

3. String (String)

- Storing text in a String variable.

```dart
void main() {
  String greeting = 'Hello world';
  print(greeting); // Hello world
}

```

4. Boolean (bool)

```dart
void main() {
  bool isAdult = true;
  print(isAdult); // true
}
```

5. Dynamic (dynamic) (and General Not Recommended)

- can hold any type, and can't access to properties.
- but it's generally not recommended.

```dart
void main() {
  dynamic someValue = true;
  print(someValue); // true
  print(someValue.runtimeType); // boolean
}
```

### Short Hands

- Shortcuts like +=, -=, \*=, and /= simplify operations on variables.

```dart
void main() {
  int n = 25;

  print(n); // 25

  // Re-assignable with shortcuts
  n += 5;   // n = n + 5;
  print(n); // 30

  n -= 5;   // n = n - 5;
  print(n); // 25

  n *= 5;   // n = n * 5;
  print(n); // 125

  n /= 5;   // n = n / 5;
  print(n); // 25
}
```

### String Interpolation

1. Basic Usage (Assigning and printing string values)

```dart
void main() {
  String greeting = "Hello, World!";
  print(greeting);  // "Hello, World!"

  greeting = 'Hello World';
  print(greeting);  //  'Hello World'
}

```

2. Use '$variable' for string interpolation instead of + for concatenation.

```dart
void main() {
  String greeting = "Hello, World!";

  print(greeting); // "Hello, World!"

  // greeting = greeting + "You";
  // General (+) operator should not be used with (String)

  // greeting =  '${greeting} You';
  // Unnecessary braces in a string interpolation. (view docs). Try removing the braces.

  // greeting = '$greeting You';
  // print(greeting);            //  "Hello, World! You"

  greeting = '${greeting.length} You';
  print(greeting); //  13 You

  // Use interpolation to compose strings and values. (View docs) Try using string interpolation to build the composite string.
}


```

3. Type Safety with Strings (Strings can only hold text, not numbers)

```dart
void main() {
 String greeting = "Hello, World!";

  print(greeting); // "Hello, World!"

  greeting = 10;
  //A value of type 'int' cant be assigned to a variable of type 'String'. Try changing the type of the variable, or casting the right-hand type to 'String'.
}
```

4. Dynamic Typing ( allows the variable to change types, but it’s generally less safe)

```dart
void main() {
  dynamic greeting = "Hello, World!";

  print(greeting); // "Hello, World!"

  greeting = 10;

  print(greeting);  // 10
}
```

### Dart Variables: var, final, and const

- Mutable vs Immutable Variables
  - var allows reassignment.
  - final and const are immutable.
  - const is compile-time constant,
  - while final is runtime constant.

```dart
void main() {
  var someValue1 = '10';     // mutual
  final someValue2 = '10';   // immutable
  const someValue3 = '10';   // immutable

  print(someValue1); // 10
  print(someValue2); // 10
  print(someValue3); // 10

  someValue1 = '1000';  // Allowed
  someValue2 = '1000';  // Error: Can't reassign a final variable.
  someValue3 = '1000';  // Error: Can't reassign a const variable.

  print(someValue1); // 10
  print(someValue2); // The final variable 'someValue2' can only be set once. Try making 'someValue2' non-final.
  print(someValue3); // Constant variables can't be assigned a value. Try removing the assignment, or remove the modifier 'const' from the variable.
}
```

- Using final and const with Non-constant Values
  - const can only be used with compile-time constants, while final can be used with values known at runtime.

```dart
void main() {
  final someValue2 = DateTime.now();  // Allowed
  const someValue3 = DateTime.now();  // Error: `const` requires compile-time constants.
  // The constructor being called isn't a const constructor. Try removing 'const' from the constructor invocation. Const variables must be initialized with a constant value. Try changing the initializer to be a constant expression.

  print(someValue2);
  print(someValue3);
}
```

### Optional Variables

- Nullable Variables
  - `? ` marks a variable as nullable.
  - `!.` forces access (dangerous if null).
  - `?.` safely accesses properties.
  - `??` provides a default value if null.
  - `? ` is not applicable to final, var, or const.

```dart
void main() {
  // String / int / bool and null

  //String someValue = ""; // "" => has a value of String, it doesn't mean someValue has no value.

  // int some = null;  // this syntax was good for dart 2 version but for dart 3 version use (?)

  int? some = null; // Nullable int
  // String? someValue = null; // redundant initialization to null
  String? someValue; // Nullable string, defaults to null

  print(someValue); // null

  someValue = '345 Hello World!'; // 345 Hello World!

  print(someValue);

  someValue = null;

  //print(someValue!.length); // Error: Using `!` on null will cause an error.
  print(someValue?.length ?? 0); // Safe access with a default value of 0.

  // ❌ Can't use ? with final, var, const
  // final? someValue = null;   // Error
  // var? someValue = null;     // Error
  // const? someValue = null;   // Error
}
```

### Control Flow

1. if-statement

```dart
bool isAdult = false;

void main() {
  int age = 13;

  if (isAdult) {
    print("ADULT 21");
  } else if (age >= 18) {
    print("ADULT");
  } else {
    print("CHILD");
  }
  // output => CHILD


  // Ternary
  String value = someValue.startsWith("H") ? "WOW" : "NAhA";

  // Switch Statement
   int age =20;
  switch (someValue) {
    case "hi" when age >= 20:
      print("hello");
    case "hi!!":
      print("hello");
    case "hi!!!":
      print("hello");
    default:
      print("default");
  }
}


```

```dart
void main() {
  String zone = "PQR";
  double weight = 6;

  String result = calculateShippingCost(zone, weight);
  print(result);
}

String calculateShippingCost(String zone, double weight) {
  double costPerKg;

  if (zone == "XYZ") {
    costPerKg = 5.0;
  } else if (zone == "ABC") {
    costPerKg = 7.0;
  } else if (zone == "PQR") {
    costPerKg = 10.0;
  } else {
    return "Error: Invalid destination zone.";
  }

  double shippingCost = costPerKg * weight;

  return "The shipping cost is \$${shippingCost.toStringAsFixed(2)}";
}

```

```dart
void main() {
  String zone = "XYZ";
  double weight = 5.0;

  String result = calculateShippingCost(zone, weight);
  print(result);
}

String calculateShippingCost(String zone, double weight) {
  double costPerKg;

  switch (zone) {
    case "XYZ":
      costPerKg = 5.0;
      break;
    case "ABC":
      costPerKg = 7.0;
      break;
    case "PQR":
      costPerKg = 10.0;
      break;
    default:
      return "Error: Invalid destination zone.";
  }

  double shippingCost = costPerKg * weight;
  return "The shipping cost is \$${shippingCost.toStringAsFixed(2)}";
}

```

---
