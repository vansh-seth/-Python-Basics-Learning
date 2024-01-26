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


# Python Sets

A set in Python is a collection of unique elements, meaning that each element in a set is distinct and there are no duplicates allowed.

## Creating a Set in Python

In Python, sets are created by placing elements inside curly braces `{}`. Here are some examples:

```python
# Create a set of integers
student_id = {112, 114, 116, 118, 115}
print('Student ID:', student_id)

# Create a set of string type
vowel_letters = {'a', 'e', 'i', 'o', 'u'}
print('Vowel Letters:', vowel_letters)

# Create a set of mixed data types
mixed_set = {'Hello', 101, -2, 'Bye'}
print('Set of mixed data types:', mixed_set)
```

## Handling Empty Sets

To create an empty set in Python, you cannot use empty curly braces `{}` as it creates an empty dictionary. Instead, you use the `set()` function without any arguments:

```python
# Create an empty set
empty_set = set()
print('Data type of empty_set:', type(empty_set))
```

```python
# Duplicate Items in a Set
# Let's see what will happen if we try to include duplicate items in a set.

numbers = {2, 4, 6, 6, 2, 8}
print(numbers)   # {8, 2, 4, 6}
```

In the above code snippet, notice that even though we tried to include duplicate items in the set `numbers`, the set only retains unique elements. When you print `numbers`, you'll observe those duplicate elements are automatically removed by the set, and unique elements are preserved.

```python
# Add and Update Set Items in Python
# Sets are mutable. However, since they are unordered, indexing has no meaning.
# We cannot access or change an element of a set using indexing or slicing. Set data type does not support it.

# Add Items to a Set in Python
# In Python, we use the add() method to add an item to a set. For example,

numbers = {21, 34, 54, 12}

print('Initial Set:', numbers)

# using add() method
numbers.add(32)

print('Updated Set:', numbers)
```

In the code above, we first create a set named `numbers`. Then, we use the `add()` method to add the element `32` to the set. Notice that sets are unordered, so the order of elements in the set may not match the order in which they were added.

```python
# Update Python Set
# The update() method is used to update the set with items other collection types (lists, tuples, sets, etc). For example,

companies = {'Lacoste', 'Ralph Lauren'}
tech_companies = ['apple', 'google', 'apple']

companies.update(tech_companies)

print(companies)

# Output: {'google', 'apple', 'Lacoste', 'Ralph Lauren'}
```

In the code above, the `update()` method adds all the unique elements from the `tech_companies` list to the `companies` set. Duplicates are automatically removed since sets only contain unique elements.

```python
# Remove an Element from a Set
# We use the discard() method to remove the specified element from a set. For example,

languages = {'Swift', 'Java', 'Python'}

print('Initial Set:', languages)

# remove 'Java' from a set
removedValue = languages.discard('Java')

print('Set after remove():', languages)
```

In the code above, the `discard()` method removes the element `'Java'` from the `languages` set if it exists. If the element is not present in the set, `discard()` does nothing.

```python
# Built-in Functions with Set
# Built-in functions like all(), any(), enumerate(), len(), max(), min(), sorted(), sum() etc. are commonly used with sets to perform different tasks.

# Iterate Over a Set in Python
fruits = {"Apple", "Peach", "Mango"}

# for loop to access each fruit
for fruit in fruits: 
    print(fruit)
```

In the code above, we iterate over the set `fruits` using a for loop and print each element.

```python
# Find Number of Set Elements
# We can use the len() method to find the number of elements present in a Set. For example,

even_numbers = {2, 4, 6, 8}
print('Set:', even_numbers)

# find number of elements
print('Total Elements:', len(even_numbers))
```

In the code above, we use the `len()` method to determine the number of elements in the set `even_numbers` and print the result.

```markdown
Output:

Set: {8, 2, 4, 6}
Total Elements: 4
```

This shows that the set `even_numbers` contains 4 elements.

## Set Operations

Python sets support various operations such as union, intersection, difference, and symmetric difference.

### Union of Two Sets

The union of two sets includes all elements from both sets, without duplicates.

```python
# Union of two sets
A = {1, 3, 5}
B = {0, 2, 4}

print('Union using |:', A | B)
print('Union using union():', A.union(B))
```

### Intersection of Two Sets

The intersection of two sets includes only the elements that are common to both sets.

```python
# Intersection of two sets
A = {1, 3, 5}
B = {1, 2, 3}

print('Intersection using &:', A & B)
print('Intersection using intersection():', A.intersection(B))
```

### Difference between Two Sets

The difference between two sets includes elements that are in the first set but not in the second set.

```python
# Difference between two sets
A = {2, 3, 5}
B = {1, 2, 6}

print('Difference using -:', A - B)
print('Difference using difference():', A.difference(B))
```

### Symmetric Difference

The symmetric difference between two sets includes elements that are in either of the sets, but not in both.

```python
# Symmetric difference between two sets
A = {2, 3, 5}
B = {1, 2, 6}

print('Using ^:', A ^ B)
print('Using symmetric_difference():', A.symmetric_difference(B))
```

## Set Methods

Python sets provide various built-in methods for performing operations like adding elements, removing elements, and more. Here are some commonly used set methods:

