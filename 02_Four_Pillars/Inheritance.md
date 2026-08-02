# Inheritance in Java

## Definition

Inheritance is an Object-Oriented Programming concept where one class acquires the properties and behaviors of another class.

The class which gives its properties and methods is called the:

**Parent Class / Super Class / Base Class**

The class which receives those properties and methods is called:

**Child Class / Sub Class / Derived Class**

In simple words:

> Inheritance allows us to reuse existing code by creating a new class from an existing class.

---

# Why do we need Inheritance?

Imagine we are creating a software system for a company.

We have:

- Employee
- Manager
- Developer
- Tester

All employees have common properties:

```
name
age
salary
```

and common methods:

```
work()
login()
logout()
```

Without inheritance, we would write the same code again and again.

Example:

```
Employee
    name
    age
    salary

Developer
    name
    age
    salary

Manager
    name
    age
    salary
```

This creates code duplication.

With inheritance:

```
        Employee
            |
    ----------------
    |              |
 Developer      Manager
```

Developer and Manager automatically get Employee features.

---

# Basic Terminology

## Parent Class

The class whose properties are inherited.

Example:

```java
class Animal{

}
```

Animal is the parent class.

---

## Child Class

The class that inherits from another class.

Example:

```java
class Dog extends Animal{

}
```

Dog is the child class.

---

# Syntax

```java
class ParentClass{

    // properties
    // methods

}


class ChildClass extends ParentClass{

    // additional properties
    // additional methods

}
```

The keyword used for inheritance is:

```java
extends
```

---

# Basic Example

```java
class Animal{

    String name;

    void eat(){

        System.out.println("Animal is eating");

    }

}


class Dog extends Animal{

    void bark(){

        System.out.println("Dog is barking");

    }

}


public class Main{

    public static void main(String[] args){

        Dog d1 = new Dog();

        d1.name = "Tommy";

        d1.eat();

        d1.bark();

    }

}
```

---

# Output

```
Animal is eating
Dog is barking
```

---

# Dry Run

## Step 1

Java creates the parent class:

```java
Animal
```

It contains:

```
name
eat()
```

---

## Step 2

Dog inherits Animal:

```java
class Dog extends Animal
```

Now Dog has:

```
name
eat()
```

and its own:

```
bark()
```

---

## Step 3

Object creation:

```java
Dog d1 = new Dog();
```

A Dog object is created.

Because Dog inherits Animal, it can access Animal members.

---

## Step 4

Calling:

```java
d1.eat();
```

Although eat() is written inside Animal, Dog can use it.

Output:

```
Animal is eating
```

---

# Types of Inheritance in Java

Java supports different inheritance types.

---

# 1. Single Inheritance

One parent and one child.

Example:

```
Animal
   |
   Dog
```

Code:

```java
class Animal{

}


class Dog extends Animal{

}
```

---

# 2. Multilevel Inheritance

A class inherits from another inherited class.

Example:

```
Animal
   |
 Mammal
   |
 Dog
```

Code:

```java
class Animal{

}


class Mammal extends Animal{

}


class Dog extends Mammal{

}
```

---

# 3. Hierarchical Inheritance

Multiple child classes inherit from one parent class.

Example:

```
        Animal
        /    \
      Dog    Cat
```

Code:

```java
class Animal{

}


class Dog extends Animal{

}


class Cat extends Animal{

}
```

---

# Multiple Inheritance

Multiple inheritance means one class inherits from multiple classes.

Example:

```
A       B
 \     /
   C
```

Java does NOT support this using classes.

Example:

```java
class C extends A,B
{

}
```

This is not allowed.

---

# Why Java does not support Multiple Inheritance?

Because it creates ambiguity.

Example:

```java
class A{

    void show(){

        System.out.println("A");

    }

}


class B{

    void show(){

        System.out.println("B");

    }

}
```

Now:

```java
class C extends A,B
{

}
```

If we call:

```java
c.show();
```

Which method should execute?

A's show() or B's show()?

This confusion is called the:

**Diamond Problem**

Java avoids this problem by not allowing multiple inheritance with classes.

---

# The super Keyword

`super` refers to the parent class object.

It is used to:

1. Access parent variables.
2. Call parent methods.
3. Call parent constructors.

Example:

```java
class Animal{

    String color = "White";

}


class Dog extends Animal{

    String color = "Black";


    void display(){

        System.out.println(color);

        System.out.println(super.color);

    }

}
```

Output:

```
Black
White
```

---

# Constructor in Inheritance

When a child object is created:

First parent constructor runs.

Then child constructor runs.

Example:

```java
class Animal{

    Animal(){

        System.out.println("Animal constructor");

    }

}


class Dog extends Animal{

    Dog(){

        System.out.println("Dog constructor");

    }

}


public class Main{

    public static void main(String[] args){

        Dog d = new Dog();

    }

}
```

Output:

```
Animal constructor
Dog constructor
```

---

# Method Overriding and Inheritance

A child class can provide its own implementation of a parent method.

Example:

```java
class Animal{

    void sound(){

        System.out.println("Animal sound");

    }

}


class Dog extends Animal{

    void sound(){

        System.out.println("Bark");

    }

}
```

Dog changes the behavior of sound().

This is called:

**Method Overriding**

(Important concept for Polymorphism)

---

# Real-Life Example

Consider vehicles.

Parent Class:

```
Vehicle

Properties:
- speed
- color

Methods:
- start()
- stop()
```

Child Classes:

```
Car
Bike
Truck
```

All vehicles can start and stop.

But each has different features.

Car:

```
openTrunk()
```

Bike:

```
kickStart()
```

Inheritance allows common features to be reused.

---

# Advantages

## 1. Code Reusability

Existing code can be reused.

---

## 2. Reduces Duplication

Common functionality is written once.

---

## 3. Easy Maintenance

Changes in parent class can automatically affect children.

---

## 4. Better Organization

Classes are arranged in a logical hierarchy.

---

# Disadvantages

## 1. Tight Coupling

Child classes depend heavily on parent classes.

---

## 2. Less Flexibility

Changes in parent may affect multiple child classes.

---

## 3. Wrong Usage Can Make Code Complex

Deep inheritance chains can become difficult to understand.

---

# Interview Questions

## 1. What is inheritance?

Inheritance is a mechanism where one class acquires properties and methods of another class.

---

## 2. Which keyword is used for inheritance in Java?

The `extends` keyword.

---

## 3. What is the parent class?

The class whose properties are inherited.

---

## 4. What is the child class?

The class that inherits properties from another class.

---

## 5. Does Java support multiple inheritance?

Java does not support multiple inheritance using classes because of ambiguity.

---

## 6. What is the advantage of inheritance?

It provides code reusability and reduces duplication.

---

# Key Points

- Inheritance allows one class to acquire another class's features.
- Parent class provides properties and methods.
- Child class receives and can extend those features.
- `extends` keyword is used.
- Java supports single, multilevel, and hierarchical inheritance.
- Java does not support multiple inheritance using classes.
- `super` keyword is used to access parent members.
- Constructors execute from parent to child.
- Method overriding is closely related to inheritance.

---

# Summary

Think of inheritance like family relationships.

A child inherits characteristics from parents.

Similarly:

```
Parent Class
      |
      ↓
Child Class
```

The child receives existing features and can add its own new features.

Inheritance helps programmers reuse code and create organized software designs.