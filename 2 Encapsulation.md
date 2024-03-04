# Encapsulation:

**Encapsulation** in Java is the bundling of data (attributes) and methods that operate on that data within a single unit (class). It hides the internal state of objects from outside interference and manipulation. Let's demonstrate encapsulation by modifying the Car class:


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
