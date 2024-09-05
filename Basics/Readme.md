# Python Basics
## Python Keywords and Identifiers
## Python Keywords

Keywords are predefined, reserved words used in Python programming that have special meanings to the compiler. We cannot use a keyword as a variable name, function name, or any other identifier. They are used to define the syntax and structure of the Python language.

All the keywords except `True`, `False`, and `None` are in lowercase and must be written as they are. The list of all the keywords is given below:

```
False   await     else     import     pass
None    break     except   in         raise
True    class     finally  is         return
and     continue  for      lambda     try
as      def       from     nonlocal   while
assert  del       global   not        with
async   elif      if       or         yield
```


## Python Identifiers

Identifiers are the names given to variables, classes, methods, etc. For example:

```python
language = 'Python'
```

Here, `language` is a variable (an identifier) that holds the value 'Python'. We cannot use keywords as variable names, as they are reserved names built into Python. For example:

```python
continue = 'Python'
```

The above code is incorrect because we have used `continue` as a variable name.

### Rules for Naming an Identifier

1. Identifiers cannot be a keyword.
2. Identifiers are case-sensitive.
3. They can have a sequence of letters and digits but must begin with a letter or `_`. The first letter of an identifier cannot be a digit.
4. It's a convention to start an identifier with a letter rather than `_`.
5. Whitespaces are not allowed.
6. Special symbols like `!`, `@`, `#`, `$`, etc., cannot be used.

### Some Valid and Invalid Identifiers in Python

| Valid Identifiers      | Invalid Identifiers |
|------------------------|----------------------|
| score                  | @core                |
| return_value           | return               |
| highest_score         | highest score        |
| name1                  | 1name                |
| convert_to_string      | convert to_string    |

### Things to Remember

- Python is a case-sensitive language. This means `Variable` and `variable` are not the same.
- Always give identifiers a name that makes sense. While `c = 10` is a valid name, writing `count = 10` would make more sense and be easier to understand.
- Multiple words can be separated using an underscore, like `this_is_a_long_variable`.

## Python Comments

Comments are sentences that we add to our code to make it easier to understand. When executing code, Python's interpreter ignores comments.

For example, we have a program to print a text entered by the user.

```python
name = input("Enter your name")
print(name)
```

To make this program more readable, we can add comments like:

```python
# Program to take the user's name

name = input('Enter your name')
print(name)
```

The line starting with # is a comment. The Python compiler ignores everything after the # symbol.

### Single-line Comment

