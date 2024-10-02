### Abstract Classes in Java

#### Definition
An **abstract class** in Java is a class that cannot be instantiated on its own. It may contain abstract methods (methods without a body) that must be implemented by its subclasses. Abstract classes provide a way to enforce certain methods to be created for different subclasses while also allowing for the implementation of shared methods. 

#### Syntax
Here is the basic structure of an abstract class in Java:
```java
abstract class Vehicle {
    abstract void startEngine();

    void stopEngine() {
        System.out.println("Engine stopped.");
    }
}
```
- `abstract class Vehicle`: Defines an abstract class named `Vehicle`.
- `abstract void startEngine()`: An abstract method that must be implemented by subclasses.
- `void stopEngine()`: A concrete method with implementation that can be used by subclasses.

#### Real-Life Example: Vehicles
Think of an **abstract class** as a blueprint for a general concept. For instance, a `Vehicle` could be an abstract class because all vehicles share common characteristics, such as having engines, but the way they operate can vary.

**Abstract Class: Vehicle**
```java
abstract class Vehicle {
    abstract void startEngine(); // Abstract method

    void stopEngine() { // Concrete method
        System.out.println("Engine stopped.");
    }
}
```
**Subclass 1: Car**
```java
class Car extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Car engine started.");
    }
}
```
**Subclass 2: Motorcycle**
```java
class Motorcycle extends Vehicle {
    @Override
    void startEngine() {
        System.out.println("Motorcycle engine started.");
    }
}
```
In this example:
- `Vehicle` is the abstract class. It has an abstract method `startEngine()` that forces any subclass to provide its own implementation.
- `Car` and `Motorcycle` are subclasses that extend `Vehicle` and implement the `startEngine()` method.

#### Why Use Abstract Classes?
1. **Code Reusability:** Abstract classes allow you to define some common behaviors (e.g., `stopEngine()` in `Vehicle`) that all subclasses can inherit and use, while enforcing specific behaviors to be implemented in subclasses (e.g., `startEngine()`).
2. **Polymorphism:** They enable polymorphism. You can use the abstract class reference to point to subclass objects.
   ```java
   Vehicle myCar = new Car();
   Vehicle myBike = new Motorcycle();
   myCar.startEngine(); // Output: Car engine started.
   myBike.startEngine(); // Output: Motorcycle engine started.
   ```
3. **Shared Attributes:** You can define common properties in the abstract class that all subclasses inherit, such as a fuel capacity.

#### Real-Life Example: Electronic Devices
Another real-life example could be an abstract class representing an **Electronic Device**. Different devices have a way to turn on, but they do it differently.
```java
abstract class ElectronicDevice {
    abstract void turnOn();

    void turnOff() {
        System.out.println("Device turned off.");
    }
}
```
**Subclass 1: Smartphone**
```java
class Smartphone extends ElectronicDevice {
    @Override
    void turnOn() {
        System.out.println("Smartphone booting up...");
    }
}
```
**Subclass 2: Television**
```java
class Television extends ElectronicDevice {
    @Override
    void turnOn() {
        System.out.println("Television powering on...");
    }
}
```
In this example:
- `ElectronicDevice` is the abstract class that defines the abstract method `turnOn()`.
- `Smartphone` and `Television` provide their own implementations of `turnOn()`.

#### Key Points to Remember
- **Cannot Instantiate:** Abstract classes cannot be instantiated directly. They are meant to be subclassed.
- **May Contain Concrete Methods:** Abstract classes can have fully implemented methods that can be inherited by subclasses.
- **Must Implement Abstract Methods:** Any subclass of an abstract class must provide implementations for all abstract methods.
- **Can Have Constructors:** Abstract classes can have constructors, but these are called when an object of a subclass is created.

### When to Use Abstract Classes
Use abstract classes when:
- You have a common base class that defines behaviors shared by all subclasses.
- You want to provide some default behavior that subclasses can inherit.
- You want to enforce specific behaviors (abstract methods) that subclasses must implement.

### Conclusion
Abstract classes in Java serve as blueprints for related classes, defining common behaviors while leaving room for subclass-specific implementations. By using abstract classes, you can create a structured and reusable codebase that enforces consistency across different subclass implementations.