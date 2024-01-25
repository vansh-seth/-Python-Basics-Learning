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


## Python Function Arguments

In computer programming, an argument is a value that is accepted by a function.

## Example 1: Python Function Arguments

```python
def add_numbers(a, b):
    sum = a + b
    print('Sum:', sum)

add_numbers(2, 3)
```

Output:
```
Sum: 5
```

In the above example, the function `add_numbers()` takes two parameters: `a` and `b`. Notice the line,

```python
add_numbers(2, 3)
```

Here, `add_numbers(2, 3)` specifies that parameters `a` and `b` will get values 2 and 3 respectively.

## Function Argument with Default Values

In Python, we can provide default values to function arguments.

We use the `=` operator to provide default values. For example,

```python
def add_numbers(a=7, b=8):
    sum = a + b
    print('Sum:', sum)

# function call with two arguments
add_numbers(2, 3)

# function call with one argument
add_numbers(a=2)

# function call with no arguments
add_numbers()
```

Output:

```
Sum: 5
Sum: 10
Sum: 15
```

In the above example, notice the function definition

```python
def add_numbers(a=7, b=8):
    ...
```

Here, we have provided default values 7 and 8 for parameters `a` and `b` respectively.

1. `add_number(2, 3)`: Both values are passed during the function call. Hence, these values are used instead of the default values.

2. `add_number(2)`: Only one value is passed during the function call. So, according to the positional argument, 2 is assigned to argument `a`, and the default value is used for parameter `b`.

3. `add_number()`: No value is passed during the function call. Hence, the default value is used for both parameters `a` and `b`.

## Python Keyword Argument

In keyword arguments, arguments are assigned based on the name of arguments. For example,

```python
def display_info(first_name, last_name):
    print('First Name:', first_name)
    print('Last Name:', last_name)

display_info(last_name='Cartman', first_name='Eric')
```

Output:

```
First Name: Eric
Last Name: Cartman
```

Here, notice the function call,

```python
display_info(last_name='Cartman', first_name='Eric')
```

Here, we have assigned names to arguments during the function call.

Hence, `first_name` in the function call is assigned to `first_name` in the function definition. Similarly, `last_name` in the function call is assigned to `last_name` in the function definition.

In such scenarios, the position of arguments doesn't matter.

## Python Function With Arbitrary Arguments

Sometimes, we do not know in advance the number of arguments that will be passed into a function. To handle this kind of situation, we can use arbitrary arguments in Python.

Arbitrary arguments allow us to pass a varying number of values during a function call.

We use an asterisk (`*`) before the parameter name to denote this kind of argument. For example,

```python
# program to find the sum of multiple numbers 

def find_sum(*numbers):
    result = 0
    
    for num in numbers:
        result += num
    
    print("Sum =", result)

# function call with 3 arguments
find_sum(1, 2, 3)

# function call with 2 arguments
find_sum(4, 9)
```

Output:

```
Sum = 6
Sum = 13
```

In the above example, we have created the function `find_sum()` that accepts arbitrary arguments. Notice the lines,

```python
find_sum(1, 2, 3)

find_sum(4, 9)
```

Here, we are able to call the same function with different arguments.

**Note:** After getting multiple values, `numbers` behave as an array so we are able to use the for loop to access each value.


## Python Recursion

Recursion is the process of defining something in terms of itself.

A physical world example would be to place two parallel mirrors facing each other. Any object in between them would be reflected recursively.

## Python Recursive Function

In Python, we know that a function can call other functions. It is even possible for the function to call itself. These types of construct are termed as recursive functions.

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/0bfc1c5e-34d3-4165-8b18-eeb627ec6779)

Following is an example of a recursive function to find the factorial of an integer.

Factorial of a number is the product of all the integers from 1 to that number. For example, the factorial of 6 (denoted as 6!) is 1*2*3*4*5*6 = 720.

### Example of a recursive function

```python
def factorial(x):
    """This is a recursive function
    to find the factorial of an integer"""

    if x == 1:
        return 1
    else:
        return (x * factorial(x-1))


num = 3
print("The factorial of", num, "is", factorial(num))
```

**Output:**

```
The factorial of 3 is 6
```

In the above example, `factorial()` is a recursive function as it calls itself.

When we call this function with a positive integer, it will recursively call itself by decreasing the number.

Each function multiplies the number with the factorial of the number below it until it is equal to one. This recursive call can be explained in the following steps.

1. `factorial(3)`          # 1st call with 3
2. `3 * factorial(2)`      # 2nd call with 2
3. `3 * 2 * factorial(1)`  # 3rd call with 1
4. `3 * 2 * 1`             # return from 3rd call as number=1
5. `3 * 2`                 # return from 2nd call
6. `6`                     # return from 1st call

