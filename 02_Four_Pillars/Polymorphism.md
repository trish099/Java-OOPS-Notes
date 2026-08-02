# Polymorphism in Java

## Definition

Polymorphism is an Object-Oriented Programming concept where **one thing can have many forms**.

The word polymorphism comes from:

- Poly → Many
- Morph → Forms

In simple words:

> Polymorphism allows the same method or object to behave differently in different situations.

---

# Real-Life Example

Think about a person.

One person can have different roles:

- At home → Father
- At university → Student
- At work → Employee

The same person behaves differently depending on the situation.

This is polymorphism.

---

# Why do we need Polymorphism?

Without polymorphism, we would need different method names for every behavior.

Example:

```
dogSound()
catSound()
cowSound()
```

This becomes difficult to manage.

With polymorphism:

```
sound()
```

The same method can behave differently for different objects.

```
Dog → Bark
Cat → Meow
Cow → Moo
```

---

# Types of Polymorphism in Java

Java mainly supports two types:

1. Compile-Time Polymorphism
2. Runtime Polymorphism

---

# 1. Compile-Time Polymorphism

Compile-time polymorphism is achieved using:

## Method Overloading

Method overloading means having multiple methods with the same name but different parameters.

The compiler decides which method to call.

That is why it is called compile-time polymorphism.

---

# Method Overloading Example

```java
class Calculator{


    int add(int a, int b){

        return a + b;

    }


    int add(int a, int b, int c){

        return a + b + c;

    }


    double add(double a, double b){

        return a + b;

    }

}


public class Main{


    public static void main(String[] args){

        Calculator c = new Calculator();


        System.out.println(c.add(10,20));

        System.out.println(c.add(10,20,30));

        System.out.println(c.add(5.5,4.5));

    }

}
```

---

# Output

```
30
60
10.0
```

---

# Dry Run

When Java sees:

```java
c.add(10,20);
```

It checks:

```
add(int,int)
```

and calls that method.

---

When Java sees:

```java
c.add(10,20,30);
```

It calls:

```
add(int,int,int)
```

---

When Java sees:

```java
c.add(5.5,4.5);
```

It calls:

```
add(double,double)
```

---

The compiler decides the method before execution.

Therefore:

```
Compile-Time Polymorphism
```

---

# Rules of Method Overloading

Methods must have different:

- Number of parameters
- Type of parameters
- Order of parameters

Example:

Valid:

```java
add(int,int)

add(int,int,int)

add(double,double)
```

Invalid:

```java
add(int,int)

int add(int,int)
```

Changing only return type is not enough.

---

# 2. Runtime Polymorphism

Runtime polymorphism is achieved using:

## Method Overriding

Method overriding occurs when a child class provides its own implementation of a parent class method.

It is related to inheritance.

---

# Method Overriding Example

```java
class Animal{


    void sound(){

        System.out.println("Animal makes sound");

    }

}



class Dog extends Animal{


    void sound(){

        System.out.println("Dog barks");

    }

}



class Cat extends Animal{


    void sound(){

        System.out.println("Cat meows");

    }

}



public class Main{


    public static void main(String[] args){


        Animal a;


        a = new Dog();

        a.sound();


        a = new Cat();

        a.sound();


    }

}
```

---

# Output

```
Dog barks
Cat meows
```

---

# Understanding Runtime Polymorphism

Look at:

```java
Animal a;
```

The reference type is Animal.

But:

```java
a = new Dog();
```

The actual object is Dog.

When:

```java
a.sound();
```

Java checks the actual object type.

Since the object is Dog:

```
Dog's sound()
```

runs.

---

# Memory Representation

Code:

```java
Animal a = new Dog();
```

Memory:

```
STACK

a
|
|
↓


HEAP

Dog Object
-------------
sound()
```

The reference is of Animal type.

The object is of Dog type.

The object's method is executed.

---

# Method Overloading vs Method Overriding

| Method Overloading | Method Overriding |
|---|---|
| Compile-time polymorphism | Runtime polymorphism |
| Same class | Parent-child classes |
| Same method name, different parameters | Same method name and parameters |
| Decided by compiler | Decided during execution |
| Does not require inheritance | Requires inheritance |

---

# Important Rules of Method Overriding

1. Method name must be same.

2. Parameters must be same.

3. Child method cannot have more restrictive access.

Example:

Parent:

```java
public void show()
```

Child cannot:

```java
private void show()
```

---

# super Keyword with Overriding

`super` is used to call the parent version of an overridden method.

Example:

```java
class Animal{


    void sound(){

        System.out.println("Animal sound");

    }

}



class Dog extends Animal{


    void sound(){

        super.sound();

        System.out.println("Dog bark");

    }

}
```

Output:

```
Animal sound
Dog bark
```

---

# Real-Life Example

## Payment System

Imagine an online shopping app.

Different payment methods:

```
Payment
   |
----------------
|              |
UPI          Card
```

All have:

```
pay()
```

But implementation differs.

UPI:

```
Pay using UPI
```

Card:

```
Pay using Card
```

The same method behaves differently.

This is polymorphism.

---

# Advantages of Polymorphism

## 1. Code Flexibility

The same code can work with different objects.

---

## 2. Code Reusability

Less duplicate code.

---

## 3. Easy Maintenance

Adding new behavior becomes easier.

---

## 4. Better Design

Large applications become easier to manage.

---

# Disadvantages

## 1. Complexity

Too much polymorphism can make code difficult to understand.

---

## 2. Runtime Overhead

Runtime polymorphism requires method lookup during execution.

---

# Polymorphism with Inheritance

Polymorphism usually works together with inheritance.

Example:

```
        Animal
          |
     -------------
     |           |
    Dog         Cat
```

Parent reference can point to different child objects:

```java
Animal a;

a = new Dog();

a = new Cat();
```

---

# Interview Questions

## 1. What is polymorphism?

Polymorphism is the ability of an object to take multiple forms and behave differently.

---

## 2. What are the types of polymorphism in Java?

1. Compile-time polymorphism
2. Runtime polymorphism

---

## 3. How is compile-time polymorphism achieved?

Using method overloading.

---

## 4. How is runtime polymorphism achieved?

Using method overriding.

---

## 5. Difference between overloading and overriding?

Overloading happens in the same class with different parameters.

Overriding happens between parent and child classes with the same method.

---

## 6. Why is method overriding called runtime polymorphism?

Because JVM decides which method to execute during program execution.

---

# Key Points

- Polymorphism means many forms.
- It allows the same method to behave differently.
- Method overloading gives compile-time polymorphism.
- Method overriding gives runtime polymorphism.
- Runtime polymorphism requires inheritance.
- Parent reference can store child objects.
- It improves flexibility and code reusability.

---

# Summary

Imagine a remote control.

The same button:

```
Power ON
```

can work differently for:

```
TV → Turns on screen

AC → Starts cooling

Music System → Starts playing music
```

The action is the same, but the behavior changes.

This is polymorphism.