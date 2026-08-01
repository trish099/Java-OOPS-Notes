# Classes and Objects

## Definition

Classes and Objects are the foundation of Object-Oriented Programming (OOP).

Everything in Java revolves around classes and objects.

---

# What is a Class?

A class is a **blueprint** or **template** used to create objects.

It tells Java:

- What data an object will store.
- What actions an object can perform.

Think of a class as a design or plan.

It does **not** occupy memory for individual objects until an object is created.

### Real-Life Example

Imagine a company that manufactures cars.

Before making a car, engineers create a **design**.

That design contains:

- Engine type
- Number of doors
- Color options
- Fuel type

This design is similar to a **class**.

---

# What is an Object?

An object is a **real instance of a class**.

Objects are created using the class.

Unlike a class, an object occupies memory.

Every object has its own data.

### Example

If Car is a class,

then

- My Audi
- Your BMW
- Friend's Thar

are different objects.

All belong to the Car class but contain different values.

---

# Class vs Object

| Class | Object |
|--------|--------|
| Blueprint | Real instance |
| Logical entity | Physical entity |
| Doesn't store individual values | Stores actual values |
| Doesn't occupy memory for data | Occupies memory |
| Used to create objects | Created from a class |

---

# Syntax

```java
class ClassName{

    // Variables

    // Methods

}

public class Main{

    public static void main(String[] args){

        ClassName objectName = new ClassName();

    }

}
```

---

# First Example

```java
class Student{

    String name;
    int age;

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

        s1.name = "Utsav";
        s1.age = 19;

        System.out.println(s1.name);
        System.out.println(s1.age);

    }

}
```

---

# Output

```
Utsav
19
```

---

# Dry Run

### Step 1

```java
class Student
```

A blueprint called Student is created.

No object exists yet.

---

### Step 2

```java
Student s1 = new Student();
```

Java creates one Student object in memory.

`s1` stores the reference to that object.

---

### Step 3

```java
s1.name = "Utsav";
```

The name variable inside the object now stores "Utsav".

---

### Step 4

```java
s1.age = 19;
```

The age variable stores 19.

---

### Step 5

```java
System.out.println(s1.name);
```

Prints

```
Utsav
```

---

# Multiple Objects

One class can create many objects.

```java
class Student{

    String name;
    int age;

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student();
        Student s2 = new Student();

        s1.name = "Rahul";
        s1.age = 18;

        s2.name = "Priya";
        s2.age = 20;

        System.out.println(s1.name + " " + s1.age);
        System.out.println(s2.name + " " + s2.age);

    }

}
```

### Output

```
Rahul 18
Priya 20
```

Notice that both objects belong to the same class but store different values.

---

# Why Do We Need Classes?

Imagine creating details for 10,000 students.

Without classes, you would need thousands of variables.

Classes let us create as many objects as we need using the same blueprint.

This reduces code duplication and makes programs easier to maintain.

---

# Real-Life Analogy

Think of a cookie cutter.

- Cookie Cutter → Class
- Cookies → Objects

One cookie cutter can create many cookies.

Similarly, one class can create many objects.

---

# Interview Questions

## 1. What is a class?

A class is a blueprint or template used to create objects.

---

## 2. What is an object?

An object is an instance of a class that stores actual data.

---

## 3. Can we create multiple objects from one class?

Yes.

A single class can create any number of objects.

---

## 4. Does a class occupy memory?

The class itself does not store individual object data.

Memory for data is allocated when objects are created.

---

## 5. What is the difference between a class and an object?

A class is the blueprint.

An object is the actual implementation of that blueprint.

---

# Key Points

- A class is a blueprint.
- An object is an instance of a class.
- Objects store actual data.
- One class can create multiple objects.
- Objects are created using the `new` keyword.
- Every object has its own copy of instance variables.

---

# Summary

Suppose a university has a **Student** class.

The class defines that every student has:

- Name
- Age
- Roll Number

Now create three students:

- Utsav
- Rahul
- Priya

All three are different objects.

Each stores different values but follows the same class design.

This is the basic idea behind Classes and Objects in Java.