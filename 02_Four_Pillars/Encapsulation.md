# Encapsulation in Java

## Definition

Encapsulation is the process of **wrapping data (variables) and methods that operate on that data into a single unit called a class**.

It also means **hiding the internal data of an object and allowing controlled access to it**.

In simple words:

> Encapsulation means protecting data by keeping it private and providing controlled access through methods.

---

# Real-Life Example

Think about a bank account.

Your bank balance is private information.

You cannot directly do:

```
balance = 1000000
```

from outside the bank system.

Instead, the bank provides methods:

```
deposit()
withdraw()
checkBalance()
```

You can access your money only through these controlled methods.

This is encapsulation.

---

# Why do we need Encapsulation?

Without encapsulation:

- Anyone can directly modify important data.
- Data can become invalid.
- Security decreases.
- Code becomes difficult to maintain.

Example:

```java
student.age = -10;
```

Age cannot logically be negative.

Encapsulation prevents such problems by controlling how data is modified.

---

# How is Encapsulation achieved in Java?

Encapsulation is achieved using:

1. Access modifiers
2. Getter and Setter methods

The most commonly used access modifier is:

```
private
```

---

# Access Modifiers

Java provides four access modifiers:

| Modifier | Access |
|---|---|
| private | Only inside the same class |
| default | Same package |
| protected | Same package + child classes |
| public | Everywhere |

For encapsulation, we usually make variables:

```java
private
```

---

# Without Encapsulation

Example:

```java
class Student{

    String name;
    int age;

}


public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

        s1.age = -5;

        System.out.println(s1.age);

    }

}
```

Output:

```
-5
```

Problem:

A student's age cannot be negative.

Anyone can directly modify the variable.

---

# With Encapsulation

We make data private.

Example:

```java
class Student{

    private String name;
    private int age;


    public void setAge(int age){

        if(age > 0){

            this.age = age;

        }

    }


    public int getAge(){

        return age;

    }

}


public class Main{

    public static void main(String[] args){

        Student s1 = new Student();

        s1.setAge(19);

        System.out.println(s1.getAge());

    }

}
```

---

# Output

```
19
```

---

# Dry Run

## Step 1

Object creation:

```java
Student s1 = new Student();
```

A Student object is created.

---

## Step 2

The variables:

```
name
age
```

are private.

They cannot be accessed directly.

Invalid:

```java
s1.age = 19;
```

because age is private.

---

## Step 3

We use:

```java
s1.setAge(19);
```

The setter method receives the value.

---

## Step 4

The setter checks:

```java
if(age > 0)
```

Only valid values are stored.

---

## Step 5

To read the value:

```java
s1.getAge();
```

The getter returns the age.

---

# Getter and Setter Methods

## Getter

A getter method is used to read private data.

Example:

```java
public int getAge(){

    return age;

}
```

It provides controlled access to data.

---

## Setter

A setter method is used to modify private data.

Example:

```java
public void setAge(int age){

    this.age = age;

}
```

It allows validation before changing data.

---

# Understanding this Keyword

In:

```java
this.age = age;
```

There are two age variables.

```
this.age
```

refers to the class variable.

```
age
```

refers to the method parameter.

Example:

```java
class Student{

    int age;


    void setAge(int age){

        this.age = age;

    }

}
```

`this` removes the confusion between both variables.

---

# Encapsulation and Data Hiding

These two terms are related but not exactly the same.

## Data Hiding

Data hiding means restricting direct access to data.

Example:

```java
private int balance;
```

---

## Encapsulation

Encapsulation includes:

- Data hiding
- Providing methods to access the data

Example:

```java
private int balance;


public void deposit(){

}
```

---

# Encapsulation Example: Bank Account

```java
class BankAccount{

    private double balance;


    public void deposit(double amount){

        if(amount > 0){

            balance += amount;

        }

    }


    public double getBalance(){

        return balance;

    }

}


public class Main{

    public static void main(String[] args){

        BankAccount account = new BankAccount();

        account.deposit(5000);

        System.out.println(account.getBalance());

    }

}
```

Output:

```
5000.0
```

---

# Memory Understanding

Example:

```java
Student s1 = new Student();
```

Memory:

```
STACK

s1
 |
 |
 ↓

HEAP

Student Object

private name
private age
```

The data exists in the object but cannot be accessed directly from outside because it is private.

Access happens through methods.

---

# Advantages of Encapsulation

## 1. Data Security

Important information remains protected.

Example:

Bank balance.

---

## 2. Controlled Access

We decide how data can be changed.

Example:

Age cannot be negative.

---

## 3. Code Maintainability

Internal implementation can change without affecting other classes.

---

## 4. Better Flexibility

Validation rules can be added anytime.

---

## 5. Reusability

Encapsulated classes can be reused safely.

---

# Disadvantages

## 1. More Code

Getter and setter methods increase code length.

---

## 2. Requires Planning

Designing proper access methods requires thinking.

---

# Encapsulation vs Abstraction

| Encapsulation | Abstraction |
|-|-|
| Hides data | Hides implementation |
| Protects variables | Hides complexity |
| Uses private variables | Uses abstract classes/interfaces |
| Focuses on security | Focuses on simplicity |

Example:

Encapsulation:

```
Bank balance is private
```

Abstraction:

```
ATM hides banking operations
```

---

# Interview Questions

## 1. What is encapsulation?

Encapsulation is the process of wrapping data and methods together inside a class and restricting direct access to data.

---

## 2. How is encapsulation achieved in Java?

Using:

- private variables
- getter methods
- setter methods

---

## 3. Why do we make variables private?

To prevent unauthorized direct modification of data.

---

## 4. What is the advantage of getter and setter methods?

They provide controlled access and allow validation.

---

## 5. Is encapsulation possible without getters and setters?

Yes.

Using methods that control access in any way.

---

## 6. Difference between encapsulation and data hiding?

Data hiding only restricts access.

Encapsulation combines data hiding with controlled access methods.

---

# Key Points

- Encapsulation means wrapping data and methods together.
- It protects object data from direct access.
- Private variables are used for data hiding.
- Getters read data.
- Setters modify data.
- Validation can be added inside setters.
- Encapsulation improves security and maintainability.
- It is one of the four pillars of OOP.

---

# Summary

Think about a bank account.

You cannot directly change:

```
balance = 100000
```

The bank controls access using:

```
deposit()
withdraw()
checkBalance()
```

Similarly, in Java:

```
Private Data
      |
      ↓
Getter/Setter Methods
      |
      ↓
Controlled Access
```

This is encapsulation.