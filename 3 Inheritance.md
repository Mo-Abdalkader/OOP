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
  
