# Python if...else Statement

In computer programming, the if statement is a conditional statement. It is used to execute a block of code only when a specific condition is met. For example, suppose we need to assign different grades to students based on their scores.

If a student scores above 90, assign grade A If a student scores above 75, assign grade B If a student scores above 65, assign grade C

These conditional tasks can be achieved using the if statement.

## Python if Statement

An if statement executes a block of code only if the specified condition is met.

### Syntax

```python
if condition:
    # body of if statement
```

Here, if the condition of the if statement is:

- True: the body of the if statement executes.
- False: the body of the if statement is skipped from execution.

Let's look at an example.

```python
number = 10

# check if number is greater than 0
if number > 0:
    print('Number is positive')

print('This statement always executes')
```

**Output:**

```
Number is positive
This statement always executes
```

In the above example, we have created a variable named `number`. Notice the test condition, `number > 0`. As the number is greater than 0, the condition evaluates True. Hence, the body of the if statement executes.

Now, let's change the value of the number to a negative integer, say -5.

```python
number = -5
```

Now, when we run the program, the output will be:

```
This statement always executes
```

This is because the value of the number is less than 0. Hence, the condition evaluates to False. And, the body of the if statement is skipped.

## Python if...else Statement

An if statement can have an optional else clause. The else statement executes if the condition in the if statement evaluates to False.

### Syntax

```python
if condition:
    # body of if statement
else:
    # body of else statement
```

Here, if the condition inside the if statement evaluates to:

- True: the body of if executes, and the body of else is skipped.
- False: the body of else executes, and the body of if is skipped.

Let's look at an example.

```python
number = 10

if number > 0:
    print('Positive number')
else:
    print('Negative number')

print('This statement always executes')
```

**Output:**

```
Positive number
This statement always executes
```

In the above example, we have created a variable named `number`. Since the value of the number is 10, the condition evaluates to True. Hence, the code inside the body of if is executed.

If we change the value of the variable to a negative integer, let's say -5, our output will be:

```
Negative number
This statement always executes
```

Here, the test condition evaluates to False. Hence the code inside the body of else is executed.

## Python if...elif...else Statement

The if...else statement is used to execute a block of code among two alternatives. However, if we need to make a choice between more than two alternatives, we use the if...elif...else statement.

### Syntax

```python
if condition1:
    # code block 1
elif condition2:
    # code block 2
else:
    # code block 3
```

Here,

- if condition1: This checks if condition1 is True. If it is, the program executes code block 1.
- elif condition2: If condition1 is not True, the program checks condition2. If condition2 is True, it executes code block 2.
- else: If neither condition1 nor condition2 is True, the program defaults to executing code block 3.

Let's look at an example.

```python
number = 0

if number > 0:
    print("Positive number")
elif number < 0:
    print('Negative number')
else:
    print('Zero')

print('This statement is always executed')
```

**Output:**

```
Zero
This statement is always executed
```

In the above example, we have created a variable named `number`. Since the value of the number is 0, both the test conditions evaluate to False. Hence, the statement inside the body of else is executed.

## Python Nested if Statements

It is possible to include an if statement inside another if statement. For example,

```python
number = 5

# outer if statement
if number >= 0:
    # inner if statement
    if number == 0:
      print('Number is 0')
    # inner else statement
    else:
        print('Number is positive')

# outer else statement
else:
    print('Number is negative')
```

**Output:**

```
Number is positive
```

# Python for Loop

In computer programming, loops are used to repeat a block of code.

```python
languages = ['Swift', 'Python', 'Go']

# access items of a list using for loop
for i in languages:
    print(i)
```

**Output:**

```
Swift
Python
Go
```

In the above example, we have created a list called `languages`. As the list has 3 elements, the loop iterates 3 times.

The value of `i` is:

- `Swift` in the first iteration.
- `Python` in the second iteration.
- `Go` in the third iteration.

## for loop Syntax

The syntax of a for loop is:

```python
for val in sequence:
    # statement(s)
```

Here, `val` accesses each item of the sequence on each iteration. The loop continues until we reach the last item in the sequence.

## Flowchart of Python for Loop

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/fa51fbc4-e9b7-47ed-addc-f722ab5a854f)

## Example: Loop Through a String

```python
language = 'Python'

# iterate over each character in language
for x in language:
    print(x)
```

**Output:**

```
P
y
t
h
o
n
```

Here, we have printed each character of the string `language` using a for loop.

## for Loop with Python `range()`

In Python, the `range()` function returns a sequence of numbers. For example,

```python
values = range(4)
```

Here, `range(4)` returns a sequence of 0, 1, 2, and 3.

We can use `range()` with a for loop to iterate a certain number of times. For example,

```python
# iterate from i = 0 to i = 3
for i in range(4):
    print(i)
```

**Output:**

```
0
1
2
3
```

Here, we used the for loop to iterate over a range from 0 to 3.

This is how the above program works:

| Iteration | Value of i | print(i) | Last item in sequence? |
|-----------|------------|-----------|-------------------------|
| 1st       | 0          | Prints 0  | No                      |
| 2nd       | 1          | Prints 1  | No                      |
| 3rd       | 2          | Prints 2  | No                      |
| 4th       | 3          | Prints 3  | Yes                     |
| The loop terminates. |


