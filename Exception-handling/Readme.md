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
