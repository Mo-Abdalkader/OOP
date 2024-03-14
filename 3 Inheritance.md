### Inheritance:

1. **Base Class (Parent Class / Superclass)**:
   - The class whose members are inherited by another class.
   - It's also called the parent class or superclass.

2. **Derived Class (Child Class / Subclass)**:
   - The class that inherits properties and behavior from another class.
   - It's also called the child class or subclass.

3. **Syntax for Inheritance**:
   - Different languages have different syntax for inheritance. Commonly, a subclass specifies its superclass using keywords like `extends`, `:`, or `inherits`.

### Advantages of Inheritance:

- **Code Reusability**: Inheritance allows subclasses to inherit properties and methods from their parent class, reducing code duplication.
- **Promotes Modularity**: Classes can be organized hierarchically, promoting a modular design that is easier to understand and maintain.
- **Polymorphism**: Inheritance enables polymorphic behavior, where objects of different classes can be treated uniformly.

### Example:
Consider a scenario where we have a Vehicle class representing common attributes and behaviors of all vehicles. We can then create a Car class and a Bicycle class that inherit from the Vehicle class, inheriting its properties and behaviors while adding their own specific characteristics.

**Cdoe:**
```java
// Parent class
public class Vehicle {
    // Properties
    protected String manufacturer;
    protected int year;

    // Constructor
    public Vehicle(String manufacturer, int year) {
        this.manufacturer = manufacturer;
        this.year = year;
    }

    // Method
    public void drive() {
        System.out.println("The vehicle is being driven.");
    }
}

// Subclass 1
public class Car extends Vehicle {
    // Additional properties specific to Car
    private int numOfDoors;

    // Constructor
    public Car(String manufacturer, int year, int numOfDoors) {
        super(manufacturer, year); // Call superclass constructor
        this.numOfDoors = numOfDoors;
    }

    // Additional method specific to Car
    public void honk() {
        System.out.println("Beep! Beep!");
    }
}

// Subclass 2
public class Bicycle extends Vehicle {
    // Additional properties specific to Bicycle
    private int numOfGears;

    // Constructor
    public Bicycle(String manufacturer, int year, int numOfGears) {
        super(manufacturer, year); // Call superclass constructor
        this.numOfGears = numOfGears;
    }

    // Additional method specific to Bicycle
    public void ringBell() {
        System.out.println("Ring! Ring!");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car("Toyota", 2020, 4);
        Bicycle myBicycle = new Bicycle("Giant", 2019, 18);

        myCar.drive(); // Output: The vehicle is being driven.
        myCar.honk();  // Output: Beep! Beep!

        myBicycle.drive();  // Output: The vehicle is being driven.
        myBicycle.ringBell(); // Output: Ring! Ring!
    }
}
```
**Explination:**
In this example, the Vehicle class serves as the superclass, defining common properties and behaviors shared by all vehicles. The Car and Bicycle classes inherit from Vehicle, gaining access to its properties and methods. They also add their own specific properties and methods (numOfDoors, honk() for Car; numOfGears, ringBell() for Bicycle). This demonstrates how inheritance promotes code reuse and helps in organizing and extending the functionality of classes in Java.


### Use of `super` Keyword:

- **Accessing Parent Class Members**: In many programming languages, the `super` keyword is used to access members (methods or properties) of the parent class from within the subclass.
- **Invoking Parent Class Constructors**: In languages like Java, `super` is used to invoke the constructor of the parent class from the constructor of the subclass.

### Examples of `super` Keyword:

- **Accessing Parent Class Method (Java)**:
   ```java
   class Parent {
       void display() {
           System.out.println("Parent class method");
       }
   }

   class Child extends Parent {
       void display() {
           super.display(); // Call parent class method
           System.out.println("Child class method");
       }
   }
  ```

- **Invoking Parent Class Constructor (Java)**:
  ``` java
  class Parent {
      Parent() {
          System.out.println("Parent class constructor");
      }
  }
  
  class Child extends Parent {
      Child() {
          super(); // Call parent class constructor
          System.out.println("Child class constructor");
      }
  }
  ```


### Overriding and Overloading:
- Overriding: When a subclass provides a specific implementation of a method that is already provided by its superclass.
- Overloading: When multiple methods with the same name exist in a class, but with different parameter lists.

### Multiple Inheritance:
- Single Inheritance: A subclass inherits from only one superclass.
- Multiple Inheritance: A subclass can inherit from multiple superclasses.
- Diamond Problem: In multiple inheritance, if two superclasses have a common ancestor, ambiguity may arise. Some languages like Java and C# do not support multiple inheritance to avoid this problem.

### Inheritance Modifiers:
- Public: Members are accessible from any other class.
- Protected: Members are accessible within the same package and subclasses.
- Private: Members are accessible only within the same class.
- Default (Package-private): Members are accessible within the same package.
  
