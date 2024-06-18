### Aggregation
**Aggregation:** is a type of association that represents a "whole-part" or "has-a" relationship between two classes, where one class is a collection or container of objects of another class. Unlike composition, aggregation implies a weaker relationship where the contained objects can exist independently of the container.

---

### Example:
Consider a scenario where we have a class `Department` and a class `Employee`. A `Department` can have multiple `Employees`, and an `Employee` can belong to only one `Department` at a time.

### Code:
```java
// Employee class
class Employee {
    private String name;

    // Constructor
    public Employee(String name) {
        this.name = name;
    }

    // Getter
    public String getName() {
        return name;
    }
}

// Department class
class Department {
    private String name;
    private List<Employee> employees;

    // Constructor
    public Department(String name) {
        this.name = name;
        this.employees = new ArrayList<>();
    }

    // Method to add an employee
    public void addEmployee(Employee employee) {
        employees.add(employee);
    }

    // Method to list all employees
    public void listEmployees() {
        for (Employee employee : employees) {
            System.out.println(employee.getName());
        }
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Department department = new Department("Human Resources");
        Employee employee1 = new Employee("John Doe");
        Employee employee2 = new Employee("Jane Smith");

        department.addEmployee(employee1);
        department.addEmployee(employee2);

        // Listing all employees in the department
        department.listEmployees();
        // Output:
        // John Doe
        // Jane Smith
    }
}
```

**Explanation:**
In this example, the Department class contains a collection of Employee objects, demonstrating aggregation. The Employee instances are independent entities that can exist outside the Department and can belong to different departments or none at all.

In the Main class, we create a Department object and Employee objects, add the employees to the department, and then list all employees in the department, illustrating the aggregation relationship.

---

### Pros and Cons of Aggregation

**Pros:**
1. **Flexibility in Relationships:**
   - Aggregation allows for a flexible relationship where the contained objects (parts) can exist independently of the container (whole).
2. **Code Reusability:**
   - By aggregating objects, code can be reused and organized in a modular way, allowing for more maintainable and scalable designs.
3. **Simplifies Object Management:**
   - The container object is responsible for managing the collection of contained objects, simplifying object creation, access, and modification.
4. **Enhanced Scalability:**
   - Aggregation supports adding and removing objects dynamically, making it easier to scale and adapt the system as requirements change.
5. **Reduced Complexity:**
   - Compared to composition, aggregation typically results in lower complexity since the contained objects are not tightly bound to the container.

**Cons:**
1. **Semantic Ambiguity:**
   - The distinction between aggregation and association can sometimes be ambiguous, leading to potential misunderstandings in the design.
2. **Potential for Inconsistency:**
   - If not managed properly, changes in the container object or the contained objects can lead to inconsistencies or unexpected behavior.
3. **Less Control over Lifecycle:**
   - Unlike composition, where the lifecycle of the contained objects is tightly controlled by the container, in aggregation, the contained objects can exist independently, which may lead to issues in lifecycle management.
4. **Performance Overhead:**
   - Managing a collection of objects in aggregation can introduce performance overhead, especially when dealing with large datasets or frequent modifications.
5. **Complex Navigation:**
   - Navigating through aggregated objects, especially in complex relationships, can become challenging and require careful design to avoid errors and inefficiencies.
