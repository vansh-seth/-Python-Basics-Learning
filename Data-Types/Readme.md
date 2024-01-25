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

# Python Tuples

In Python, a tuple is similar to a list, but the main difference is that tuples are immutable, meaning their elements cannot be changed after creation. Tuples are created by placing elements inside parentheses `()`, separated by commas.

## Creating a Tuple

Tuples can contain elements of different types and may be nested. Here are examples of different types of tuples:

```python
# Different types of tuples

# Empty tuple
my_tuple = ()
print(my_tuple)  # Output: ()

# Tuple with integers
my_tuple = (1, 2, 3)
print(my_tuple)  # Output: (1, 2, 3)

# Tuple with mixed datatypes
my_tuple = (1, "Hello", 3.4)
print(my_tuple)  # Output: (1, 'Hello', 3.4)

# Nested tuple
my_tuple = ("mouse", [8, 4, 6], (1, 2, 3))
print(my_tuple)  # Output: ('mouse', [8, 4, 6], (1, 2, 3))
```

## Accessing Tuple Elements

Tuple elements are accessed using indexing and slicing, similar to lists.

```python
letters = ("p", "r", "o", "g", "r", "a", "m", "i", "z")

print(letters[0])    # Accessing the first element: 'p'
print(letters[-1])   # Accessing the last element using negative indexing: 'z'
print(letters[1:4])  # Slicing to get elements from index 1 to 3: ('r', 'o', 'g')
```

## Tuple Methods

Tuples have limited methods compared to lists due to their immutable nature. Some common tuple methods include `count()` and `index()`.

```python
my_tuple = ('a', 'p', 'p', 'l', 'e',)
print(my_tuple.count('p'))  # Count occurrences of 'p': 2
print(my_tuple.index('l'))  # Find the index of 'l': 3
```

## Iterating Through a Tuple

We can iterate through a tuple using a `for` loop.

```python
languages = ('Python', 'Swift', 'C++')

# Iterating through the tuple
for language in languages:
    print(language)
```

## Advantages of Tuples over Lists

- Tuples are immutable, making them faster for iteration and write-protected.
- Tuples with immutable elements can be used as dictionary keys.
- Tuples are generally used for heterogeneous data types.

Tuples are a useful data structure when you need to store data that shouldn't be changed after creation.

# Python Strings

In computer programming, a string is a sequence of characters. In Python, strings can be represented using either single quotes (`'`) or double quotes (`"`). Here's how to create strings:

```python
# Creating strings
string1 = "Python programming"
string2 = 'Python programming'

print(string1)
print(string2)
```

Strings in Python can contain any characters, including letters, numbers, symbols, and spaces.

## Accessing String Characters

We can access individual characters in a string using indexing and slicing.

```python
greet = 'hello'

# Accessing the first character
print(greet[0])  # Output: 'h'

# Slicing to get a substring
print(greet[1:4])  # Output: 'ell'
```

It's important to note that Python strings are immutable, meaning their characters cannot be changed after creation.

## Multiline Strings

Python supports multiline strings, which are defined using triple quotes (`"""` or `'''`).

```python
# Multiline string
message = """
Never gonna give you up
Never gonna let you down
"""

print(message)
```

## String Operations

Python offers various operations for working with strings, including:

- Comparing strings
- Joining strings
- Iterating through strings
- Finding the length of a string
- Checking for string membership
- Using string methods like `upper()`, `lower()`, `replace()`, `split()`, etc.

```python
# Example of string operations
greet = "Hello, "
name = "Jack"

# Joining strings
result = greet + name
print(result)  # Output: Hello, Jack

# Iterating through a string
for letter in greet:
    print(letter)

# Finding the length of a string
print(len(greet))  # Output: 5

# Checking for string membership
print('a' in 'program')  # Output: True
```

## Escape Sequences

Escape sequences in Python are used to include special characters inside a string. Some common escape sequences include `\n` for a newline and `\'` for a single quote.

```python
# Using escape sequences
example = 'He said, "What\'s there?"'
print(example)  # Output: He said, "What's there?"
```

## String Formatting (f-Strings)

Python's f-Strings provide an easy way to format strings by embedding expressions inside curly braces `{}`.

```python
# String formatting with f-Strings
name = 'Cathy'
country = 'UK'

print(f'{name} is from {country}')
```

f-Strings make string formatting more concise and readable.

Strings are fundamental data types in Python and are widely used in various applications.
