### Polymorphism in Java

**Polymorphism** is one of the four pillars of Object-Oriented Programming (OOP), along with Encapsulation, Abstraction, and Inheritance. In Java, polymorphism allows objects of different classes to be treated as objects of a common superclass. It can occur in two main ways:

1. **Compile-time polymorphism** (Method Overloading)
2. **Run-time polymorphism** (Method Overriding)

### 1. Compile-time Polymorphism (Method Overloading)
Compile-time polymorphism occurs when multiple methods in the same class share the same name but differ in the number or types of parameters. This is known as **method overloading**.

#### Example:
```java
class Calculator {
    // Method with two parameters
    public int add(int a, int b) {
        return a + b;
    }

    // Overloaded method with three parameters
    public int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(5, 10));      // Output: 15
        System.out.println(calc.add(5, 10, 15));  // Output: 30
    }
}
```

In this case, the `add()` method is overloaded, meaning Java can resolve which version of the method to invoke based on the method signature (number and type of arguments) at **compile-time**.

### 2. Run-time Polymorphism (Method Overriding)
Run-time polymorphism occurs when a subclass provides a specific implementation of a method that is already defined in its superclass. This is called **method overriding**.

The method to be called is determined at **run-time** rather than compile-time, making it a dynamic behavior.

#### Example:
```java
class Animal {
    // Parent class method
    public void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    // Overriding the parent class method
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    // Overriding the parent class method
    @Override
    public void sound() {
        System.out.println("Cat meows");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Animal();  // Parent class reference and object
        Animal myDog = new Dog();        // Parent class reference to Dog object
        Animal myCat = new Cat();        // Parent class reference to Cat object

        myAnimal.sound();  // Output: Animal makes a sound
        myDog.sound();     // Output: Dog barks
        myCat.sound();     // Output: Cat meows
    }
}
```

Here, the method `sound()` is overridden in the `Dog` and `Cat` subclasses. At run-time, the JVM determines which `sound()` method to call based on the object type (`Dog` or `Cat`), even though the reference is of type `Animal`.

### Key Points:
- **Overloading** is an example of **compile-time polymorphism** (static binding). It allows methods in the same class to have the same name but differ in parameter types or number of parameters.
- **Overriding** is an example of **run-time polymorphism** (dynamic binding). It occurs when a subclass provides its specific implementation of a method that is already present in its superclass.
  
### Polymorphism and Interfaces
Polymorphism can also occur with **interfaces** in Java. A class can implement multiple interfaces, and an interface reference can point to an object of any class that implements it.

#### Example:
```java
interface Vehicle {
    void move();
}

class Car implements Vehicle {
    public void move() {
        System.out.println("Car is moving");
    }
}

class Bike implements Vehicle {
    public void move() {
        System.out.println("Bike is moving");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle myCar = new Car();  // Vehicle reference to Car object
        Vehicle myBike = new Bike();  // Vehicle reference to Bike object

        myCar.move();  // Output: Car is moving
        myBike.move();  // Output: Bike is moving
    }
}
```

In this case, both `Car` and `Bike` implement the `Vehicle` interface, but the actual method that is executed depends on the type of object at run-time.

### Benefits of Polymorphism
- **Code Reusability**: You can reuse methods from the parent class without rewriting them.
- **Flexibility and Maintainability**: Makes your program more flexible and easier to maintain by allowing one interface for different types of objects.
- **Loose Coupling**: Promotes loose coupling, which makes systems more modular.

By using polymorphism, developers can write flexible and maintainable code, which is one of the most important aspects of OOP.