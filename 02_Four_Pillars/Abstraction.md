# Abstraction in Java

## Definition

Abstraction is the process of **hiding unnecessary implementation details** and showing only the important information to the user.

In simple words:

> Abstraction means showing "what an object does" and hiding "how it does it".

The user only needs to know the functionality, not the internal working.

---

# Real-Life Example

Think about a car.

When you drive a car, you use:

- Steering wheel
- Accelerator
- Brake
- Gear

You don't need to know:

- How fuel is injected.
- How the engine creates power.
- How the transmission works.

The driver only knows:

```
Press accelerator → Car moves
Press brake → Car stops
```

The internal mechanism is hidden.

This is abstraction.

---

# Why do we need Abstraction?

Large software systems contain thousands of lines of code.

Showing all internal details to every user makes the system complicated.

Abstraction helps by:

- Reducing complexity.
- Improving code readability.
- Increasing security.
- Making code easier to maintain.
- Allowing developers to focus on essential features.

---

# How is Abstraction achieved in Java?

Java provides two ways to achieve abstraction:

1. Abstract Classes
2. Interfaces

---

# Abstract Class

An abstract class is a class that cannot be directly instantiated.

It can contain:

- Abstract methods (methods without implementation)
- Normal methods (methods with implementation)
- Variables
- Constructors

---

# Syntax of Abstract Class

```java
abstract class ClassName{

    abstract void methodName();

    void normalMethod(){

        // implementation

    }

}
```

---

# Abstract Method

An abstract method is a method that has:

- No body
- Only declaration

Example:

```java
abstract void start();
```

The child class must provide its implementation.

---

# Example Using Abstract Class

```java
abstract class Vehicle{

    abstract void start();

}


class Car extends Vehicle{

    void start(){

        System.out.println("Car starts with key");

    }

}


public class Main{

    public static void main(String[] args){

        Car c1 = new Car();

        c1.start();

    }

}
```

---

# Output

```
Car starts with key
```

---

# Dry Run

### Step 1

Java creates an abstract class:

```java
Vehicle
```

It contains:

```
start()
```

but does not know how the vehicle starts.

---

### Step 2

Car class inherits Vehicle:

```java
class Car extends Vehicle
```

Now Car must define:

```java
start()
```

---

### Step 3

Object creation:

```java
Car c1 = new Car();
```

A Car object is created.

---

### Step 4

Method call:

```java
c1.start();
```

Car's implementation runs.

Output:

```
Car starts with key
```

---

# Important Rule of Abstract Class

We cannot create an object of an abstract class.

Invalid:

```java
Vehicle v = new Vehicle();
```

Reason:

Vehicle does not have complete behavior.

It only defines a common idea.

---

# Abstract Class with Constructor

Many beginners think abstract classes cannot have constructors.

That is false.

Example:

```java
abstract class Animal{

    Animal(){

        System.out.println("Animal created");

    }

}


class Dog extends Animal{

}


public class Main{

    public static void main(String[] args){

        Dog d = new Dog();

    }

}
```

Output:

```
Animal created
```

The child object calls the parent constructor.

---

# Interface

An interface is another way to achieve abstraction.

It defines what a class must do.

It focuses on behavior.

Example:

```java
interface Payment{

    void pay();

}
```

Any class implementing Payment must provide:

```java
pay()
```

implementation.

---

# Example Using Interface

```java
interface Payment{

    void pay();

}


class UPI implements Payment{

    public void pay(){

        System.out.println("Payment using UPI");

    }

}


public class Main{

    public static void main(String[] args){

        UPI payment = new UPI();

        payment.pay();

    }

}
```

---

# Output

```
Payment using UPI
```

---

# Abstract Class vs Interface

| Abstract Class | Interface |
|---|---|
| Uses abstract keyword | Uses interface keyword |
| Can have abstract and normal methods | Mainly defines behavior |
| Can have constructors | Cannot have constructors |
| Can have instance variables | Variables are public static final by default |
| Supports partial abstraction | Provides complete abstraction |

---

# Abstraction vs Encapsulation

Many students confuse these.

| Abstraction | Encapsulation |
|-|-|
| Hides implementation details | Hides data |
| Focuses on what an object does | Focuses on protecting data |
| Achieved using abstract classes and interfaces | Achieved using access modifiers |
| Example: Driving a car | Example: Private bank balance |

---

# Real-Life Examples

## ATM Machine

You know:

- Withdraw money
- Check balance
- Deposit money

You don't know:

- How bank servers verify transactions.
- How encryption works.

This is abstraction.

---

## Mobile Phone

You use:

- Camera app
- Calling feature

You don't see:

- Image processing algorithms.
- Network communication.

This is abstraction.

---

# Advantages

## 1. Reduces Complexity

Users only see necessary information.

---

## 2. Improves Security

Internal implementation is hidden.

---

## 3. Better Maintainability

Internal code can change without affecting users.

---

## 4. Code Reusability

Common behavior can be defined once.

---

# Disadvantages

- Can increase code complexity.
- Requires proper planning.
- Too much abstraction can make code difficult to understand.

---

# Interview Questions

## 1. What is abstraction?

Abstraction is the process of hiding implementation details and showing only essential features.

---

## 2. How can abstraction be achieved in Java?

Using:

1. Abstract classes
2. Interfaces

---

## 3. Can we create an object of an abstract class?

No.

Because abstract classes may contain incomplete methods.

---

## 4. Can an abstract class have a constructor?

Yes.

---

## 5. Difference between abstraction and encapsulation?

Abstraction hides implementation details.

Encapsulation hides data.

---

## 6. Why do we need abstraction?

To reduce complexity and expose only required functionality.

---

# Key Points

- Abstraction means hiding internal details.
- It focuses on what an object does, not how it does it.
- Java achieves abstraction using abstract classes and interfaces.
- Abstract classes can contain both abstract and normal methods.
- Abstract classes cannot be instantiated.
- Interfaces define a contract that classes must follow.
- Abstraction makes large applications easier to design and maintain.

---

# Summary

Imagine using a car.

You only know:

```
Start
Accelerate
Brake
```

You don't know:

```
Engine combustion process
Fuel injection system
Transmission mechanism
```

The car hides its complexity and provides simple controls.

That is abstraction in Object-Oriented Programming.