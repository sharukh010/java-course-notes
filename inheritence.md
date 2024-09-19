### Inheritance in Java

**Inheritance** is a mechanism in Java where one class acquires the properties and behaviors (methods and fields) of another class. The class that inherits is called the **subclass** (child class), and the class from which it inherits is called the **superclass** (parent class).

Inheritance allows for **code reusability**, and also helps in implementing polymorphism.

#### Syntax of Inheritance:
In Java, inheritance is achieved using the `extends` keyword.

```java
// Base class or Superclass
class Animal {
    String name;
    
    public void eat() {
        System.out.println(name + " is eating");
    }
}

// Derived class or Subclass
class Dog extends Animal {
    public void bark() {
        System.out.println(name + " is barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.name = "Buddy";
        dog.eat();  // inherited method from Animal
        dog.bark(); // method in Dog class
    }
}
```

### Types of Inheritance in Java

There are several types of inheritance, though Java only supports **Single**, **Multilevel**, and **Hierarchical Inheritance**. **Multiple** and **Hybrid Inheritance** are not directly supported but can be achieved via interfaces.

#### 1. Single Inheritance

In single inheritance, a subclass inherits from one superclass.

```java
class Vehicle {
    public void start() {
        System.out.println("Vehicle is starting");
    }
}

class Car extends Vehicle {
    public void honk() {
        System.out.println("Car is honking");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        car.start(); // inherited from Vehicle
        car.honk();  // specific to Car
    }
}
```

#### 2. Multilevel Inheritance

In multilevel inheritance, a class is derived from another class, which in turn is derived from another class.

```java
class Animal {
    public void eat() {
        System.out.println("Animal is eating");
    }
}

class Mammal extends Animal {
    public void walk() {
        System.out.println("Mammal is walking");
    }
}

class Dog extends Mammal {
    public void bark() {
        System.out.println("Dog is barking");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();   // inherited from Animal
        dog.walk();  // inherited from Mammal
        dog.bark();  // specific to Dog
    }
}
```

#### 3. Hierarchical Inheritance

In hierarchical inheritance, multiple subclasses inherit from a single superclass.

```java
class Animal {
    public void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("Dog is barking");
    }
}

class Cat extends Animal {
    public void meow() {
        System.out.println("Cat is meowing");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();  // inherited from Animal
        dog.bark(); // specific to Dog

        Cat cat = new Cat();
        cat.eat();  // inherited from Animal
        cat.meow(); // specific to Cat
    }
}
```

### Unsupported Types in Java:

#### 4. Multiple Inheritance (Not Supported via Classes)
Java does not support multiple inheritance with classes to avoid ambiguity (Diamond problem), but it can be achieved using interfaces.

#### 5. Hybrid Inheritance (Not Supported Directly)
Hybrid inheritance is a combination of multiple and multilevel inheritance. This is also not directly supported in Java but can be implemented using interfaces.

### Summary:
- **Inheritance** allows a class to inherit properties and methods from another class.
- Java supports **Single**, **Multilevel**, and **Hierarchical** inheritance through classes.
- **Multiple** and **Hybrid** inheritance are not supported directly through classes but can be achieved via interfaces.

