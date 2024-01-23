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
```
