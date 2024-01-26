# Python Exceptions

An exception is an unexpected event that occurs during program execution. It represents errors that are beyond the control of the programmer and need to be handled.

## Python Logical Errors (Exceptions)

Errors that occur at runtime (after passing the syntax test) are called exceptions or logical errors. Some common exceptions include:

- `FileNotFoundError`: Raised when trying to open a file that does not exist.
- `ZeroDivisionError`: Raised when trying to divide a number by zero.
- `ImportError`: Raised when trying to import a module that does not exist.

When exceptions occur, Python creates an exception object and prints a traceback along with details about why the error occurred.

## Python Built-in Exceptions

Illegal operations can raise various built-in exceptions in Python. Some common built-in exceptions and their causes include:

- `AssertionError`: Raised when an assert statement fails.
- `AttributeError`: Raised when attribute assignment or reference fails.
- `EOFError`: Raised when the `input()` function hits the end-of-file condition.
- `KeyError`: Raised when a key is not found in a dictionary.
- `MemoryError`: Raised when an operation runs out of memory.
- `TypeError`: Raised when a function or operation is applied to an object of incorrect type.
- `ValueError`: Raised when a function gets an argument of the correct type but improper value.
- `ZeroDivisionError`: Raised when the second operand of a division or modulo operation is zero.
- Many more...

## Python Error and Exception Handling

Errors represent conditions such as compilation errors, syntax errors, library incompatibility, etc., which are usually beyond the control of the programmer and should not be handled.

Exceptions, on the other hand, can be caught and handled by the program.

In Python, we can handle exceptions using `try`, `except`, and `finally` statements. These statements allow us to gracefully handle unexpected errors and continue program execution.

# Python Exception Handling

Exception handling in Python allows us to gracefully handle errors that may occur during program execution. This helps in preventing the program from crashing unexpectedly and allows us to respond to errors in a controlled manner.

## Python `try...except` Block

The `try...except` block is used to handle exceptions in Python. Here's the syntax:

```python
try:
    # code that may cause exception
except:
    # code to run when exception occurs
```

In this block:
- We place the code that might generate an exception inside the `try` block.
- The `except` block catches the exception and executes the code inside it.

### Example: Exception Handling Using `try...except`

```python
try:
    numerator = 10
    denominator = 0

    result = numerator / denominator

    print(result)
except:
    print("Error: Denominator cannot be 0.")
```

In this example, if the denominator is 0, it generates an exception which is caught by the `except` block.

## Catching Specific Exceptions in Python

For each `try` block, there can be zero or more `except` blocks. Multiple `except` blocks allow us to handle different exceptions differently.

```python
try:
    even_numbers = [2, 4, 6, 8]
    print(even_numbers[5])
except ZeroDivisionError:
    print("Denominator cannot be 0.")
except IndexError:
    print("Index Out of Bound.")
```

Here, we handle `ZeroDivisionError` and `IndexError` separately.

## Python `try` with `else` Clause

The `else` clause allows us to run a certain block of code if the `try` block runs without any errors.

```python
try:
    num = int(input("Enter a number: "))
    assert num % 2 == 0
except:
    print("Not an even number!")
else:
    reciprocal = 1 / num
    print(reciprocal)
```

In this example, if the number is even, the reciprocal is computed and displayed.

## Python `try...finally`

The `finally` block is always executed no matter whether there is an exception or not.

```python
try:
    numerator = 10
    denominator = 0

    result = numerator / denominator

    print(result)
except:
    print("Error: Denominator cannot be 0.")
finally:
    print("This is finally block.")
```

In this example, regardless of whether an exception occurs or not, the code in the `finally` block is always executed.

