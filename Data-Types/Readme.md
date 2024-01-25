# Python Numbers, Type Conversion, and Mathematics

Python offers various data types to handle numeric values. These include integers, floating-point numbers, and complex numbers, each with its own characteristics and uses.

## Python Numeric Data Type

Integers and floating points are distinguished by the presence or absence of a decimal point:

- Integers (`int`) hold signed integers of non-limited length.
- Floating-point numbers (`float`) hold decimal values and are accurate up to 15 decimal places.
- Complex numbers (`complex`) are written in the form `x + yj`, where `x` is the real part and `y` is the imaginary part.

```python
num1 = 5
print(num1, 'is of type', type(num1))

num2 = 5.42
print(num2, 'is of type', type(num2))

num3 = 8+2j
print(num3, 'is of type', type(num3))
```

In the above example, `num1` is an integer, `num2` is a float, and `num3` is a complex number.

## Number Systems

Computer programmers often work with binary (base 2), hexadecimal (base 16), and octal (base 8) number systems in addition to the decimal (base 10) system. Python supports these number systems with appropriate prefixes:

- Binary: `0b` or `0B`
- Octal: `0o` or `0O`
- Hexadecimal: `0x` or `0X`

```python
print(0b1101011)  # prints 107
print(0xFB + 0b10)  # prints 253
print(0o15)  # prints 13
```

## Type Conversion in Python

Python supports implicit and explicit type conversions:

- Implicit conversions occur automatically during operations like addition and subtraction.
- Explicit conversions are done using functions like `int()`, `float()`, and `complex()`.

```python
print(1 + 2.0)  # prints 3.0

num1 = int(2.3)
print(num1)  # prints 2

num2 = int(-2.8)
print(num2)  # prints -2

num3 = float(5)
print(num3) # prints 5.0

num4 = complex('3+5j')
print(num4)  # prints (3 + 5j)
```

## Python Random Module

The `random` module provides functions to generate random numbers or pick random items from an iterator.

```python
import random

print(random.randrange(10, 20))  # prints a random integer between 10 and 19

list1 = ['a', 'b', 'c', 'd', 'e']

print(random.choice(list1))  # prints a random item from list1

random.shuffle(list1)  # shuffles list1
print(list1)  # prints the shuffled list1

print(random.random())  # prints a random float between 0 and 1
```

## Python Mathematics

Python's `math` module offers various mathematical functions:

```python
import math

print(math.pi)
print(math.cos(math.pi))
print(math.exp(10))
print(math.log10(1000))
print(math.sinh(1))
print(math.factorial(6))
```

These functions enable operations like trigonometry, logarithms, and statistical calculations.

Feel free to explore further and utilize these features in your Python projects.

# Python Lists

In Python, lists are used to store multiple data at once, allowing for the management of collections of items efficiently.

## List Elements

Lists can contain elements of different types and can store duplicate elements. We create a list by placing elements inside square brackets `[]`, separated by commas.

```python
# Creating a list
ages = [19, 26, 23]
print(ages)  # Output: [19, 26, 23]
```

## Accessing List Elements

Python lists are ordered, and each item is associated with an index number. We use these index numbers to access list items. Indexing starts at 0.

```python
languages = ["Python", "Swift", "C++"]
print(languages[0])   # Output: Python
print(languages[-1])  # Output: C++
```

## Slicing Lists

We can use slicing to access a portion of a list using the slicing operator `:`. Slicing allows us to extract elements based on their positions within the list.

```python
my_list = ['p','r','o','g','r','a','m','i','z']
print(my_list[2:5])  # Output: ['o', 'g', 'r']
print(my_list[5:])   # Output: ['a', 'm', 'i', 'z']
```

## Adding and Removing Elements

Python lists are mutable, meaning we can add and remove elements. We can use methods like `append()`, `extend()`, `insert()`, `remove()`, and `del` to modify lists.

```python
numbers = [21, 34, 54, 12]
numbers.append(32)  # Adds 32 to the end of the list
print(numbers)      # Output: [21, 34, 54, 12, 32]

languages.remove('Swift')  # Removes 'Swift' from the list
print(languages)           # Output: ['Python', 'C++']
```

## List Methods

Python lists offer a variety of methods for manipulation, including appending, extending, inserting, removing, sorting, and more.

```python
# Example methods:
numbers.append(32)
numbers.extend([40, 50])
numbers.insert(2, 28)
numbers.remove(34)
del numbers[0]
numbers.sort()
```

## List Comprehension

List comprehension is a concise way to create lists in Python. It allows for the creation of lists based on existing iterables, such as range objects or other lists.

```python
# Creating a list using list comprehension
squared_numbers = [n ** 2 for n in range(1, 6)]
print(squared_numbers)  # Output: [1, 4, 9, 16, 25]
```

Lists are fundamental data structures in Python, offering flexibility and versatility for managing collections of data efficiently.
