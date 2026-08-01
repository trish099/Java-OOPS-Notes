# Methods and Constructors

## Introduction

In Java, every object can perform some actions.

For example,

A Car can:
- Start
- Stop
- Accelerate

A Student can:
- Study
- Attend Classes
- Give Exams

These actions are represented using **methods**.

Similarly, whenever we create an object, Java needs a way to initialize it.

This is where **constructors** come into the picture.

Although methods and constructors look similar, they have completely different purposes.

---

# What is a Method?

A method is a block of code that performs a specific task.

Instead of writing the same code again and again, we place it inside a method and call it whenever required.

Think of a method as an action.

Example:

A mobile phone can:

- Call
- Send Message
- Open Camera
- Play Music

These actions are methods.

---

# Why do we need Methods?

Imagine printing a welcome message 100 times.

Without methods:

```java
System.out.println("Welcome");
System.out.println("Welcome");
System.out.println("Welcome");
```

This becomes repetitive.

Instead,

```java
displayMessage();
displayMessage();
displayMessage();
```

The code becomes shorter, cleaner and easier to maintain.

---

# Syntax of a Method

```java
returnType methodName(){

    // Code

}
```

Example:

```java
void greet(){

    System.out.println("Welcome!");

}
```

Here,

- `void` → The method does not return anything.
- `greet` → Method name.
- `{}` → Body of the method.

---

# Example of a Method

```java
class Student{

    void study(){

        System.out.println("Student is studying.");

    }

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

        s1.study();

    }

}
```

### Output

```
Student is studying.
```

---

# Dry Run

### Step 1

Java creates the Student class.

It contains one method:

```java
study()
```

---

### Step 2

```java
Student s1 = new Student();
```

A Student object is created.

---

### Step 3

```java
s1.study();
```

Java calls the study() method.

Everything inside the method executes.

---

# What is a Constructor?

A constructor is a special method that is automatically called whenever an object is created.

Its main purpose is to initialize an object.

Example:

Suppose every Student object should have:

- Name
- Age

Instead of assigning them one by one after creating the object,

we can initialize them automatically using a constructor.

---

# Why do we need Constructors?

Without constructors,

```java
Student s1 = new Student();

s1.name = "Utsav";
s1.age = 19;
```

Every time we create an object, we have to assign values manually.

With constructors,

```java
Student s1 = new Student("Utsav",19);
```

Everything is initialized in one line.

---

# Rules of a Constructor

A constructor:

- Has the same name as the class.
- Has no return type.
- Is called automatically when an object is created.
- Can take parameters.

---

# Syntax

```java
class Student{

    Student(){

    }

}
```

Notice,

There is **no return type**.

Not even `void`.

---

# Default Constructor

If we do not write any constructor,

Java automatically provides one.

Example:

```java
class Student{

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

    }

}
```

Java internally creates a default constructor.

---

# Parameterized Constructor

```java
class Student{

    String name;
    int age;

    Student(String n,int a){

        name = n;
        age = a;

    }

}

public class Main{

    public static void main(String[] args){

        Student s1 = new Student("Utsav",19);

        System.out.println(s1.name);
        System.out.println(s1.age);

    }

}
```

### Output

```
Utsav
19
```

---

# Dry Run

### Step 1

```java
Student s1 = new Student("Utsav",19);
```

Memory is allocated.

---

### Step 2

Java automatically calls

```java
Student(String n,int a)
```

---

### Step 3

Inside the constructor,

```java
name = n;
age = a;
```

becomes

```java
name = "Utsav";
age = 19;
```

---

### Step 4

Object is fully initialized.

---

# Constructor vs Method

| Constructor | Method |
|-------------|--------|
| Initializes an object | Performs a task |
| Same name as class | Can have any valid name |
| No return type | Must have a return type (or `void`) |
| Called automatically when an object is created | Called explicitly by the programmer |
| Runs only during object creation | Can be called multiple times |

---

# Real-Life Example

Imagine buying a new smartphone.

When you switch it on for the first time,

it asks you to:

- Select language
- Connect to Wi-Fi
- Sign in
- Set password

This initial setup happens only once.

This is similar to a constructor.

After the phone is ready,

you can:

- Open Camera
- Make Calls
- Play Music
- Send Messages

These are like methods.

---

# Interview Questions

## 1. What is a method?

A method is a block of code that performs a specific task.

---

## 2. What is a constructor?

A constructor is a special member that initializes an object when it is created.

---

## 3. Can a constructor have a return type?

No.

Not even `void`.

---

## 4. Can constructors be overloaded?

Yes.

A class can have multiple constructors with different parameters.

---

## 5. What happens if we don't write a constructor?

Java provides a default constructor, provided no constructor is explicitly defined.

---

## 6. Can we call a constructor manually?

No.

Constructors are invoked automatically during object creation using the `new` keyword.

---

# Key Points

- Methods perform actions.
- Constructors initialize objects.
- Methods can be called many times.
- Constructors are called automatically when an object is created.
- Constructors have the same name as the class.
- Constructors do not have a return type.
- Java provides a default constructor if none is written.
- Constructors can also take parameters.

---

# Summary

Think of a student joining a university.

When admission happens:

- Name is entered.
- Roll number is assigned.
- Branch is selected.

This one-time setup is like a **constructor**.

After admission, the student can:

- Study
- Attend lectures
- Give exams
- Participate in events

These everyday actions are like **methods**.

In simple words:

- **Constructor = Initial setup**
- **Method = Actions performed after setup**