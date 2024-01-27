# Python Iterators
Iterators are methods that iterate collections like lists, tuples, etc. Using an iterator method, we can loop through an object and return its elements.

Technically, a Python iterator object must implement two special methods, `__iter__()` and `__next__()`, collectively called the iterator protocol.

### Iterating Through an Iterator

In Python, we can use the `next()` function to return the next item in the sequence.

Let's see an example,

```python
# define a list
my_list = [4, 7, 0]

# create an iterator from the list
iterator = iter(my_list)

# get the first element of the iterator
print(next(iterator))  # prints 4

# get the second element of the iterator
print(next(iterator))  # prints 7

# get the third element of the iterator
print(next(iterator))  # prints 0
```

Output:

```
4
7
0
```

Here, first we created an iterator from the list using the `iter()` method. And then used the `next()` function to retrieve the elements of the iterator in sequential order.

When we reach the end and there is no more data to be returned, we will get the `StopIteration` Exception.

### Using for Loop

A more elegant way of automatically iterating is by using the `for` loop. For example,

```python
# define a list
my_list = [4, 7, 0]

for element in my_list:
    print(element)
```

Output:

```
4
7
0
```

### Working of for loop for Iterators

The `for` loop in Python is used to iterate over a sequence of elements, such as a list, tuple, or string.

When we use the `for` loop with an iterator, the loop will automatically iterate over the elements of the iterator until it is exhausted.

Here's an example of how a `for` loop works with an iterator,

```python
# create a list of integers
my_list = [1, 2, 3, 4, 5]

# create an iterator from the list
iterator = iter(my_list)

# iterate through the elements of the iterator
for element in iterator:

    # Print each element
    print(element)
```

In this example, the `for` loop iterates over the elements of the iterator object.

On each iteration, the loop assigns the value of the next element to the variable `element`, and then executes the indented code block.

This process continues until the iterator is exhausted, at which point the `for` loop terminates.

### Building Custom Iterators

Building an iterator from scratch is easy in Python. We just have to implement the `__iter__()` and the `__next__()` methods,

`__iter__()` returns the iterator object itself. If required, some initialization can be performed.
`__next__()` must return the next item in the sequence. On reaching the end, and in subsequent calls, it must raise `StopIteration`.
Let's see an example that will give us the next power of 2 in each iteration. Power exponent starts from zero up to a user set number,

```python
class PowTwo:
    """Class to implement an iterator
    of powers of two"""

    def __init__(self, max=0):
        self.max = max

    def __iter__(self):
        self.n = 0
        return self

    def __next__(self):
        if self.n <= self.max:
            result = 2 ** self.n
            self.n += 1
            return result
        else:
            raise StopIteration


# create an object
numbers = PowTwo(3)

# create an iterable from the object
i = iter(numbers)

# Using next to get to the next iterator element
print(next(i)) # prints 1
print(next(i)) # prints 2
print(next(i)) # prints 4
print(next(i)) # prints 8
print(next(i)) # raises StopIteration exception
```

Output:

```
1
2
4
8
Traceback (most recent call last):
  File "<string>", line 32, in <module>
File "<string>", line 18, in __next__
StopIteration
```

We can also use a `for` loop to iterate over our iterator class.

```python
for i in PowTwo(3):
    print(i)
```

Output:

```
1
2
4
8
```

### Python Infinite Iterators

An infinite iterator is an iterator that never ends, meaning that it will continue to produce elements indefinitely.

Here is an example of how to create an infinite iterator in Python using the `count()` function from the `itertools` module,

```python
from itertools import count

# create an infinite iterator that starts at 1 and increments by 1 each time
infinite_iterator = count(1)

# print the first 5 elements of the infinite iterator
for i in range(5):
    print(next(infinite_iterator))
```

Output:

```
1
2
3
4
5
```

Here, we have created an infinite iterator that starts at 1 and increments by 1 each time.

And then we printed the first 5 elements of the infinite iterator using the `for` loop and the `next()` method.

# Python Generators
In Python, a generator is a function that returns an iterator that produces a sequence of values when iterated over.

Generators are useful when we want to produce a large sequence of values, but we don't want to store all of them in memory at once.

### Create Python Generator

In Python, similar to defining a normal function, we can define a generator function using the `def` keyword, but instead of the `return` statement, we use the `yield` statement.

```python
def generator_name(arg):
    # statements
    yield something
```

Here, the `yield` keyword is used to produce a value from the generator.

When the generator function is called, it does not execute the function body immediately. Instead, it returns a generator object that can be iterated over to produce the values.

### Example: Python Generator

Here's an example of a generator function that produces a sequence of numbers,

```python
def my_generator(n):
    # initialize counter
    value = 0
    # loop until counter is less than n
    while value < n:
        # produce the current value of the counter
        yield value
        # increment the counter
        value += 1

# iterate over the generator object produced by my_generator
for value in my_generator(3):
    # print each value produced by generator
    print(value)
```

Output:

```
0
1
2
```

In the above example, the `my_generator()` generator function takes an integer `n` as an argument and produces a sequence of numbers from 0 to `n-1`.

The `yield` keyword is used to produce a value from the generator and pause the generator function's execution until the next value is requested.

We can also create a generator object from the generator function by calling the function like we would any other function as,

```python
generator = my_range(3)
print(next(generator))  # 0
print(next(generator))  # 1
print(next(generator))  # 2
```

### Python Generator Expression

In Python, a generator expression is a concise way to create a generator object.

It is similar to a list comprehension, but instead of creating a list, it creates a generator object that can be iterated over to produce the values in the generator.

#### Generator Expression Syntax

A generator expression has the following syntax,

```
(expression for item in iterable)
```

Here, `expression` is a value that will be returned for each item in the iterable.

The generator expression creates a generator object that produces the values of `expression` for each item in the iterable, one at a time, when iterated over.

#### Example 2: Python Generator Expression

```python
# create the generator object
squares_generator = (i * i for i in range(5))

# iterate over the generator and print the values
for i in squares_generator:
    print(i)
```

Output:

```
0
1
4
9
16
```

Here, we have created the generator object that will produce the squares of the numbers 0 through 4 when iterated over.

And then, to iterate over the generator and get the values, we have used the `for` loop.

### Use of Python Generators

There are several reasons that make generators a powerful implementation.

1. **Easy to Implement**: Generators can be implemented in a clear and concise way as compared to their iterator class counterpart. 

2. **Memory Efficient**: A normal function to return a sequence will create the entire sequence in memory before returning the result. Generator implementation of such sequences is memory-friendly and is preferred since it only produces one item at a time.

3. **Represent Infinite Stream**: Generators are excellent mediums to represent an infinite stream of data. 

4. **Pipelining Generators**: Multiple generators can be used to pipeline a series of operations.

```python
# Example for pipelining generators
def fibonacci_numbers(nums):
    x, y = 0, 1
    for _ in range(nums):
        x, y = y, x+y
        yield x

def square(nums):
    for num in nums:
        yield num**2

print(sum(square(fibonacci_numbers(10))))
# Output: 4895
```

This pipelining is efficient and easy to read.