- `add()`
- `remove()`
- `discard()`
- `union()`
- `intersection()`
- `difference()`
- `symmetric_difference()`
- `update()`

Sets are versatile data structures in Python, useful for tasks requiring unique elements and set operations.


# Python Dictionary

A Python dictionary is a collection of items that allows us to store data in key: value pairs.

## Create a Dictionary

We create a dictionary by placing key: value pairs inside curly brackets `{}`, separated by commas. For example,

```python
# creating a dictionary
country_capitals = {
  "Germany": "Berlin", 
  "Canada": "Ottawa", 
  "England": "London"
}

# printing the dictionary
print(country_capitals)
```

**Output**

```
{'Germany': 'Berlin', 'Canada': 'Ottawa', 'England': 'London'}
```

The `country_capitals` dictionary has three elements (key-value pairs), where Germany is the key and Berlin is the value assigned to it and so on.

### Key Value Pairs in a Dictionary

**Notes:**

- Dictionary keys must be immutable, such as tuples, strings, integers, etc. We cannot use mutable (changeable) objects such as lists as keys.
- We can also create a dictionary using a Python built-in function `dict()`.

**Valid and Invalid Dictionaries:**

- Keys of a dictionary must be immutable
- Keys of a dictionary must be unique

## Access Dictionary Items

We can access the value of a dictionary item by placing the key inside square brackets.

```python
country_capitals = {
  "Germany": "Berlin", 
  "Canada": "Ottawa", 
  "England": "London"
}

# access the value of keys
print(country_capitals["Germany"])    # Output: Berlin
print(country_capitals["England"])    # Output: London
```

**Note:** We can also use the `get()` method to access dictionary items.

## Add Items to a Dictionary

We can add an item to a dictionary by assigning a value to a new key. For example,

```python
country_capitals = {
  "Germany": "Berlin", 
  "Canada": "Ottawa", 
}

# add an item with "Italy" as key and "Rome" as its value
country_capitals["Italy"] = "Rome"

print(country_capitals)
```

**Output**

```
{'Germany': 'Berlin', 'Canada': 'Ottawa', 'Italy': 'Rome'}
```

## Remove Dictionary Items

We can use the `del` statement to remove an element from a dictionary. For example,

```python
country_capitals = {
  "Germany": "Berlin", 
  "Canada": "Ottawa", 
}

# delete item having "Germany" key
del country_capitals["Germany"]

print(country_capitals)
```

**Output**

```
{'Canada': 'Ottawa'}
```

**Note:** We can also use the `pop()` method to remove an item from a dictionary.

If we need to remove all items from a dictionary at once, we can use the `clear()` method.

## Change Dictionary Items

Python dictionaries are mutable (changeable). We can change the value of a dictionary element by referring to its key. For example,

```python
country_capitals = {
  "Germany": "Berlin", 
  "Italy": "Naples", 
  "England": "London"
}

# change the value of "Italy" key to "Rome"
country_capitals["Italy"] = "Rome"

print(country_capitals)
```

**Output**

```
{'Germany': 'Berlin', 'Italy': 'Rome', 'England': 'London'}
```

**Note:** We can also use the `update()` method to add or change dictionary items.

## Iterate Through a Dictionary

A dictionary is an ordered collection of items (starting from Python 3.7), therefore it maintains the order of its items.

We can iterate through dictionary keys one by one using a for loop.

```python
country_capitals = {
  "United States": "Washington D.C.", 
  "Italy": "Rome" 
}

# print dictionary keys one by one
for country in country_capitals:
    print(country)

print()

# print dictionary values one by one
for country in country_capitals:
    capital = country_capitals[country]
    print(capital)
```

**Output**

```
United States
Italy

Washington D.C.
Rome
```

## Find Dictionary Length

We can find the length of a dictionary by using the `len()` function.

```python
country_capitals = {"England": "London", "Italy": "Rome"}

# get dictionary's length
print(len(country_capitals))   # Output: 2

numbers = {10: "ten", 20: "twenty", 30: "thirty"}

# get dictionary's length
print(len(numbers))            # Output: 3

countries = {}

# get dictionary's length
print(len(countries))          # Output: 0
```

## Python Dictionary Methods

Here are some of the commonly used dictionary methods.

| Function   | Description                                |
|------------|--------------------------------------------|
| pop()      | Removes the item with the specified key.   |
| update()   | Adds or changes dictionary items.          |
| clear()    | Remove all the items from the dictionary.  |
| keys()     | Returns all the dictionary's keys.         |
| values()   | Returns all the dictionary's values.       |
| get()      | Returns the value of the specified key.    |
| popitem()  | Returns the last inserted key and value as a tuple. |
| copy()     | Returns a copy of the dictionary.          |

## Dictionary Membership Test

We can check whether a key exists in a dictionary by using the `in` and `not in` operators.

```python
file_types = {
    ".txt": "Text File",
    ".pdf": "PDF Document",
    ".jpg": "JPEG Image",
}

# use of in and not in operators
print(".pdf" in file_types)       # Output: True
print(".mp3" in file_types)       # Output: False
print(".mp3" not in file_types)   # Output: True
```

**Note:** The `in` operator checks whether a key exists; it doesn't check whether a value exists or not.
