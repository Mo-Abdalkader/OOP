### Composition

**Composition:** is a strong form of association that represents a "part-of" relationship between two classes, where one class is composed of one or more instances of other classes. In composition, the composed objects (parts) have a lifecycle that is dependent on the containing object (whole), meaning if the whole is destroyed, the parts are also destroyed.

---

### Example:
Consider a scenario where we have a class `Car` and a class `Engine`. A `Car` has an `Engine`, and the `Engine` cannot exist independently without the `Car`.

### Code:
```java
// Engine class
class Engine {
    private String type;

    // Constructor
    public Engine(String type) {
        this.type = type;
    }

    // Getter
    public String getType() {
        return type;
    }
}

// Car class
class Car {
    private String model;
    private Engine engine;

    // Constructor
    public Car(String model, String engineType) {
        this.model = model;
        this.engine = new Engine(engineType);
    }

    // Method to display car details
    public void displayDetails() {
        System.out.println("Car model: " + model);
        System.out.println("Engine type: " + engine.getType());
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Car car = new Car("Tesla Model S", "Electric");
        
        // Displaying car details
        car.displayDetails();
        // Output:
        // Car model: Tesla Model S
        // Engine type: Electric
    }
}
```

**Explanation:**
In this example, the Car class contains an instance of the Engine class, demonstrating composition. The Engine instance is created and managed by the Car class, and it cannot exist independently outside the context of the Car.

In the Main class, we create a Car object, which internally creates an Engine object. We then display the details of the car, showcasing the composition relationship.

---

### Pros and Cons of Composition

**Pros:**
1. **Strong Lifecycle Dependency:**
   - Composition ensures a strong lifecycle dependency, meaning the contained objects are destroyed when the containing object is destroyed, which helps in managing resources effectively.
2. **Encapsulation:**
   - Composition promotes encapsulation by hiding the implementation details of the contained objects and exposing only the necessary interfaces.
3. **Code Reusability:**
   - By composing objects, code can be reused and organized in a modular way, allowing for more maintainable and scalable designs.
4. **Simplifies Object Management:**
   - The containing object is responsible for the lifecycle of the composed objects, simplifying object creation and destruction management.
5. **Enhanced Maintainability:**
   - Changes to the composed objects can be made independently without affecting other parts of the system, as long as the interface remains consistent.

**Cons:**
1. **Increased Complexity:**
   - Composition can add to the complexity of the system, especially when there are many composed objects with intricate dependencies.
2. **Tight Coupling:**
   - Since composed objects are tightly bound to their containing object, changes in the composition structure can require significant modifications in the codebase.
3. **Difficult to Change Composition:**
   - Altering the composition of objects can be challenging, as it might require changes in the design and implementation of the containing object.
4. **Performance Overhead:**
   - Managing the lifecycle of composed objects can introduce performance overhead, particularly if there are many nested compositions.
5. **Potential for Memory Leaks:**
   - Improper management of the lifecycle and dependencies of composed objects can lead to memory leaks or other resource management issues.
