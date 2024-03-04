# Encapsulation:

**Encapsulation** is one of the core principles of object-oriented programming (OOP) that involves bundling data (attributes) and methods (behaviors) that operate on that data within a single unit (class). It hides the internal state of objects from outside interference and manipulation, allowing controlled access through defined interfaces (methods). Let's demonstrate encapsulation by modifying the Car class:


**Implementation:**
```java
public class Car {
    // Private properties for encapsulation
    private String make;
    private String model;
    private int year;

    // Public methods for accessing/mutating properties
    public String getMake() {
        return make;
    }

    public void setMake(String make) {
        this.make = make;
    }

    public String getModel() {
        return model;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public int getYear() {
        return year;
    }

    public void setYear(int year) {
        this.year = year;
    }

    // Other methods...
}
```

**Explination:**
In this updated `Car` class, the properties `make`, `model`, and `year` are encapsulated using private access modifiers, meaning they can only be accessed or modified within the `Car` class itself. Public getter and setter methods (`getMake()`, `setMake()`, etc.) are provided to allow controlled access to these properties from outside the class. This encapsulation ensures that the internal state of a `Car` object remains protected and can only be modified through predefined methods, maintaining data integrity and security.



---
The importance of encapsulation lies in several key benefits it provides:
| Feature                               | Hiding Variable and Using Functions                  | Modifying Automatically                             |
|---------------------------------------|------------------------------------------------------|------------------------------------------------------|
| Data Access                           | Access and modification are controlled through getter and setter methods. | Direct access and modification of the variable without any control. |
| Validation                            | Allows validation and enforcement of constraints within setter methods. | No validation or constraint enforcement, leading to potential data inconsistency or errors. |
| Flexibility                           | Provides flexibility to add additional logic or side effects to setter methods. | Limited flexibility as the modification occurs directly without intervention. |
| Encapsulation                        | Promotes encapsulation by encapsulating data and providing controlled access. | May violate encapsulation principles by exposing internal state directly. |
| Code Maintenance and Readability    | Enhances code maintainability and readability by providing clear interfaces for data access. | May lead to code that is harder to maintain and understand due to scattered direct accesses. |
| Error Handling                        | Allows centralized error handling and reporting within setter methods. | Error handling may need to be implemented separately where the modification occurs. |


Regarding the benefit of hiding a variable and performing a function to modify its value instead of modifying it automatically, consider the following scenario:

Suppose you have a Person class with an attribute age. Instead of directly exposing the age attribute as public and allowing external code to modify it directly, you encapsulate it and provide public methods like getAge() and setAge() to access and modify the age value, respectively.

**Example:**
```java
public class Person {
    private int age;

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age >= 0 && age <= 120) {
            this.age = age;
        } else {
            throw new IllegalArgumentException("Age must be between 0 and 120.");
        }
    }
}
```

**Explination:**
By encapsulating the age attribute and providing getter and setter methods, you gain the following benefits:

Validation: The setAge() method can enforce validation rules, such as ensuring that the age value falls within a valid range (e.g., between 0 and 120). This prevents invalid data from being set and maintains data integrity.
Flexibility: You can add additional logic or side effects to the setter method, such as logging, triggering events, or updating related attributes, without modifying external code that uses the class.
Control: By controlling access to the age attribute through getter and setter methods, you can maintain control over how the attribute is read and modified, allowing you to enforce business rules or constraints as needed.
Overall, encapsulation promotes better code organization, maintainability, and flexibility by hiding implementation details and providing controlled access to an object's data.