We use the hash(#) symbol to write a single-line comment. For example,

```python
# declare a variable
name = 'John'

# print name
print(name)    # John
```
In the above example, we have used three single-line comments:

```python
# declare a variable
# print name
# John
```

We can also use single-line comments alongside the code:

```python
print(name)    # John
```

### Multiline Comments

Python doesn't have dedicated multi-line comment syntax.
we can achieve the same effect by using the hash (#) symbol at the beginning of each line.

example:

```python
# print(1)
# print(2)
# print(3)
```

We can also use multiline strings as comments like:

```python
'''This program takes an input from the user
and prints it'''

name = input('Enter your name: ')
print(name)
```

**Output:**

```
Enter your name: John
John
```

We can see that these unassigned multiline strings are ignored.

### Prevent Executing Code Using Comments

Comments are valuable when debugging code. If we encounter an error while running a program, instead of removing code segments, we can comment them out to prevent execution.

For example,

```python
number1 = 10
number2 = 15

sum = number1 + number2

print('The sum is:', sum)
print('The product is:', product)
```

Here, the code throws an error because we have not defined a product variable.

We can comment out the code that's causing the error.

For example,

```python
number1 = 10
number2 = 15

sum = number1 + number2

print('The sum is:', sum)
# print('The product is:', product)
```

**Output:**

```
The sum is 25
```

Now, the code runs without any errors.

Here, we have resolved the error by commenting out the code related to the product.

If we need to calculate the product soon, we can uncomment it.

### Why Use Comments?

We should use comments for the following reasons:

- Comments make our code readable for future reference.
- Comments are used for debugging purposes.
- We can use comments for code collaboration as it helps peer developers to understand our code.


## Python Variables, Constants, and Literals

## Python Variables

A variable is a container to hold data. For example,

```python
number = 10
```

Here, `number` is the variable storing the value `10`.

### Assigning Values to Variables in Python

As seen in the above example, we use the assignment operator `=` to assign a value to a variable.

```python
# assign value to site_name variable
site_name = 'vanish'

print(site_name)

# Output: vanish
```

Note: Python is a type-inferred language, so you don't have to explicitly define the variable type.

### Changing the Value of a Variable in Python

```python
site_name = 'vansh'
print(site_name)

# assigning a new value to site_name
site_name = 'apple'

print(site_name)
```

**Output:**
```
vansh
apple
```

Here, the value of `site_name` is changed from 'vansh' to 'apple'.

### Example: Assigning multiple values to multiple variables

```python
a, b, c = 5, 3.2, 'Hello'

print(a)  # prints 5
print(b)  # prints 3.2
print(c)  # prints Hello 
```

If we want to assign the same value to multiple variables at once, we can do this as:

```python
site1 = site2  = 'vansh'

print(site1)  # prints vansh
print(site2)  # prints vansh
```

Here, we have assigned the same string value 'vansh' to both the variables `site1` and `site2`.

### Rules for Naming Python Variables

- Constant and variable names should have a combination of letters in lowercase (a to z) or uppercase (A to Z) or digits (0 to 9) or an underscore (_).
- Create a name that makes sense.
- If you want to create a variable name having two words, use an underscore to separate them.
- Python is case-sensitive.
- Avoid using keywords like if, True, class, etc. as variable names.

## Python Constants

A constant is a special type of variable whose value cannot be changed.

In Python, constants are usually declared and assigned in a module.

```python
# declare constants 
PI = 3.14
GRAVITY = 9.8
```

### Python Literals

Literals are representations of fixed values in a program. They can be numbers, characters, or strings, etc.

```python
site_name = 'vansh'
```

Here, `site_name` is a variable, and 'vansh' is a literal.

### Python Numeric Literals

Numeric Literals are immutable (unchangeable) and can be of three different types: Integer, Float, and Complex.

- Decimal: `5`, `10`, `-68`
- Binary: `0b101`, `0b11`
- Octal: `0o13`
- Hexadecimal: `0x13`

### Python Boolean Literals

There are two boolean literals: `True` and `False`.

```python
result1 = True  
```

Here, `True` is a boolean literal assigned to `result1`.

### String and Character Literals in Python

Character literals are unicode characters enclosed in a quote.

```python
some_character = 'S'
```

Here, `S` is a character literal assigned to `some_character`.

Similarly, String literals are sequences of Characters enclosed in quotation marks.

```python
some_string = 'Python is fun' 
```

Here, 'Python is fun' is a string literal assigned to `some_string`.

### Special Literal in Python

Python contains one special literal `None`. We use it to specify a null variable.

```python
value = None

print(value)

# Output: None
```

Here, we get `None` as an output as the `value` variable has no value assigned to it.

### Literal Collections

There are four different literal collections: List literals, Tuple literals, Dict literals, and Set literals.

```python
# list literal
fruits = ["apple", "mango", "orange"] 
print(fruits)

# tuple literal
numbers = (1, 2, 3) 
print(numbers)

# dictionary literal
alphabets = {'a':'apple', 'b':'ball', 'c':'cat'} 
print(alphabets)

# set literal
vowels = {'a', 'e', 'i' , 'o', 'u'} 
print(vowels)
```

**Output:**
```
['apple', 'mango', 'orange']
(1, 2, 3)
{'a': 'apple', 'b': 'ball', 'c': 'cat'}
{'e', 'a', 'o', 'i', 'u'}
```

## Python Data Types

In computer programming, data types specify the type of data that can be stored inside a variable. For example,

```python
num = 24
```

Here, `24` (an integer) is assigned to the `num` variable. So the data type of `num` is of the `int` class.

## Python Data Types

| Data Types | Classes        | Description                       |
|------------|----------------|-----------------------------------|
| Numeric    | int, float, complex | holds numeric values             |
| String     | str            | holds a sequence of characters    |
| Sequence   | list, tuple, range | holds a collection of items       |
| Mapping    | dict           | holds data in key-value pair form |
| Boolean    | bool           | holds either True or False        |
| Set        | set, frozenset  | holds a collection of unique items|

Since everything is an object in Python programming, data types are actually classes and variables are instances (objects) of these classes.

## Python Numeric Data type

In Python, the numeric data type is used to hold numeric values.

- `int`: holds signed integers of non-limited length.
- `float`: holds floating decimal points and is accurate up to 15 decimal places.
- `complex`: holds complex numbers.

Let's see an example,

```python
num1 = 5
print(num1, 'is of type', type(num1))

num2 = 2.0
print(num2, 'is of type', type(num2))

num3 = 1+2j
print(num3, 'is of type', type(num3))
```

Output:

```
5 is of type <class 'int'>
2.0 is of type <class 'float'>
(1+2j) is of type <class 'complex'>
```

## Python List Data Type

A list is an ordered collection of similar or different types of items separated by commas and enclosed within brackets [ ].

For example,

```python
languages = ["Swift", "Java", "Python"]
```

Access List Items:

To access items from a list, we use the index number (0, 1, 2 ...). For example,

```python
languages = ["Swift", "Java", "Python"]

# access element at index 0
print(languages[0])   # Swift

# access element at index 2
print(languages[2])   # Python
```


## Python Tuple Data Type

A tuple is an ordered sequence of items, same as a list. The only difference is that tuples are immutable. Tuples, once created, cannot be modified.

In Python, we use parentheses () to store items in a tuple. For example,

```python
product = ('Xbox', 499.99)
```

Access Tuple Items:

Similar to lists, we use the index number to access tuple items in Python. For example,

```python
# create a tuple 
product = ('Microsoft', 'Xbox', 499.99)

# access element at index 0
print(product[0])   # Microsoft

# access element at index 1
print(product[1])   # Xbox
```

## Python String Data Type

A string is a sequence of characters represented by either single or double quotes. For example,

```python
name = 'Python'
print(name)  

message = 'Python for beginners'
print(message)
```

Output:

```
Python
Python for beginners
```

In the above example, we have created string-type variables: `name` and `message` with values 'Python' and 'Python for beginners' respectively.


## Python Set Data Type

A set is an unordered collection of unique items. A set is defined by values separated by commas inside braces { }.

For example,

```python
# create a set named student_id
student_id = {112, 114, 116, 118, 115}

# display student_id elements
print(student_id)

# display the type of student_id
print(type(student_id))
```

Output:

```
{112, 114, 115, 116, 118}
<class 'set'>
```

Here, we have created a set named `student_info` with 5 integer values.

Since sets are unordered collections, indexing has no meaning. Hence, the slicing operator [] does not work.

## Python Dictionary Data Type

A Python dictionary is an ordered collection of items. It stores elements in key/value pairs.

Here, keys are unique identifiers that are associated with each value.

Let's see an example,

```python
# create a dictionary named capital_city
capital_city = {'Nepal': 'Kathmandu', 'Italy': 'Rome', 'England': 'London'}

print(capital_city)
```

Output:

```
{'Nepal': 'Kathmandu', 'Italy': 'Rome', 'England': 'London'}
```

In the above example, we have created a dictionary named `capital_city`. Here,

- Keys are 'Nepal', 'Italy', 'England'
- Values are 'Kathmandu', 'Rome', 'London'

### Access Dictionary Values Using Keys

We use keys to retrieve the respective value. But not the other way around. For example,

```python
# create a dictionary named capital_city
capital_city = {'Nepal': 'Kathmandu', 'Italy': 'Rome', 'England': 'London'}

print(capital_city['Nepal'])  # prints Kathmandu

# throws an error message 
print(capital_city['Kathmandu'])
```

Here, we have accessed values using keys from the `capital_city` dictionary.

Since 'Nepal' is a key, `capital_city['Nepal']` accesses its respective value i.e., Kathmandu.

However, 'Kathmandu' is the value for the 'Nepal' key, so `capital_city['Kathmandu']` throws an error message.

## Python Type Conversion

In programming, type conversion is the process of converting data of one type to another, such as converting int data to str.

There are two types of type conversion in Python.

1. **Implicit Conversion - automatic type conversion**
2. **Explicit Conversion - manual type conversion**

## Python Implicit Type Conversion

In certain situations, Python automatically converts one data type to another. This is known as implicit type conversion.

### Example 1: Converting integer to float

Let's see an example where Python promotes the conversion of the lower data type (integer) to the higher data type (float) to avoid data loss.

```python
integer_number = 123
float_number = 1.23

new_number = integer_number + float_number

# display new value and resulting data type
print("Value:", new_number)
print("Data Type:", type(new_number))
```

**Output:**
```
Value: 124.23
Data Type: <class 'float'>
```

In the above example, Python converts the smaller data type (integer) to the larger data type (float) to avoid the loss of data.

Note:
- We get TypeError if we try to add str and int. For example, '12' + 23. Python is not able to use Implicit Conversion in such conditions.
- Python has a solution for these types of situations known as Explicit Conversion.

## Explicit Type Conversion

In Explicit Type Conversion, users convert the data type of an object to the required data type using built-in functions like int(), float(), str(), etc.

This type of conversion is also called typecasting because the user casts (changes) the data type of the objects.

### Example 2: Addition of string and integer Using Explicit Conversion

```python
num_string = '12'
num_integer = 23

print("Data type of num_string before Type Casting:", type(num_string))

# explicit type conversion
num_string = int(num_string)

print("Data type of num_string after Type Casting:", type(num_string))

num_sum = num_integer + num_string

print("Sum:", num_sum)
print("Data type of num_sum:", type(num_sum))
```

**Output:**
```
Data type of num_string before Type Casting: <class 'str'>
Data type of num_string after Type Casting: <class 'int'>
Sum: 35
Data type of num_sum: <class 'int'>
```

In the above example, we use `int()` to perform explicit type conversion of `num_string` to an integer type. After conversion, Python can add these two variables.

## Key Points to Remember

- Type Conversion is the conversion of an object from one data type to another data type.
- Implicit Type Conversion is automatically performed by the Python interpreter.
- Python avoids the loss of data in Implicit Type Conversion.
- Explicit Type Conversion is also called Type Casting, and the data types of objects are converted using predefined functions by the user.
- In Type Casting, loss of data may occur as we enforce the object to a specific data type.

## Python Basic Input and Output

## Python Output

In Python, we use the `print()` function to display output. For example,

```python
print('Python is powerful')
```

**Output:**
```
Python is powerful
```

The `print()` function can take multiple parameters:

```python
print(object=, separator=, end=, file=, flush=)
```

- `object`: value(s) to be printed
- `sep` (optional): separates multiple objects inside `print()`
- `end` (optional): adds specific values like new line "\n" or tab "\t"
- `file` (optional): where the values are printed (default is `sys.stdout` - screen)
- `flush` (optional): boolean specifying if the output is flushed or buffered (default: False)

### Example 1: Python Print Statement

```python
print('Good Morning!')
print('It is rainy today')
```

**Output:**
```
Good Morning!
It is rainy today
```

### Example 2: Python print() with end Parameter

```python
print('Good Morning!', end=' ')
print('It is rainy today')
```

**Output:**
```
Good Morning! It is rainy today
```

### Example 3: Python print() with sep parameter

```python
print('New Year', 2023, 'See you soon!', sep='. ')
```

**Output:**
```
New Year. 2023. See you soon!
```

### Example: Print Python Variables and Literals

```python
number = -10.6
name = "Programiz"

# print literals
print(5)

# print variables
print(number)
print(name)
```

**Output:**
```
5
-10.6
Programiz
```

### Example: Print Concatenated Strings

```python
print('Programiz is ' + 'awesome.')
```

**Output:**
```
Programiz is awesome.
```

## Output formatting

We can use the `str.format()` method for output formatting. For example,

```python
x = 5
y = 10

print('The value of x is {} and y is {}'.format(x, y))
```

## Python Input

To take input from the user, we use the `input()` function.

### Example: Python User Input

```python
# using input() to take user input
num = input('Enter a number: ')

print('You Entered:', num)
print('Data type of num:', type(num))
```

**Output:**
```
Enter a number: 10
You Entered: 10
Data type of num: <class 'str'>
```

In this example, `input()` is used to take user input, and the entered value is stored in the `num` variable. It's important to note that the entered value is a string, and to convert it to a number, we can use `int()` or `float()` functions.


