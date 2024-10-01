## Access Modifiers in Java

Access modifiers in Java define the accessibility or scope of a class, constructor, method, or data member. Java has four main access modifiers:

1. **Private**
2. **Default (Package-Private)**
3. **Protected**
4. **Public**

### 1. **Private Access Modifier**
- **Scope:** The private access modifier restricts the visibility of a member to the class in which it is declared. Private members are not accessible outside of their defining class.
- **Use:** It is commonly used to hide the implementation details of a class and to enforce encapsulation.
- **Example:**
    ```java
    public class Example {
        private int data = 30;

        private void display() {
            System.out.println("This is a private method.");
        }
    }
    ```

### 2. **Default (Package-Private) Access Modifier**
- **Scope:** When no access modifier is specified, Java assigns the default access level (also known as package-private). This makes the members accessible only within classes in the same package.
- **Use:** Useful for grouping classes that are closely related and need access to each other's methods and variables without exposing them to the outside world.
- **Example:**
    ```java
    class Example {
        int data = 30; // Default access modifier

        void display() {
            System.out.println("This is a default access method.");
        }
    }
    ```

### 3. **Protected Access Modifier**
- **Scope:** The protected access modifier allows access to the member variables or methods within the same package and subclasses (even if they are in different packages).
- **Use:** It is mainly used when inheritance is involved, allowing subclasses to access certain members of the superclass.
- **Example:**
    ```java
    public class Example {
        protected int data = 30;

        protected void display() {
            System.out.println("This is a protected method.");
        }
    }
    ```

### 4. **Public Access Modifier**
- **Scope:** The public access modifier makes a class, method, or variable accessible from any other class, regardless of the package it is in.
- **Use:** When the members need to be accessible across all classes and packages.
- **Example:**
    ```java
    public class Example {
        public int data = 30;

        public void display() {
            System.out.println("This is a public method.");
        }
    }
    ```

### Summary Table of Access Modifiers in Java

Here is a table summarizing the access levels of Java's access modifiers:

| Modifier   | Class | Package | Subclass | World (Other Packages) |
|------------|-------|---------|----------|-----------------------|
| **private**| Yes   | No      | No       | No                    |
| **default**| Yes   | Yes     | Yes       | No                    |
| **protected** | Yes   | Yes     | Yes      | No                    |
| **public** | Yes   | Yes     | Yes      | Yes                   |

- **Class**: Accessible within the same class.
- **Package**: Accessible by other classes in the same package.
- **Subclass**: Accessible in subclasses, including those in different packages (only for `protected` and `public`).
- **World**: Accessible by all classes in all packages (only for `public`).