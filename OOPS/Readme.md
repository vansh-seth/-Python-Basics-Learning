# Python Object Oriented Programming

Python supports object-oriented programming (OOP) paradigm, which focuses on creating objects that encapsulate data and functionality. Here's a breakdown of key OOP concepts in Python:

## Classes and Objects

- **Classes**: A class is a blueprint for creating objects. It defines attributes and methods that objects of the class will have.
- **Objects**: Objects are instances of classes. They have attributes (data) and methods (functions) associated with them.

```python
class Parrot:
    # Class attribute
    species = "bird"

    # Constructor
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Create instances of Parrot class
blu = Parrot("Blu", 10)
woo = Parrot("Woo", 15)

# Access attributes
print(f"{blu.name} is {blu.age} years old")
print(f"{woo.name} is {woo.age} years old")
```

## Inheritance

- **Inheritance**: Inheritance allows a class (subclass) to inherit properties and behavior from another class (superclass).
- **Superclass and Subclass**: Superclass is the parent class, and subclass is the child class that inherits from the superclass.

```python
class Animal:
    def eat(self):
        print("I can eat!")

class Dog(Animal):
    def bark(self):
        print("I can bark! Woof woof!!")

dog1 = Dog()
dog1.eat()
dog1.bark()
```

## Encapsulation

- **Encapsulation**: Encapsulation refers to bundling data (attributes) and methods (functions) that operate on the data into a single unit called a class.
- **Access Control**: Access modifiers like private and public control the access to class members.

```python
class Computer:
    def __init__(self):
        self.__maxprice = 900

    def sell(self):
        print(f"Selling Price: {self.__maxprice}")

    def setMaxPrice(self, price):
        self.__maxprice = price

c = Computer()
c.sell()
c.__maxprice = 1000  # This won't change the price due to encapsulation
c.sell()
c.setMaxPrice(1000)   # This will change the price
c.sell()
```

## Polymorphism

- **Polymorphism**: Polymorphism allows objects to be treated as instances of their superclass. It enables different objects to be treated uniformly based on a common interface.
- **Method Overriding**: Subclasses can override methods of the superclass to provide their own implementation.

```python
class Polygon:
    def render(self):
        print("Rendering Polygon...")

class Square(Polygon):
    def render(self):
        print("Rendering Square...")

class Circle(Polygon):
    def render(self):
        print("Rendering Circle...")

s1 = Square()
s1.render()

c1 = Circle()
c1.render()
```

Object-oriented programming provides a powerful way to organize code, promote reusability, and improve maintainability.

# Python Objects and Classes

In Python, objects and classes are fundamental concepts of object-oriented programming (OOP). Classes serve as blueprints for creating objects, which are instances of those classes.

## Python Classes

A class is a template for creating objects. It encapsulates data for the object and defines methods to operate on that data.

To define a class in Python, use the `class` keyword followed by the class name:

```python
class ClassName:
    # class definition
```

Here's an example of a simple Python class:

```python
class Bike:
    name = ""
    gear = 0
```

In this class:
- `Bike` is the class name.
- `name` and `gear` are attributes with default values.

## Python Objects

An object is an instance of a class. It represents a real-world entity and combines data (attributes) and behavior (methods).

To create an object of a class, use the class name followed by parentheses:

```python
objectName = ClassName()
```

Here's how to create an object of the `Bike` class:

```python
bike1 = Bike()
```

Now, you can use the object to access the class attributes:

```python
bike1.name = "Mountain Bike"
bike1.gear = 11
```

## Example: Python Class and Objects

```python
class Bike:
    name = ""
    gear = 0

bike1 = Bike()
bike1.name = "Mountain Bike"
bike1.gear = 11

print(f"Name: {bike1.name}, Gears: {bike1.gear} ")
```

## Python Methods

Methods are functions defined within a class. They perform operations on the object's data.

Here's an example of a class with a method:

```python
class Room:
    length = 0.0
    breadth = 0.0

    def calculate_area(self):
        print("Area of Room =", self.length * self.breadth)
```

You can call the method using an object of the class:

```python
study_room = Room()
study_room.length = 42.5
study_room.breadth = 30.8
study_room.calculate_area()
```

## Python Constructors

A constructor is a special method in Python that is automatically called when an object is created.

```python
class Bike:
    def __init__(self, name=""):
        self.name = name

bike1 = Bike("Mountain Bike")
```

In this example, `__init__()` is the constructor. It initializes the `name` attribute of the object.

Constructors allow you to initialize object properties when creating objects.

# Python Inheritance

In Python, inheritance is a mechanism that allows a class to inherit properties and methods from another class. This promotes code reusability and helps in creating a logical hierarchy of classes.

## Python Inheritance Syntax

To implement inheritance in Python, you define a subclass that inherits from a superclass using the following syntax:

```python
# define a superclass
class SuperClass:
    # attributes and methods of the superclass

# define a subclass inheriting from SuperClass
class SubClass(SuperClass):
    # attributes and methods of the subclass
```

Here, `SubClass` is the subclass, and `SuperClass` is the superclass that `SubClass` inherits from.

## Example: Python Inheritance

```python
class Animal:
    name = ""
    
    def eat(self):
        print("I can eat")

class Dog(Animal):
    def display(self):
        print("My name is ", self.name)

labrador = Dog()
labrador.name = "Rohu"
labrador.eat()
labrador.display()
```

