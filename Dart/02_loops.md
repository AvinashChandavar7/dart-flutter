# Loops

```dart
void main(){
   // loop!

   print("Hello, world! 1");
   print("Hello, world! 2");
   print("Hello, world! 3");
   print("Hello, world! 4");
   print("Hello, world! 5");
   print("Hello, world! 6");
}
```

1. `For` loop

```dart
void main() {
/*
for( initialization ; condition ; increment/decrement ){
  logic stmt;
}
*/
  // i++  => i = i + 1
  // i--  => i = i - 1
  // i+=2 => i = i + 2


  for (int i = 0; i < 10; i++) {
    print("Hello, world  ${i + 1}");
  }

  // String
  for (int i = 0; i < 14; i++) {
    String s = "Hello, world";
    print(s.substring(0, i++));
  }
}
```

2. `For in` loop

```dart
void main() {
  // for in loop
  String value = "Hello";
  for (int i = 0; i < value.length; i++) {
    print(value[i]);
  }
}

void main() {
  List<String> fruits = ['Apple', 'Banana', 'Cherry'];
  // Using for-in to iterate over the list
  for (var fruit in fruits) {
    print(fruit);
  }
}
```

3. `while` loop

```dart
void main() {
  // while (condition) {}

  String value = "Hello";
  int i = 0;

  while (i < value.length) {
    print(value[i]);
    i++;
  }
}
```

4. `do while` loop

```dart
void main() {
  // do {} while(condition);

  String value = "Hello";
  int i = 0;

  do {
    print(value[i]);
    i++;
  } while (i != i);
 // } while (i < value.length);
}

```

5. `continue` & `break` stmt loop

```dart
void main() {
  String value = "Hello";
  for (int i = 0; i < value.length; i++) {
    if (i == 1 || i == 2 || i == 3) {
      continue;
    }
    print(value[i]);
  }
}

void main() {
  String value = "Hello";
  for (int i = 0; i < value.length; i++) {
    if (i == 1 || i == 2 || i == 3) {
      break;
    }
    print(value[i]);
  }
}

```

| **For Loop**                                                          | **While Loop**                                                   |
| --------------------------------------------------------------------- | ---------------------------------------------------------------- |
| Used when the number of iterations is known.                          | Used when the number of iterations is unknown.                   |
| Counter variable declared in the loop declaration.                    | No built-in counter variable; must be managed manually.          |
| Can run indefinitely if no condition is given.                        | Runs indefinitely until the condition is met.                    |
| Condition is optional but may cause an infinite loop if not specified | Must have a condition; otherwise, it causes a compilation error. |
