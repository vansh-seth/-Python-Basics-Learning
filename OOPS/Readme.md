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


```python
# Python Objects and Classes

# Define a class
class Bike:
    # Class attributes
    name = ""
    gear = 0

# Create an object of the class
bike1 = Bike()

# Access attributes and assign values
bike1.gear = 11
bike1.name = "Mountain Bike"

print(f"Name: {bike1.name}, Gears: {bike1.gear} ")

# Create multiple objects of the class
class Employee:
    # Class attribute
    employee_id = 0

# Create two objects of the Employee class
employee1 = Employee()
employee2 = Employee()

# Access attributes using employee1
employee1.employeeID = 1001
print(f"Employee ID: {employee1.employeeID}")

# Access attributes using employee2
employee2.employeeID = 1002
print(f"Employee ID: {employee2.employeeID}")

# Define a class with method
class Room:
    length = 0.0
    breadth = 0.0
    
    # Method to calculate area
    def calculate_area(self):
        print("Area of Room =", self.length * self.breadth)

# Create an object of Room class
study_room = Room()

# Assign values to attributes
study_room.length = 42.5
study_room.breadth = 30.8

# Access method inside class
study_room.calculate_area()

# Constructors in Python
class Car:
    # Constructor function
    def __init__(self, model=""):
        self.model = model

# Create object with default value
car1 = Car()
print(f"Car Model: {car1.model}")

# Create object with specific value
car2 = Car("Toyota")
print(f"Car Model: {car2.model}")
```

Output:
```
Name: Mountain Bike, Gears: 11 
Employee ID: 1001
Employee ID: 1002
Area of Room = 1309.0
Car Model: 
Car Model: Toyota
```

In the above code:
- We define classes `Bike`, `Employee`, `Room`, and `Car`.
- Create objects of these classes and access attributes and methods.
- Demonstrates the use of constructors (`__init__()` method) to initialize attributes during object creation.