In this example, `Dog` is a subclass of `Animal`. The `Dog` class inherits the `name` attribute and `eat()` method from the `Animal` class. The `display()` method is defined in the `Dog` class.

## Method Overriding in Python Inheritance

If a method is present in both the superclass and subclass, the method in the subclass overrides the method in the superclass. This is known as method overriding.

```python
class Animal:
    name = ""
    
    def eat(self):
        print("I can eat")

class Dog(Animal):
    def eat(self):
        print("I like to eat bones")

labrador = Dog()
labrador.eat()
```

In this example, the `eat()` method in the `Dog` class overrides the `eat()` method in the `Animal` class.

## The super() Function in Inheritance

The `super()` function allows you to call methods from the superclass within the subclass.

```python
class Animal:
    name = ""
    
    def eat(self):
        print("I can eat")

class Dog(Animal):
    def eat(self):
        super().eat()
        print("I like to eat bones")

labrador = Dog()
labrador.eat()
```

Here, `super().eat()` calls the `eat()` method of the superclass (`Animal`) within the `eat()` method of the subclass (`Dog`).

Inheritance is a powerful feature of object-oriented programming that promotes code reuse and helps in organizing classes effectively.

# Python Multiple Inheritance

In Python, a class can be derived from more than one superclass, a feature known as multiple inheritance. This allows a class to inherit attributes and methods from multiple parent classes.

## Python Multiple Inheritance Syntax

To implement multiple inheritance in Python, you define a class that inherits from multiple superclasses using the following syntax:

```python
class SuperClass1:
    # features of SuperClass1

class SuperClass2:
    # features of SuperClass2

class MultiDerived(SuperClass1, SuperClass2):
    # features of SuperClass1 + SuperClass2 + MultiDerived class
```

Here, the `MultiDerived` class is derived from both `SuperClass1` and `SuperClass2` classes.

## Example: Python Multiple Inheritance

```python
class Mammal:
    def mammal_info(self):
        print("Mammals can give direct birth.")

class WingedAnimal:
    def winged_animal_info(self):
        print("Winged animals can flap.")

class Bat(Mammal, WingedAnimal):
    pass

# create an object of Bat class
b1 = Bat()

b1.mammal_info()
b1.winged_animal_info()
```

In this example, the `Bat` class is derived from both `Mammal` and `WingedAnimal` superclasses. The `Bat` class inherits the `mammal_info()` method from `Mammal` and the `winged_animal_info()` method from `WingedAnimal`.

## Method Resolution Order (MRO) in Python

When a class inherits from multiple superclasses with the same method name, Python uses the Method Resolution Order (MRO) to determine which method to call. The MRO specifies the order in which Python searches for methods in the inheritance hierarchy.

```python
class SuperClass1:
    def info(self):
        print("Super Class 1 method called")

class SuperClass2:
    def info(self):
        print("Super Class 2 method called")

class Derived(SuperClass1, SuperClass2):
    pass

d1 = Derived()
d1.info()  
```

Here, when the `info()` method is called using the `d1` object of the `Derived` class, Python uses the MRO to determine which method to call. In this case, the method from `SuperClass1` is called because it appears first in the inheritance list.

Multiple inheritance is a powerful feature of Python but should be used judiciously to avoid confusion and maintain code readability.

# Python Multilevel Inheritance

In Python, multilevel inheritance refers to the ability to derive a class from another derived class, forming a chain of inheritance. This allows attributes and methods to be inherited across multiple levels of the class hierarchy.

## Multilevel Inheritance Syntax

To implement multilevel inheritance in Python, you define classes that derive from other classes hierarchically. Here's the syntax:

```python
class SuperClass:
    # Super class code here

class DerivedClass1(SuperClass):
    # Derived class 1 code here

class DerivedClass2(DerivedClass1):
    # Derived class 2 code here
```

In this syntax, `DerivedClass1` is derived from `SuperClass`, and `DerivedClass2` is derived from `DerivedClass1`.

## Example: Python Multilevel Inheritance

```python
class SuperClass:
    def super_method(self):
        print("Super Class method called")

# Define class derived from SuperClass
class DerivedClass1(SuperClass):
    def derived1_method(self):
        print("Derived class 1 method called")

# Define class derived from DerivedClass1
class DerivedClass2(DerivedClass1):
    def derived2_method(self):
        print("Derived class 2 method called")

# Create an object of DerivedClass2
d2 = DerivedClass2()

d2.super_method()         # Output: "Super Class method called"
d2.derived1_method()      # Output: "Derived class 1 method called"
d2.derived2_method()      # Output: "Derived class 2 method called"
```

In this example, `DerivedClass2` is derived from `DerivedClass1`, which in turn is derived from `SuperClass`. This creates a multilevel inheritance hierarchy where `DerivedClass2` inherits attributes and methods from both `DerivedClass1` and `SuperClass`.

By creating an object `d2` of `DerivedClass2`, we can access methods from `SuperClass`, `DerivedClass1`, and `DerivedClass2`.

Multilevel inheritance is a powerful feature of object-oriented programming in Python, allowing for code reuse and structuring of classes in a hierarchical manner.
