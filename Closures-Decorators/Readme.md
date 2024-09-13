# Python Closures
Python closure is a nested function that allows us to access variables of the outer function even after the outer function is closed.
### Nested function in Python

In Python, we can create a function inside another function. This is known as a nested function. For example,

```python
def greet(name):
    # inner function
    def display_name():
        print("Hi", name)
    
    # call inner function
    display_name()

# call outer function
greet("John")  

# Output: Hi John
```

In the above example, we have defined the `display_name()` function inside the `greet()` function.

Here, `display_name()` is a nested function. The nested function works similar to the normal function. It executes when `display_name()` is called inside the function `greet()`.

### Python Closures

As we have already discussed, closure is a nested function that helps us access the outer function's variables even after the outer function is closed. For example,

```python
def greet():
    # variable defined outside the inner function
    name = "John"
    
    # return a nested anonymous function
    return lambda: "Hi " + name

# call the outer function
message = greet()

# call the inner function
print(message())

# Output: Hi John
```

In the above example, we have created a function named `greet()` that returns a nested anonymous function.

Here, when we call the outer function,

```python
message = greet()
```

The returned function is now assigned to the `message` variable.

At this point, the execution of the outer function is completed, so the `name` variable should be destroyed. However, when we call the anonymous function using

```python
print(message())
```

we are able to access the `name` variable of the outer function.

It's possible because the nested function now acts as a closure that closes the outer scope variable within its scope even after the outer function is executed.

### Example: Print Odd Numbers using Python Closure

```python
def calculate():
    num = 1
    def inner_func():
        nonlocal num
        num += 2
        return num
    return inner_func

# call the outer function
odd = calculate()

# call the inner function
print(odd())
print(odd())
print(odd())

# call the outer function again
odd2 = calculate()
print(odd2())
```

Output:

```
3
5
7
3
```

In the above example,

```python
odd = calculate()
```

This code executes the outer function `calculate()` and returns a closure to the odd number. That's why we can access the `num` variable of `calculate()` even after completing the outer function.

Again, when we call the outer function using

```python
odd2 = calculate()
```

a new closure is returned. Hence, we get `3` again when we call `odd2()`.

### When to use closures?

Closures can be used to avoid global values and provide data hiding, and can be an elegant solution for simple cases with one or few methods.

However, for larger cases with multiple attributes and methods, a class implementation may be more appropriate.

```python
def make_multiplier_of(n):
    def multiplier(x):
        return x * n
    return multiplier

# Multiplier of 3
times3 = make_multiplier_of(3)

# Multiplier of 5
times5 = make_multiplier_of(5)

# Output: 27
print(times3(9))

# Output: 15
print(times5(3))

# Output: 30
print(times5(times3(2)))
```

Python Decorators make extensive use of closures as well.

On a concluding note, it is good to point out that the values that get enclosed in the closure function can be found out.

All function objects have a `__closure__` attribute that returns a tuple of cell objects if it is a closure function.

Referring to the example above, we know `times3` and `times5` are closure functions.

# Python Decorators

In Python, a decorator is a design pattern that allows you to modify the functionality of a function by wrapping it in another function.

The outer function is called the decorator, which takes the original function as an argument and returns a modified version of it.

### Prerequisites for learning decorators

Before we learn about decorators, we need to understand a few important concepts related to Python functions. Also, remember that everything in Python is an object, even functions are objects.

#### Nested Function

We can include one function inside another, known as a nested function. For example,

```python
def outer(x):
    def inner(y):
        return x + y
    return inner

add_five = outer(5)
result = add_five(6)
print(result)  # prints 11
```

#### Pass Function as Argument

We can pass a function as an argument to another function in Python. For example,

```python
def add(x, y):
    return x + y

def calculate(func, x, y):
    return func(x, y)

result = calculate(add, 4, 6)
print(result)  # prints 10
```

#### Return a Function as a Value

In Python, we can also return a function as a return value. For example,

```python
def greeting(name):
    def hello():
        return "Hello, " + name + "!"
    return hello

greet = greeting("Atlantis")
print(greet())  # prints "Hello, Atlantis!"
```

### Python Decorators

As mentioned earlier, A Python decorator is a function that takes in a function and returns it by adding some functionality.

