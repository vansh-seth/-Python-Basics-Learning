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

Here's how this program works.
```
