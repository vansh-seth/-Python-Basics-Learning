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

In the above example, we created a list of fruits, a tuple of numbers, a dictionary of alphabets, and a set of vowels.


