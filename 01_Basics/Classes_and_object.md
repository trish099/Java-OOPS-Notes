# What is Object-Oriented Programming (OOP)?

## Definition

Object-Oriented Programming (OOP) is a way of writing programs by thinking in terms of **objects** rather than just instructions.

An object is anything that has:

* **Data (State)** → What it has.
* **Behavior (Methods)** → What it can do.

Almost everything around us can be considered an object.

For example:

* Car
* Student
* Mobile Phone
* Laptop
* Bank Account

All of these have some information (data) and can perform some actions (behavior).

Java is mainly based on the Object-Oriented Programming paradigm.

---

# Why was OOP introduced?

Imagine you have to write software for a college.

The college has:

* 20,000 students
* 500 teachers
* Hundreds of classrooms
* Thousands of courses

If we write everything in one big file using only variables and functions, the code quickly becomes:

* difficult to understand
* difficult to modify
* difficult to debug
* difficult to reuse

OOP solves this problem by dividing the program into small independent objects.

Instead of thinking,

> "How should I write this program?"

we think,

> "What objects exist in this system?"

For a college management system, the objects could be:

* Student
* Teacher
* Course
* Library
* Classroom

Each object handles its own work.

This makes the code much cleaner.

---

# What is a Class?

A **class** is a blueprint or design for creating objects.

Think of it like the blueprint of a house.

A blueprint tells us:

* How many rooms the house will have.
* Where the doors will be.
* Where the windows will be.

But...

You cannot live inside the blueprint.

Similarly,

A class only describes an object.

It is **not** the actual object.

Example:

```
Student

Properties:
- name
- age
- rollNumber

Methods:
- study()
- attendClass()
- giveExam()
```

This is only the design.

No actual student has been created yet.

---

# What is an Object?

An **object** is a real instance of a class.

If "Student" is a class,

Then

Student 1

* Name: Rahul
* Age: 19

Student 2

* Name: Priya
* Age: 20

Student 3

* Name: Aman
* Age: 18

are different objects.

They all belong to the same class but store different values.

One class can create thousands or even millions of objects.

---

# Properties (State)

Properties are the information stored inside an object.

For a Car:

```
Brand
Color
Price
Speed
Fuel Type
```

These describe the current state of the car.

Different cars can have different values.

---

# Methods (Behavior)

Methods define what an object can do.

For a Car:

```
start()
stop()
accelerate()
brake()
```

These actions are called behaviors.

---

# Simple Java Example

```java
class Car {

    // Properties (State)
    String brand;
    String color;

    // Method (Behavior)
    void start() {
        System.out.println(brand + " is starting...");
    }
}

public class Main {

    public static void main(String[] args) {

        // Creating an object
        Car car1 = new Car();

        // Assigning values
        car1.brand = "Audi";
        car1.color = "Black";

        // Accessing properties
        System.out.println(car1.brand);
        System.out.println(car1.color);

        // Calling method
        car1.start();
    }
}
```

---

# Dry Run (Line by Line)

### Step 1

```java
class Car
```

Java creates a blueprint called **Car**.

No object exists yet.

---

### Step 2

```java
Car car1 = new Car();
```

This line creates the first object.

Memory is allocated for this object.

Now `car1` refers to that object.

---

### Step 3

```java
car1.brand = "Audi";
```

The `brand` property of `car1` now stores `"Audi"`.

---

### Step 4

```java
car1.color = "Black";
```

The `color` property now stores `"Black"`.

---

### Step 5

```java
System.out.println(car1.brand);
```

Output:

```
Audi
```

---

### Step 6

```java
car1.start();
```

The `start()` method is executed.

Since `brand = "Audi"`,

Output becomes:

```
Audi is starting...
```

---

# Output

```
Audi
Black
Audi is starting...
```

---

# Why is OOP so popular?

Large applications like:

* Instagram
* WhatsApp
* Amazon
* Flipkart
* Banking Systems

contain millions of lines of code.

Without OOP, managing such applications would be extremely difficult.

OOP makes software:

* Organized
* Reusable
* Easy to maintain
* Easy to expand

---

# Advantages

### 1. Code Reusability

Write once, use many times.

---

### 2. Better Organization

Every object manages its own work.

---

### 3. Easier Maintenance

If one class has a bug, we usually fix only that class instead of the whole program.

---

### 4. Real-World Modeling

Real-world things can be represented naturally.

Example:

Student

Car

Employee

Bank Account

Hospital

---

### 5. Security

OOP allows us to hide important data from direct access using encapsulation.

---

# Disadvantages

* Requires more planning before coding.
* Uses slightly more memory than simple procedural programs.
* Can feel complex for very small programs.

---

# Real-Life Analogy

Imagine a classroom.

The **Student** class defines:

* Name
* Roll Number
* Branch

Every student in the classroom is an object.

Although every student belongs to the same class, each has different values.

This is exactly how objects work in Java.

---

# Interview Questions

### What is OOP?

OOP is a programming paradigm that organizes programs using objects containing data and methods.

---

### What is a class?

A class is a blueprint used to create objects.

---

### What is an object?

An object is an instance of a class.

---

### What is the difference between a class and an object?

| Class                         | Object               |
| ----------------------------- | -------------------- |
| Blueprint                     | Real instance        |
| No memory for individual data | Occupies memory      |
| Used to create objects        | Created from a class |

---

### Why do we use OOP?

Because it makes programs modular, reusable, maintainable, secure, and closer to real-world design.

---

# Key Points

* OOP stands for Object-Oriented Programming.
* Java is primarily object-oriented.
* A class is a blueprint.
* An object is an actual instance of a class.
* Objects contain **state (properties)** and **behavior (methods)**.
* One class can create many objects.
* OOP becomes especially useful when building large software systems.