In fact, any object which implements the special `__call__()` method is termed callable. So, in the most basic sense, a decorator is a callable that returns a callable.

Basically, a decorator takes in a function, adds some functionality, and returns it.

```python
def make_pretty(func):
    def inner():
        print("I got decorated")
        func()
    return inner

def ordinary():
    print("I am ordinary")
```

Here, we have created two functions:

- `ordinary()` that prints "I am ordinary"
- `make_pretty()` that takes a function as its argument and has a nested function named `inner()`, and returns the `inner` function.

We are calling the `ordinary()` function normally, so we get the output "I am ordinary". Now, let's call it using the decorator function.

```python
def make_pretty(func):
    def inner():
        print("I got decorated")
        func()
    return inner

def ordinary():
    print("I am ordinary")
    
# decorate the ordinary function
decorated_func = make_pretty(ordinary)

# call the decorated function
decorated_func()
```

Output:

```
I got decorated
I am ordinary
```

In the example shown above, `make_pretty()` is a decorator. Notice the code,

```python
decorated_func = make_pretty(ordinary)
```

We are now passing the `ordinary()` function as the argument to the `make_pretty()`. The `make_pretty()` function returns the `inner()` function, and it is now assigned to the `decorated_func` variable.

```python
decorated_func()
```

Here, we are actually calling the `inner()` function, where we are printing.

### @ Symbol With Decorator

Instead of assigning the function call to a variable, Python provides a much more elegant way to achieve this functionality using the `@` symbol. For example,

```python
def make_pretty(func):
    def inner():
        print("I got decorated")
        func()
    return inner

@make_pretty
def ordinary():
    print("I am ordinary")

ordinary()  
```

Output:

```
I got decorated
I am ordinary
```

Here, the `ordinary()` function is decorated with the `make_pretty()` decorator using the `@make_pretty` syntax, which is equivalent to calling `ordinary = make_pretty(ordinary)`.

### Decorating Functions with Parameters

The above decorator was simple and it only worked with functions that did not have any parameters. What if we had functions that took in parameters like:

```python
def divide(a, b):
    return a/b
```

This function has two parameters, `a` and `b`. We know it will give an error if we pass in `b` as `0`.

Now let's make a decorator to check for this case that will cause the error.

```python
def smart_divide(func):
    def inner(a, b):
        print("I am going to divide", a, "and", b)
        if b == 0:
            print("Whoops! cannot divide")
            return

        return func(a, b)
    return inner

@smart_divide
def divide(a, b):
    print(a/b)

divide(2,5)

divide(2,0)
```

Output:

```
I am going to divide 2 and 5
0.4
I am going to divide 2 and 0
Whoops! cannot divide
```

Here, when we call the `divide()` function with the arguments `(2,5)`, the `inner()` function defined in the `smart_divide()` decorator is called instead.

This `inner()` function calls the original `divide()` function with the arguments `2` and `5` and returns the result, which is `0.4`.

Similarly, When we call the `divide()` function with the arguments `(2,0)`, the `inner()` function checks that `b` is equal to `0` and prints an error message before returning `None`.

### Chaining Decorators in Python

Multiple decorators can be chained in Python.

To chain decorators in Python, we can apply multiple decorators to a single function by placing them one after the other, with the most inner decorator being applied first.

```python
def star(func):
    def inner(*args, **kwargs):
        print("*" * 15)
        func(*args, **kwargs)
        print("*" * 15)
    return inner

def percent(func):
    def inner(*args, **kwargs):
        print("%" * 15)
        func(*args, **kwargs)
        print("%" * 15)
    return inner

@star
@percent
def printer(msg):
    print(msg)

printer("Hello")
```

Output:

```
***************
%%%%%%%%%%%%%%%
Hello
%%%%%%%%%%%%%%%
***************
```

The above syntax of,

```python
@star
@percent
def printer(msg):
    print(msg)
```

is equivalent to

```python
def printer(msg):
    print(msg)
printer = star(percent(printer))
```

The order in which we chain decorators matter. If we had reversed the order as,

```python
@percent
@star
def printer(msg):
    print(msg)
```

The output would be:

```
%%%%%%%%%%%%%%%
***************
Hello
***************
%%%%%%%%%%%%%%%
```

