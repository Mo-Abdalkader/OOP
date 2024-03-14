### Polymorphism
**Polymorphism:** allows objects of different classes to be treated as objects of a common superclass through a shared interface. It enables flexibility and dynamic behavior by allowing methods to be overridden in subclasses, thus exhibiting different behaviors while being invoked through the same interface.

### Example:
Consider a scenario where we have a superclass Shape with a method draw(), and two subclasses Circle and Rectangle which override the draw() method to implement their own specific drawing behavior.

### Code:
```java
// Superclass
class Shape {
    // Method
    public void draw() {
        System.out.println("Drawing a shape...");
    }
}

// Subclass 1
class Circle extends Shape {
    // Override method
    @Override
    public void draw() {
        System.out.println("Drawing a circle...");
    }
}

// Subclass 2
class Rectangle extends Shape {
    // Override method
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle...");
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Shape shape1 = new Circle();
        Shape shape2 = new Rectangle();

        // Polymorphism: The draw() method of each shape will be invoked dynamically
        shape1.draw();  // Output: Drawing a circle...
        shape2.draw();  // Output: Drawing a rectangle...
    }
}
```
**Explination:**
In this example, we have a Shape superclass with a method draw(). The Circle and Rectangle classes are subclasses of Shape and override the draw() method to provide their specific drawing behavior.

In the Main class, we create objects of type Shape, but they actually refer to instances of Circle and Rectangle respectively. When calling the draw() method on these objects, the overridden version of the draw() method in each subclass is invoked, demonstrating polymorphism. Despite referring to objects of different types, the draw() method behaves differently based on the actual type of the object at runtime.

| Feature                               | Shape shape1 = new Circle();                        | Circle shape1 = new Circle();                       |
|---------------------------------------|------------------------------------------------------|-----------------------------------------------------|
| Reference Type                        | Reference variable is of type Shape.                 | Reference variable is of type Circle.               |
| Polymorphism                          | Allows for polymorphism, treating Circle as Shape.    | Does not allow polymorphism.                        |
| Access to Members                     | Can only access members defined in Shape interface/class unless explicitly cast to Circle. | Can directly access all members defined in Circle class. |
| Flexibility                           | Provides flexibility to switch to other subclasses of Shape without changing reference type. | Limited flexibility as the reference type is fixed to Circle. |
| Encapsulation                        | Promotes encapsulation by using a more general type (Shape) to reference the object. | May violate encapsulation by directly exposing the specific class type (Circle). |
| Code Readability and Maintainability  | Enhances code readability and maintainability by using a more abstract reference type (Shape). | May reduce code readability and maintainability due to a more concrete reference type (Circle). |
