# Python Functions

A function is a block of code that performs a specific task.

Suppose, you need to create a program to create a circle and color it. You can create two functions to solve this problem:

1. create a circle function
2. create a color function

Dividing a complex problem into smaller chunks makes our program easy to understand and reuse.

## Types of Functions
There are two types of functions in Python programming:

1. **Standard Library Functions**: These are built-in functions in Python that are available to use.
2. **User-defined Functions**: We can create our own functions based on our requirements.

## Python Function Declaration
The syntax to declare a function is:

```python
def function_name(arguments):
    # function body 
    return
```

Here,
- `def` - keyword used to declare a function
- `function_name` - any name given to the function
- `arguments` - any value passed to function
- `return` (optional) - returns value from a function

Let's see an example,

```python
def greet():
    print('Hello World!')
```

This function doesn't have any arguments and doesn't return any values. We will learn about arguments and return statements later in this tutorial.

## Calling a Function in Python
In the above example, we have declared a function named `greet()`.

```python
# call the function
greet()
```

### Example: Python Function

```python
def greet():
    print('Hello World!')

# call the function
greet()

print('Outside function')
```

Output:

```
Hello World!
Outside function
```

In the above example, we have created a function named `greet()`. Here's how the program works:

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/d259a712-e775-419d-8231-2312d8363151)

Here,
- When the function is called, the control of the program goes to the function definition.
- All codes inside the function are executed.
- The control of the program jumps to the next statement after the function call.

## Python Function Arguments
As mentioned earlier, a function can also have arguments. An argument is a value that is accepted by a function. For example,

```python
# function with two arguments
def add_numbers(num1, num2):
    sum = num1 + num2
    print('Sum: ',sum)

# function with no argument
def add_numbers():
    # code
```

If we create a function with arguments, we need to pass the corresponding values while calling them. For example,

```python
# function call with two values
add_numbers(5, 4)

# function call with no value
add_numbers()
```

### Example 1: Python Function Arguments

```python
# function with two arguments
def add_numbers(num1, num2):
    sum = num1 + num2
    print("Sum: ",sum)

# function call with two values
add_numbers(5, 4)
```

Output:

```
Sum: 9
```

In the above example, we have created a function named `add_numbers()` with arguments: `num1` and `num2`.

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/e5925888-9068-478c-8ee5-4161ec9bfbb2)

We can also call the function by mentioning the argument name as:

```python
add_numbers(num1 = 5, num2 = 4)
```

In Python, we call it Keyword Argument (or named argument). The code above is equivalent to

```python
add_numbers(5, 4)
```

### Example 2: Function return Type

```python
# function definition
def find_square(num):
    result = num * num
    return result

# function call
square = find_square(3)

print('Square:',square)
```

Output:

```
Square: 9
```

In the above example, we have created a function named `find_square()`. The function accepts a number and returns the square of the number.

## How Functions Work in Python?

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/b6439e52-5c20-4a83-abde-0e4675519c22)

### Example 3: Add Two Numbers

```python
# function that adds two numbers
def add_numbers(num1, num2):
    sum = num1 + num2
    return sum

# calling function with two values
result = add_numbers(5, 4)

print('Sum: ', result)
```

## Python Library Functions
In Python, standard library functions are the built-in functions that can be used directly in our program. For example,

- `print()` - prints the string inside the quotation marks
- `sqrt()` - returns the square root of a number
- `pow()` - returns the power of a number

These library functions are defined inside the module. And, to use them we must include the module inside our program.

### Example 4: Python Library Function

```python
import math

# sqrt computes the square root
square_root = math.sqrt(4)

print("Square Root of 4 is",square_root)

# pow() comptes the power
power = pow(2, 3)

print("2 to the power 3 is",power)
```

Output:

```
Square Root of 4 is 2.0
2 to the power 3 is 8
```

In the above example, we have used:

- `math.sqrt(4)` - to compute the square root of 4
- `pow(2, 3)` - computes the power of a number i.e. 2^3

Here, notice the statement,

```python
import math
```

Since `sqrt()` is defined inside the `math` module, we need to include it in our program.

## Benefits of Using Functions
1. **Code Reusable**: We can use the same function multiple times in our program which makes our code reusable. For example,

```python
# function definition
def get_square(num):
    return num * num

for i in [1,2,3]:
    # function call
    result = get_square(i)
    print('Square of',i, '=',result)
```

Output:

```
Square of 1 = 1
Square of 2 = 4
Square of 3 = 9
```

In the above example, we have created the function named `get_square()` to calculate the square of a number. Here, the function is used to calculate the square of numbers from 
