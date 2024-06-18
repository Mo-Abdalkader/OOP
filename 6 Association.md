### Association
**Association:** defines a relationship between two separate classes that establish a connection through their objects. It represents a "uses-a" or "has-a" relationship, where one object uses or contains another object but without implying ownership or lifecycle dependency.

---

### Example:
Consider a scenario where we have a class `Library` and a class `Book`. A `Library` can have multiple `Books`, and `Books` can belong to multiple `Libraries`.

### Code:
```java
// Book class
class Book {
    private String title;

    // Constructor
    public Book(String title) {
        this.title = title;
    }

    // Getter
    public String getTitle() {
        return title;
    }
}

// Library class
class Library {
    private String name;
    private List<Book> books;

    // Constructor
    public Library(String name) {
        this.name = name;
        this.books = new ArrayList<>();
    }

    // Method to add a book
    public void addBook(Book book) {
        books.add(book);
    }

    // Method to list all books
    public void listBooks() {
        for (Book book : books) {
            System.out.println(book.getTitle());
        }
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        Library library = new Library("City Library");
        Book book1 = new Book("1984");
        Book book2 = new Book("To Kill a Mockingbird");

        library.addBook(book1);
        library.addBook(book2);

        // Listing all books in the library
        library.listBooks();  
        // Output:
        // 1984
        // To Kill a Mockingbird
    }
}
```

**Explanation:**
In this example, we have a Library class that can contain multiple Book objects, demonstrating an association between the Library and Book classes. The Library class has methods to add books and list all books in the library.

In the Main class, we create a Library object and Book objects, add the books to the library, and then list all books in the library. This showcases how association allows objects to be related and interact with each other.

---

### Pros and Cons of Association

**Pros:**
1. **Flexibility in Relationships:**
   - Association allows objects to be related in a flexible manner, representing various real-world relationships without tight coupling.
2. **Code Reusability:**
   - By defining relationships between objects, association promotes code reuse and modular design, enabling objects to work together without being dependent on each other’s implementation.
3. **Enhanced Maintainability:**
   - Since associations can be easily modified or extended, maintaining and updating the relationships between objects becomes more straightforward.
4. **Improved Code Readability:**
   - Clear associations between classes make the design and relationships in the code more understandable and easier to follow.
5. **Encapsulation:**
   - Associations help in maintaining encapsulation by allowing objects to interact through well-defined interfaces rather than direct access to each other’s data.

**Cons:**
1. **Increased Complexity:**
   - Managing multiple associations can add complexity to the design, making it harder to understand and maintain the overall system.
2. **Potential for Tight Coupling:**
   - If not designed carefully, associations can lead to tight coupling, where changes in one class can significantly impact associated classes.
3. **Difficulties in Object Lifecycle Management:**
   - Properly managing the creation and destruction of associated objects can be challenging, leading to potential memory management issues like memory leaks.
4. **Performance Overhead:**
   - Establishing and maintaining associations between objects can introduce a performance overhead, especially if the relationships are complex or involve many objects.
5. **Complex Navigation:**
   - Navigating through associations, especially in large systems with many interrelated objects, can become complex and error-prone, requiring careful design and management.
