# Python Operators

Operators are special symbols that perform operations on variables and values. Let's explore different types of Python operators.

## 1. Arithmetic Operators

Arithmetic operators perform mathematical operations like addition, subtraction, multiplication, etc.

```python
a = 7
b = 2

# addition
print('Sum: ', a + b)  

# subtraction
print('Subtraction: ', a - b)   

# multiplication
print('Multiplication: ', a * b)  

# division
print('Division: ', a / b) 

# floor division
print('Floor Division: ', a // b)

# modulo
print('Modulo: ', a % b)  

# a to the power b
print('Power: ', a ** b)   
```

**Output:**
```
Sum: 9
Subtraction: 5
Multiplication: 14
Division: 3.5
Floor Division: 3
Modulo: 1
Power: 49
```

## 2. Assignment Operators

Assignment operators are used to assign values to variables.

```python
# assign 10 to a
a = 10

# assign 5 to b
b = 5 

# assign the sum of a and b to a
a += b      # a = a + b

print(a)
```

**Output:**
```
15
```

## 3. Comparison Operators

Comparison operators compare two values/variables and return a boolean result (True or False).

```python
a = 5
b = 2

# equal to operator
print('a == b =', a == b)

# not equal to operator
print('a != b =', a != b)

# greater than operator
print('a > b =', a > b)

# less than operator
print('a < b =', a < b)

# greater than or equal to operator
print('a >= b =', a >= b)

# less than or equal to operator
print('a <= b =', a <= b)
```

**Output:**
```
a == b = False
a != b = True
a > b = True
a < b = False
a >= b = True
a <= b = False
```

## 4. Logical Operators

Logical operators are used to check whether an expression is True or False.

```python
# logical AND
print(True and True)     # True
print(True and False)    # False

# logical OR
print(True or False)     # True

# logical NOT
print(not True)          # False
```

## 5. Bitwise Operators

Bitwise operators operate on operands as if they were strings of binary digits.

```python
x = 10
y = 4

# Bitwise AND
print(x & y)    # 0

# Bitwise OR
print(x | y)    # 14

# Bitwise NOT
print(~x)       # -11

# Bitwise XOR
print(x ^ y)    # 14

# Bitwise right shift
print(x >> 2)   # 2

# Bitwise left shift
print(x << 2)   # 40
```

## 6. Special Operators

### Identity operators

```python
x1 = 5
y1 = 5
x2 = 'Hello'
y2 = 'Hello'
x3 = [1, 2, 3]
y3 = [1, 2, 3]

print(x1 is not y1)  # False
print(x2 is y2)      # True
print(x3 is y3)      # False
```

### Membership operators

```python
x = 'Hello world'
y = {1: 'a', 2: 'b'}

print('H' in x)       # True
print('hello' not in x)  # True
print(1 in y)        # True
print('a' in y)      # False
```

These operators play a crucial role in various aspects of Python programming.
