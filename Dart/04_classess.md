# Class

1. **_CLASS_**

- A class is a blueprint/template for creating objects.
- It defines a type of object according to
  1. its properties (fields)
  2. behaviors (methods).

2. **_Object_**

- An object is an instance of a class.
- It has its own specific values for the properties defined in the class and can use the methods of the class..

3. **Constructor**

- A constructor is a special method that initializes a new object with default or provided values when it is created.

4. **Types of Constructors**

   - **Default Constructor**: Initializes an object with default values.
   - **Parameterized Constructor**: Initializes an object with specific values provided as arguments.
   - **Named Constructor**: Allows multiple ways to initialize an object with named parameters.

5. **Private Variables**

- Variables that are only accessible within the class they are defined in.
- They are used to encapsulate and protect data.

6. **Getters and Setters**

- Special methods used to access (getters) and modify (setters) private variables.

7. **Static Variables and Methods**

- Variables and methods that belong to the class itself, rather than to any specific instance. They are accessed using the class name.

---

1. Basic Class Definition and Object Instantiation

```dart
// fn    -> camel case  -> "camelCase"
// class -> pascal case -> "PascalCase"
void main() {
  // calling fn -> fnName();
  // calling class -> Cookie();

  print(Cookie().toString()); // Instance of 'Cookie'
  print(Cookie().shape); // Circle
  print(Cookie().size); // 15.2
  print('${Cookie().size} cm'); // 15.2 cm
  Cookie().baking(); // Baking Has started...
  print(Cookie().isCooling());

  final isCookieCooling = Cookie().isCooling();
  print(isCookieCooling); // false
}

class Cookie {
  // variables or property
  String shape = "Circle";
  double size = 15.2; // cm

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}

```

2. Creating and Using Objects

```dart

void main() {
  // own Datatype => Cookie
  Cookie cookie = Cookie();

  print(cookie.toString()); // Instance of 'Cookie'
  print(cookie.shape); // Circle
  print(cookie.size); // 15.2
  print('${cookie.size} cm'); // 15.2 cm
  cookie.baking(); // Baking Has started...
  print(cookie.isCooling());

  final isCookieCooling = cookie.isCooling();
  print(isCookieCooling); // false
}

class Cookie {
  // variables
  String shape = "Circle";
  double size = 15.2; // cm

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}

```

3. Modifying Object Properties

```dart

/*
void main() {
  //Cookie cookie = Cookie();

  final cookie = Cookie();
  print(cookie.shape);  // Circle

  cookie.shape = "Rectangle";
  print(cookie.shape);  // Rectangle
}
*/

void main() {

  print(Cookie().shape);  // Circle
  Cookie().shape = "Rectangle";
  print(Cookie().shape);  // Circle
}

class Cookie {
  // variables
  String shape = "Circle";
  double size = 15.2; // cm

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}

```

4. Parameterized Constructor

```dart

void main() {
  //final cookie = new  Cookie();  in java
  final cookie = Cookie("Circle", 20);

  print(cookie.shape); // Circle
  print(cookie.shape); // 20
}

// 1. short hand and Parameterized Constructor
class Cookie {
  // variables
  String shape;
  double size;

// Parameterized Constructor
  Cookie(this.shape, this.size) {
    print(this);                       // Instance of 'Cookie'
    print("Cookie Constructor called");// Cookie Constructor called
    baking();                          //Baking Has started...
  }

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}

// 2. long hand Constructor
class Cookie {
  // variables
  String? shape = "Cookie";
  double? size;

  Cookie(String shape, double size){
    print(this.shape);
    this.shape = shape;
    this.size = size;
  }

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}


```

5. Named Constructor with Required Parameters

```dart
void main() {
  final cookie = Cookie(shape: "Circle", size: 20);
}

class Cookie {
  // variables
  final String shape;
  final double size;

  // Named constructor
  Cookie({required this.shape, required this.size}) {
    baking();
  }

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}


```

6. Private Variables

```dart
void main() {
  final cookie = Cookie(shape: "Circle", size: 20);
  print(cookie);
}

class Cookie {
  // variables
  final String shape;
  final double size;

  // Named constructor
  Cookie({required this.shape, required this.size}) {
    baking();
  }

  // Private Variables
  int _height = 4;
  int _width = 5;

  /*
  'size' cant be used as a setter because it's final.
  Try finding a different setter, or making 'size' non-final.

  void calculateSize(){
    size = _height * _width;
  }
  */

  int calculateSize() {
    return _height * _width;
  }

  // methods
  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}

```

7. Class with Getters and Setters

```dart
void main() {
  final cookie = Cookie(shape: "Circle", size: 20);

  // cookie._height = 10; i do not want change value outer side class

  print(cookie.height);// 4  // this only get height value (read only value)

  //cookie.setHeight(15); this is function give error instead u want have setter
  cookie.setHeight = 15;

  print(cookie.height); // 15
}

class Cookie {
  // variables
  final String shape;
  final double size;

  // Named constructor
  Cookie({required this.shape, required this.size}) {
    baking();
  }

  // Private Variables
  int _height = 4;
  int _width = 5;

  // Getters
  int get height => _height;
  int get width => _width;

  /*  instead of this use setter
  void modifyHeight(int h){
  _height = h;
  }
  */

  // Setter
  set setHeight(int h) {
    _height = h;
  }

  // methods

  int calculateSize() {
    return _height * _width;
  }

  void baking() {
    print("Baking Has started...");
  }

  bool isCooling() {
    return false;
  }
}


```

7. Static Members in a Class

```dart
void main() {
  final constants = Constants();

  print(constants.greeting);
  print(constants.bye);
}

class Constants {
  String greeting = "Hello, how are you?";
  String bye = "bye";
}
// ----------

void main() {
  print(Constants.greeting);
  print(Constants.bye);
  print(Constants.giveMeSomeValue());
}

class Constants {
  Constants() {
    print("Constructor Called");
  }

  static String greeting = "Hello, how are you?";
  static String bye = "bye";

  // static method
  static int giveMeSomeValue() {
    return 10;
  }
}


```