# Python while Loop

In Python, we use the while loop to repeat a block of code until a certain condition is met. For example,

```python
number = 1

while number <= 3:
    print(number)
    number = number + 1
```

**Output:**

```
1
2
3
```

In the above example, we have used a while loop to print the numbers till the condition `number <= 3` is satisfied.

## while Loop Syntax

```python
while condition:
    # body of while loop
```

Here,

- The while loop evaluates the condition.
- If the condition is true, body of while loop is executed. The condition is evaluated again.
- This process continues until the condition is False.
- Once the condition evaluates to False, the loop terminates.

## Flowchart of Python while Loop

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/fac6c8ae-7920-4ac4-bab5-1000506b3de8)

## Example: Python while Loop

```python
# calculate the sum of five numbers entered by user
sum = 0
count = 0

while count < 5:
    input_value = int(input('Enter a number: '))
    sum += input_value
    count += 1

print('The sum is:', sum)
```

**Output:**

```
Enter a number: 3
Enter a number: 2
Enter a number: 1
Enter a number: 4
Enter a number: 6
The sum is: 16
```

Here is how the above program works in each iteration of the loop:

| Variables | count < 5 | sum = sum + user_input |
|-----------|-----------|-------------------------|
| count = 0 | True      | sum = 0 + 3 = 3         |
| count = 1 | True      | sum = 3 + 2 = 5         |
| count = 2 | True      | sum = 5 + 1 = 6         |
| count = 3 | True      | sum = 6 + 4 = 10        |
| count = 4 | True      | sum = 10 + 6 = 16       |
| count = 5 | False     | The loop is terminated. |

## Example: while Loop to Display Game Level

```python
# variables to store game information
current_level = 1
final_level = 4
game_completed = True

# iterate until the final level is reached
while current_level <= final_level:
    if game_completed:
        print(f'Welcome to Level {current_level}')
        current_level += 1

print('Game Over!')
```

**Output:**

```
Welcome to Level 1
Welcome to Level 2
Welcome to Level 3
Welcome to Level 4
Game Over!
```

In the above example, we have used a while loop to check the current level of the player and display it.


## Infinite while Loop

If the condition of a while loop is always True, the loop runs for infinite times, forming an infinite while loop. For example,

```python
age = 32

# the test condition is always True
while age > 18:
    print('You can vote')
```

**Output:**

```
You can vote
You can vote
You can vote
.
.
.
```

# Python break and continue

In programming, the `break` and `continue` statements are used to alter the flow of loops:

- `break` exits the loop entirely.
- `continue` skips the current iteration and proceeds to the next one.

## Python `break` Statement

The `break` statement terminates the loop immediately when it's encountered.

### Syntax

```python
break
```

### Working of Python `break` Statement

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/0059d833-ea5f-4376-9be6-a4b652ad57bb)

The above image shows the working of break statements in for and while loops.

**Note:** The `break` statement is usually used inside decision-making statements such as if...else.

### Example: `break` Statement with `for` Loop

We can use the `break` statement with the `for` loop to terminate the loop when a certain condition is met. For example,

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

**Output:**

```
0
1
2
```

In the above example, `if i == 3:` `break` terminates the loop when `i` is equal to 3. Hence, the output doesn't include values after 2.

**Note:** We can also terminate the `while` loop using a `break` statement.

## Python `continue` Statement

The `continue` statement skips the current iteration of the loop, and the control flow of the program goes to the next iteration.

### Syntax

```python
continue
```

### Working of `continue` Statement in Python

![image](https://github.com/vansh-seth/-Python-Basics-Learning/assets/111755254/c93dc1fa-c7e9-46f9-a8d7-6b201d47422c)

### Example: `continue` Statement with `for` Loop

We can use the `continue` statement with the `for` loop to skip the current iteration of the loop and jump to the next iteration. For example,

```python
for i in range(5):
    if i == 3:
        continue
    print(i)
```

**Output:**

```
0
1
2
4
```

In the above example, `if i == 3:` `continue` skips the current iteration when `i` is equal to 3 and continues the next iteration. Hence, the output has all the values except 3.

**Note:** We can also use the `continue` statement with a `while` loop.

# Python `pass` Statement

In Python programming, the `pass` statement is a null statement which can be used as a placeholder for future code.

Suppose we have a loop or a function that is not implemented yet, but we want to implement it in the future. In such cases, we can use the `pass` statement.

## Syntax

```python
pass
```

## Using `pass` With Conditional Statement

```python
n = 10

# use pass inside if statement
if n > 10:
    pass

print('Hello')
```

Here, notice that we have used the `pass` statement inside the `if` statement.

However, nothing happens when the `pass` is executed. It results in no operation (NOP).

Suppose we didn't use `pass` or just put a comment as:

```python
n = 10

if n > 10:
    # write code later

print('Hello')
```

Here, we will get an error message: `IndentationError: expected an indented block`.

**Note:** The difference between a comment and a `pass` statement in Python is that while the interpreter ignores a comment entirely, `pass` is not ignored.

## Use of `pass` Statement inside Function or Class

We can do the same thing in an empty function or class as well. For example,

```python
def function(args):
    pass

class Example:
    pass
```