Let's look at an image that shows a step-by-step process of what is going on:

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/6293aa28-e7d0-4f8b-8372-3c6c288731c4)

Our recursion ends when the number reduces to 1. This is called the base condition.

Every recursive function must have a base condition that stops the recursion or else the function calls itself infinitely.

The Python interpreter limits the depths of recursion to help avoid infinite recursions, resulting in stack overflows.

By default, the maximum depth of recursion is 1000. If the limit is crossed, it results in RecursionError. Let's look at one such condition.

```python
def recursor():
    recursor()
recursor()
```

**Output:**

```
Traceback (most recent call last):
  File "<string>", line 3, in <module>
  File "<string>", line 2, in a
  File "<string>", line 2, in a
  File "<string>", line 2, in a
  [Previous line repeated 996 more times]
RecursionError: maximum recursion depth exceeded
```

### Advantages of Recursion

- Recursive functions make the code look clean and elegant.
- A complex task can be broken down into simpler sub-problems using recursion.
- Sequence generation is easier with recursion than using some nested iteration.

### Disadvantages of Recursion

- Sometimes the logic behind recursion is hard to follow through.
- Recursive calls are expensive (inefficient) as they take up a lot of memory and time.
- Recursive functions are hard to debug.


## Python Lambda/Anonymous Function

In Python, a lambda function is a special type of function without the function name. For example,

```python
lambda: print('Hello World')
```

Here, we have created a lambda function that prints 'Hello World'.

## Python lambda Function Declaration

We use the `lambda` keyword instead of `def` to create a lambda function. Here's the syntax to declare the lambda function:

```python
lambda argument(s): expression
```

Here,

- `argument(s)` - any value passed to the lambda function
- `expression` - expression is executed and returned

Let's see an example,

```python
greet = lambda: print('Hello World')
```

Here, we have defined a lambda function and assigned it to the variable named `greet`.

To execute this lambda function, we need to call it. Here's how we can call the lambda function:

```python
# call the lambda
greet()
```

The lambda function above simply prints the text 'Hello World'.

**Note**: This lambda function doesn't have any arguments.

### Example: Python lambda Function

```python
# declare a lambda function
greet = lambda: print('Hello World')

# call lambda function
greet()

# Output: Hello World
```

In the above example, we have defined a lambda function and assigned it to the `greet` variable.

When we call the lambda function, the `print()` statement inside the lambda function is executed.

## Python lambda Function with an Argument

Similar to normal functions, the lambda function can also accept arguments. For example,

```python
# lambda that accepts one argument
greet_user = lambda name: print('Hey there,', name)

# lambda call
greet_user('Delilah')

# Output: Hey there, Delilah
```

In the above example, we have assigned a lambda function to the `greet_user` variable.

Here, `name` after the `lambda` keyword specifies that the lambda function accepts the argument named `name`.

Notice the call of lambda function,

```python
greet_user('Delilah')
```

Here, we have passed a string value `'Delilah'` to our lambda function.

And finally, the statement inside the lambda function is executed.


You can include the following content in your `README.md` file to explain Python variable scopes:


## Python Variable Scope

In Python, we can declare variables in three different scopes: local scope, global scope, and nonlocal scope.

A variable scope specifies the region where we can access a variable.

## Local Variables

When we declare variables inside a function, these variables will have a local scope (within the function). We cannot access them outside the function. These types of variables are called local variables.

For example,

```python
def greet():
    # local variable
    message = 'Hello'
    
    print('Local', message)

greet()

# try to access message variable 
# outside greet() function
print(message)  # This will raise a NameError
```

Here, the `message` variable is local to the `greet()` function, so it can only be accessed within the function. That's why we get an error when we try to access it outside the `greet()` function.

## Global Variables

In Python, a variable declared outside of the function or in global scope is known as a global variable. This means that a global variable can be accessed inside or outside of the function.

For example,

```python
# declare global variable
message = 'Hello'

def greet():
    # accessing global variable
    print('Local', message)

greet()
print('Global', message)
```

This time we can access the `message` variable from outside of the `greet()` function. This is because we have created the `message` variable as a global variable.

## Nonlocal Variables

In Python, nonlocal variables are used in nested functions whose local scope is not defined. This means that the variable can be neither in the local nor the global scope. We use the `nonlocal` keyword to create nonlocal variables.

For example,

```python
def outer():
    message = 'local'

    def inner():
        nonlocal message
        message = 'nonlocal'
        print("inner:", message)

    inner()
    print("outer:", message)

outer()
```

In the above example, there is a nested `inner()` function. We have used the `nonlocal` keyword to create a nonlocal variable. The `inner()` function is defined in the scope of another function `outer()`.

Note: If we change the value of a nonlocal variable, the changes appear in the local variable.
