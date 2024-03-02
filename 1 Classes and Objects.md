>[!important]
>### Definition:
> **Class**:
>A class is a blueprint or template for creating objects. It defines the attributes (properties) and behaviors (methods) that objects of that class will have. Classes are static entities and do not exist in memory during program execution.
>
> **Object**:
>An object is an instance of a class. It represents a specific entity in a program and possesses its own unique state (values for its attributes) and behavior (functions/methods). Objects are dynamic entities and exist in memory during program execution.

---
### Comparison:
| Feature        | Class                                         | Object                                           |
|----------------|-----------------------------------------------|--------------------------------------------------|
| Definition     | A blueprint or template for creating objects | An instance of a class representing a specific entity |
| Nature         | Static                                        | Dynamic                                          |
| Usage          | Serves as a blueprint for creating multiple objects of the same type | Represents a specific instance or occurrence of the class |
| Memory Allocation | Memory is not allocated during program execution | Memory is allocated during program execution |
| Example        | Defines properties and behaviors shared by all objects of that class | Represents a specific entity with its own state and behavior |


### Implementation:

```java
// Class Example
class Car {
    private String make;
    private String model;
    
    // Constructor
    public Car(String make, String model) {
        this.make = make;
        this.model = model;
    }
    
    // Method to display car details
    public void displayDetails() {
        System.out.println("Make: " + make + ", Model: " + model);
    }
}

// Object Example
public class Main {
    public static void main(String[] args) {
        // Creating an instance of the Car class (Object)
        Car myCar = new Car("Toyota", "Camry");
        
        // Using object methods
        myCar.displayDetails(); // Output: Make: Toyota, Model: Camry
    }
}
