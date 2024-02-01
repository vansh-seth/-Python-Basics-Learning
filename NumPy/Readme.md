# NumPy

NumPy, short for **Numerical Python**, is a Python library designed for data analysis and scientific computing. It offers a multidimensional array object along with functions tailored for array manipulation. Its n-dimensional arrays accelerate data processing tasks. NumPy seamlessly integrates with other Python packages and offers interfaces for integration with languages like C and C++.

## Installing NumPy

NumPy can be installed by typing the following command:

```python
pip install numpy
```

# Arrays in Programming

An array is a fundamental data structure that enables the storage of multiple values under a single variable name. Unlike other data structures like lists, tuples, or dictionaries, arrays contain elements of the same data type, arranged in a specific order. Accessing elements in an array is based on their index position.

### Key Characteristics of Arrays:

1. **Uniform Data Type:** All elements within an array must share the same data type, even though their values may vary.
2. **Contiguous Memory Storage:** Array elements are stored sequentially in memory, facilitating rapid operations on arrays.
3. **Indexed Access:** Each element in the array is uniquely identified by its index, beginning from 0. For example, in an array [165, 95, 78, 31, 180], the first element 165 is at index 0, the second element 95 is at index 1, and so forth. This indexing commences from 0 and follows zero-based indexing, similar to Python lists.

Arrays serve as a fundamental component in various programming languages due to their efficiency and ease of use. Nearly all programming languages offer support for arrays in some capacity.

### NumPy Arrays:

NumPy arrays are specifically tailored for numerical data, including lists of numbers, vectors, and matrices. The NumPy library provides a comprehensive suite of functionalities for creating, manipulating, and transforming arrays efficiently. While Python includes its own array data structure, it lacks the versatility and efficiency of NumPy arrays. Officially known as ndarray but commonly referred to as arrays, NumPy arrays surpass Python arrays in functionality and utility.

## Difference Between List and Array:

### List:
- Lists can accommodate elements of different data types, such as integers, floats, strings, and more, within a single list.
- Elements within a list are not stored contiguously in memory, which can impact the speed of operations on lists.
- Lists lack native support for element-wise operations like addition or multiplication due to the potential disparity in data types among elements.
- Lists can store objects of various data types, which necessitates Python to store type information for each element, resulting in greater memory consumption and reduced efficiency.

### Array:
- Array elements are stored in contiguous memory locations, enhancing the efficiency of operations performed on arrays compared to lists.
- Arrays support element-wise operations seamlessly. For instance, operations like division or multiplication can be performed directly on array elements.
- Arrays, particularly NumPy arrays, consume less memory compared to lists since they do not need to store data type information for each element separately.
- While lists are a fundamental component of core Python, arrays (specifically ndarray) are part of the NumPy library, offering enhanced functionalities for numerical computing and data manipulation.

## Creating NumPy Arrays from Lists

To create arrays in NumPy, you first need to import the NumPy library, typically using the alias `np`. Here's how you can do it:

```python
import numpy as np
```

The `np.array()` function in NumPy is used to convert a given list into an array. For example, if you have a list `[10, 20, 30]`, you can create an array named `array1` like this:

```python
array1 = np.array([10, 20, 30])
```

When you print `array1`, you'll see:

```python
array([10, 20, 30])
```

### Creating a 1-D Array

A one-dimensional array, or 1-D array, consists of a single row of elements. To create a 1-D array from a list that contains numbers and strings, you can use the `np.array()` function. For instance:

```python
array2 = np.array([5, -7.4, 'a', 7.2])
```

Printing `array2` results in:

```python
array(['5', '-7.4', 'a', '7.2'], dtype='<U32')
```

If the list contains a string value, all integer and float values are promoted to strings during the conversion to an array. The notation `dtype='<U32'` indicates a Unicode-32 data type.

### Creating a 2-D Array

To create a two-dimensional (2-D) array, you can pass nested lists to the `np.array()` function. Here's an example:

```python
array3 = np.array([[2.4, 3], [4.91, 7], [0, -1]])
```

Printing `array3` yields:

```python
array([[ 2.4 , 3. ],
       [ 4.91, 7. ],
       [ 0. , -1. ]])
```

In the conversion process, integers like 3, 7, 0, and -1 are promoted to floats.


## Attributes of NumPy Array

Here are some important attributes of a NumPy ndarray object:

i) **ndarray.ndim**: This attribute gives the number of dimensions of the array as an integer value. Arrays can be 1-D, 2-D, or n-D. In this context, we'll focus on 1-D and 2-D arrays. NumPy refers to dimensions as axes, where a 2-D array has two axes: axis-0 (rows) and axis-1 (columns). The number of axes is also called the array's rank.

    Example:
    - `array1.ndim` outputs `1`
    - `array3.ndim` outputs `2`

ii) **ndarray.shape**: This attribute returns a sequence of integers indicating the size of the array for each dimension. For instance, a 1-D array's shape has nothing after the comma, while a 2-D array's shape is represented as (rows, columns).

    Example:
    - `array1.shape` outputs `(3,)`
    - `array2.shape` outputs `(4,)`
    - `array3.shape` outputs `(3, 2)`, meaning 3 rows and 2 columns.

iii) **ndarray.size**: It provides the total number of elements in the array, which equals the product of the elements of the shape.

    Example:
    - `array1.size` outputs `3`
    - `array3.size` outputs `6`

iv) **ndarray.dtype**: This attribute indicates the data type of the elements in the array. All elements in an array share the same data type, such as int32, int64, float32, float64, U32, etc.

    Example:
    - `array1.dtype` outputs `dtype('int32')`
    - `array2.dtype` outputs `dtype('<U32')`
    - `array3.dtype` outputs `dtype('float64')`

v) **ndarray.itemsize**: It specifies the size in bytes of each element in the array. For instance, int32 and float32 types allocate 32 bits (or 4 bytes) of memory per element, while int64 and float64 allocate 64 bits (or 8 bytes) per element.

    Example:
    - `array1.itemsize` outputs `4` (memory allocated to integer)
    - `array2.itemsize` outputs `128` (memory allocated to string)
    - `array3.itemsize` outputs `8` (memory allocated to float type)


## Creating NumPy Arrays in Different Ways

Here are various methods to create NumPy arrays:

1. **Specifying Data Type**: You can specify the data type (integer, float, etc.) while creating an array using the `dtype` argument in the `array()` function. This automatically converts the data to the specified type. For example:

    ```python
    array4 = np.array([[1, 2], [3, 4]], dtype=float)
    ```

    This creates an array:
    ```python
    array([[1., 2.],
           [3., 4.]])
    ```

2. **Creating an Array of Zeros**: You can create an array with all elements initialized to 0 using the `zeros()` function. By default, the data type of the array created by `zeros()` is float. For instance:

    ```python
    array5 = np.zeros((3, 4))
    ```

    This results in:
    ```python
    array([[0., 0., 0., 0.],
           [0., 0., 0., 0.],
           [0., 0., 0., 0.]])
    ```

3. **Creating an Array of Ones**: Similarly, you can create an array with all elements initialized to 1 using the `ones()` function. By default, the data type of the array created by `ones()` is float. For example:

    ```python
    array6 = np.ones((3, 2))
    ```

    This yields:
    ```python
    array([[1., 1.],
           [1., 1.],
           [1., 1.]])
    ```

4. **Creating an Array with a Given Range**: You can create an array with numbers in a given range and sequence using the `arange()` function, which is similar to Python's `range()` function.

    Example:
    ```python
    array7 = np.arange(6)
    ```

    This creates an array of 6 elements starting from 0 with a step size of 1:
    ```python
    array([0, 1, 2, 3, 4, 5])
    ```

    Additionally, you can specify the start value, end value, and step size to create arrays with custom sequences.

    Example:
    ```python
    array8 = np.arange(-2, 24, 4)
    ```

    This creates an array with start value -2, end value 24, and step size 4:
    ```python
    array([-2,  2,  6, 10, 14, 18, 22])
    ```

## Indexing and Slicing

NumPy arrays are versatile structures that support indexing, slicing, and iteration, offering flexibility in accessing and manipulating array elements.

### Indexing

In 2-D arrays, indexing starts from 0 for both dimensions. Each element is referenced using two indexes: `i` for the row number and `j` for the column number.

Consider a table displaying student marks in three subjects:

| Name   | Maths | English | Science |
|--------|-------|---------|---------|
| Vansh  | 97    | 87      | 56      |
| Saksham| 99    | 90      | 98      |
| Adarsh | 84    | 59      | 40      |
| Aastha | 87    | 72      | 74      |

Let's create an array named `marks` to store the marks for these subjects. As there are 4 students (rows) and 3 subjects (columns), the array will be `marks[4][3]`.

Here, `marks[i, j]` denotes the element at (i+1)th row and (j+1)th column. For instance, `marks[3, 1]` refers to Aasths's marks in English, which is 72.

### Slicing

Slicing enables extracting portions of an array by specifying start and end index values using `[start : end]` along with the array name.

For example:

```python
array8 = np.array([5, 7, 45, 10, 14, 79, 56])
array8[3:5]   # returns array([10, 14])
array8[::-1]  # returns array([56, 79, 14, 10, 45, 7, 5])
```

Let's observe how slicing works for a 2-D array `array9` with 3 rows and 4 columns:

```python
array9 = np.array([[-1, 0, 11, 45],
                   [-8, 15, 47, 560],
                   [-5, 17, 45, 70]])
```

To retrieve all elements in the 3rd column:

```python
array9[0:3, 2]  # returns array([11, 47, 45])
```

If row indices are unspecified, all rows are considered. Similarly, if column indices are unspecified, all columns are considered. Therefore, accessing all elements in the 3rd column can also be written as:

```python
array9[:, 2]  # returns array([11, 47, 45])
```

## Operations on Arrays

### Arithmetic Operations
Arithmetic operations on NumPy arrays are efficient and straightforward. When performing basic arithmetic operations such as addition, subtraction, multiplication, and division on two arrays, the operations are executed on corresponding pairs of elements. 

For example, when adding two arrays together, each element in the first array will be added to the corresponding element in the second array, and so forth. Let's consider the following element-wise operations on two arrays:

```python
import numpy as np

array1 = np.array([[9, 63], [87, 43]])
array2 = np.array([[71, 57], [40, 72]])

# Element-wise addition of two matrices
print(array1 + array2)
# Output: 
# array([[80, 120],[127, 115]])

# Subtraction
print(array1 - array2)
# Output: 
# array([[ -62, 6],[47, -29]])

# Multiplication
print(array1 * array2)
# Output: 
# array([[ 639, 3591],[ 3480,  3096]])

# Matrix Multiplication
print(array1 @ array2)
# Output: 
# array([[3159 5049],[7897 8055]])

# Exponentiation
print(array1 ** 3)
# Output: 
# array([[   729 250047], [658503  79507]], dtype=int32)

# Division
print(array2 / array1)
# Output: 
# array([[7.88888889 0.9047619 ]
 [0.45977011 1.6744186 ]])

# Element-wise Remainder of Division (Modulo)
print(array2 % array1)
# Output: 
# array([[ 8 57]
 [40 29]], dtype=int32)
```

It's essential to note that for element-wise operations, the size of both arrays must be the same, meaning that `array1.shape` must be equal to `array2.shape`. This ensures that the operations are applied correctly across corresponding elements in the arrays.


### Transpose
Transposing an array in NumPy involves converting its rows into columns and vice versa, similar to matrix operations in mathematics.

Consider the following example:

```python
import numpy as np

array3 = np.array([[10, -7, 0, 20],
                   [-5, 1, 200, 40],
                   [30, 1, -1, 4]])

# Original array
print(array3)
# Output:
# array([[ 10, -7, 0, 20],
#        [ -5, 1, 200, 40],
#        [ 30, 1, -1, 4]])

# Transposing the array does not change the original array
print(array3.transpose())
# Output:
# array([[ 10, -5, 30],
#        [ -7, 1, 1],
#        [ 0, 200, -1],
#        [ 20, 40, 4]])
```

### Sorting

Sorting in NumPy involves arranging the elements of an array in ascending or descending order. By default, NumPy performs sorting in ascending order.

Consider the following sorting examples:

```python
array4 = np.array([1, 0, 2, -3, 6, 8, 4, 7])

# Sorting in ascending order
array4.sort()
print(array4)
# Output: array([-3, 0, 1, 2, 4, 6, 7, 8])

# Sorting a 2-D array row-wise by default
array4 = np.array([[10, -7, 0, 20],
                    [-5, 1, 200, 40],
                    [30, 1, -1, 4]])

# Sorting row-wise
array4.sort()
print(array4)
# Output:
# array([[ -7,  0, 10, 20],
#        [ -5,  1, 40, 200],
#        [ -1,  1,  4, 30]])

# Sorting column-wise by specifying axis=0
array5 = np.array([[10, -7, 0, 20],
                   [-5, 1, 200, 40],
                   [30, 1, -1, 4]])

# Sorting column-wise
array5.sort(axis=0)
print(array5)
# Output:
# array([[ -5, -7, -1,  4],
#        [ 10,  1,  0, 20],
#        [ 30,  1, 200, 40]])
```

## Concatenating Arrays

Concatenating arrays in NumPy involves joining two or more arrays together. When concatenating 1-D arrays, it means appending the sequences one after another. The `numpy.concatenate()` function is used to concatenate two or more 2-D arrays either row-wise or column-wise.

It's essential to note that all dimensions of the arrays to be concatenated must match exactly, except for the dimension or axis along which they need to be joined. Any mismatch in the dimensions will result in an error. By default, the concatenation of the arrays happens along `axis=0`, meaning rows are stacked one after another.

Consider the following example:

```python
import numpy as np

array1 = np.array([[10, 20], [-30, 40]])
array2 = np.zeros((2, 3), dtype=array1.dtype)

# Displaying arrays
print(array1)
# Output:
# array([[ 10, 20],
#        [-30, 40]])

print(array2)
# Output:
# array([[0, 0, 0],
#        [0, 0, 0]])

# Checking shapes
print(array1.shape)  # (2, 2)
print(array2.shape)  # (2, 3)

# Concatenating along axis=1 (column-wise)
print(np.concatenate((array1, array2), axis=1))
# Output:
# array([[ 10, 20,  0,  0,  0],
#        [-30, 40,  0,  0,  0]])

# Attempting to concatenate along axis=0 (row-wise) with mismatched dimensions
print(np.concatenate((array1, array2)))
# Output:
# ValueError: all the input array dimensions except for the concatenation axis must match exactly
```

##  Reshaping Arrays

Reshaping arrays in NumPy involves modifying the arrangement of elements within the array using the `reshape()` function. However, it's crucial to note that reshaping an array cannot alter the total number of elements it contains. Attempting to change the number of elements using `reshape()` will result in an error.

Consider the following example:

```python
import numpy as np

array3 = np.arange(10, 22)

# Displaying the original array
print(array3)
# Output:
# array([10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21])

# Reshaping the array into a 3x4 matrix
print(array3.reshape(3, 4))
# Output:
# array([[10, 11, 12, 13],
#        [14, 15, 16, 17],
#        [18, 19, 20, 21]])

# Reshaping the array into a 2x6 matrix
print(array3.reshape(2, 6))
# Output:
# array([[10, 11, 12, 13, 14, 15],
#        [16, 17, 18, 19, 20, 21]])
```

## Splitting Arrays

Splitting arrays in NumPy involves dividing an array into two or more subarrays using the `numpy.split()` function. This function splits an array along the specified axis. We can either specify a sequence of index values where an array is to be split, or we can specify an integer N, indicating the number of equal parts in which the array is to be split.

By default, `numpy.split()` splits along `axis=0`. 

Consider the following example array:

```python
array4 = np.array([[ 10, -7, 0, 20],
                   [ -5, 1, 200, 40],
                   [ 30, 1, -1, 4],
                   [ 1, 2, 0, 4],
                   [ 0, 1, 0, 2]])

# [1,3] indicate the row indices at which to split the array
first, second, third = np.split(array4, [1, 3])

# array4 is split on the first row and stored in the sub-array first
print(first)
# Output:
# array([[10, -7,  0, 20]])

# array4 is split after the first row and up to the third row, stored in the sub-array second
print(second)
# Output:
# array([[-5,  1, 200,  40],
#        [30,  1,  -1,   4]])

# the remaining rows of array4 are stored in the sub-array third
print(third)
# Output:
# array([[1, 2, 0, 4],
#        [0, 1, 0, 2]])

# [1, 2], axis=1 specify the column indices along which to split
firstc, secondc, thirdc = np.split(array4, [1, 2], axis=1)

print(firstc)
# Output:
# array([[10],
#        [-5],
#        [30],
#        [ 1],
#        [ 0]])

print(secondc)
# Output:
# array([[-7],
#        [ 1],
#        [ 1],
#        [ 2],
#        [ 1]])

print(thirdc)
# Output:
# array([[ 0, 20],
#        [200, 40],
#        [ -1,  4],
#        [  0,  4],
#        [  0,  2]])

# 2nd parameter 2 implies the array is split into 2 equal parts along axis=1, the column axis
firsthalf, secondhalf = np.split(array4, 2, axis=1)

print(firsthalf)
# Output:
# array([[10, -7],
#        [-5,  1],
#        [30,  1],
#        [ 1,  2],
#        [ 0,  1]])

print(secondhalf)
# Output:
# array([[ 0, 20],
#        [200, 40],
#        [ -1,  4],
#        [  0,  4],
#        [  0,  2]])
```

##  Statistical Operations on Arrays

NumPy provides a variety of functions to perform statistical operations on arrays. These operations are fundamental techniques in descriptive statistics. Let's consider two arrays, `arrayA` and `arrayB`:

```python
import numpy as np

arrayA = np.array([1, 0, 2, -3, 6, 8, 4, 7])
arrayB = np.array([[3, 6], [4, 2]])
```

1. The `max()` function finds the maximum element from an array.
```python
# Maximum element from the whole 1-D array
arrayA.max()  # Output: 8

# Maximum element from the whole 2-D array
arrayB.max()  # Output: 6

# If axis=1, it gives column-wise maximum
arrayB.max(axis=1)  # Output: array([6, 4])

# If axis=0, it gives row-wise maximum
arrayB.max(axis=0)  # Output: array([4, 6])
```

2. The `min()` function finds the minimum element from an array.
```python
arrayA.min()  # Output: -3
arrayB.min()  # Output: 2
arrayB.min(axis=0)  # Output: array([3, 2])
```

3. The `sum()` function finds the sum of all elements of an array.
```python
arrayA.sum()  # Output: 25
arrayB.sum()  # Output: 15

# Axis is used to specify the dimension on which the sum is to be made.
# Here axis=1 means the sum of elements on the first row
arrayB.sum(axis=1)  # Output: array([9, 6])
```

4. The `mean()` function finds the average of elements of the array.
```python
arrayA.mean()  # Output: 3.125
arrayB.mean()  # Output: 3.75
arrayB.mean(axis=0)  # Output: array([3.5, 4.])
arrayB.mean(axis=1)  # Output: array([4.5, 3.])
```

5. The `std()` function is used to find the standard deviation of an array of elements.
```python
arrayA.std()  # Output: 3.550968177835448
arrayB.std()  # Output: 1.479019945774904
arrayB.std(axis=0)  # Output: array([0.5, 2.])
arrayB.std(axis=1)  # Output: array([1.5, 1.])
```

## Loading Arrays from Files

Sometimes, we may need to load data from files into arrays for processing. NumPy provides two primary functions for this purpose: `loadtxt()` and `genfromtxt()`. These functions are particularly useful for handling CSV (Comma Separated Values) files, which are commonly used for storing large datasets.

Let's consider an example where we have a text file named `marks.txt` stored in the folder `C:/vansh`. This file contains data in a CSV format:

```
RollNo, Marks1, Marks2, Marks3
1, 36, 18, 57
2, 22, 23, 45
3, 43, 51, 37
4, 41, 40, 60
5, 13, 18, 37
```

#### Using `numpy.loadtxt()`

We can load data from the `marks.txt` file into an array called `studentdata` using the `loadtxt()` function:

```python
import numpy as np

studentdata = np.loadtxt('C:/vansh/marks.txt', skiprows=1, delimiter=',', dtype=int)
print(studentdata)
```

In the above code:

- `skiprows=1` skips the header row.
- `delimiter=','` specifies that the values are separated by commas.
- `dtype=int` specifies the data type of the array to be integer.

#### Using `numpy.genfromtxt()`

Another function, `genfromtxt()`, can also be used to load data from files. This function can handle missing values in the data file. Let's consider a file named `Missing.txt` with missing and non-numeric values:

```
RollNo, Marks1, Marks2, Marks3
1, 36, 18, 57
2, ab, 23, 45
3, 43, 51, 37
4, 41, 40, 60
5, 13, 18, 27
```

We can load this data into an array named `dataarray` as follows:

```python
dataarray = np.genfromtxt('C:/vansh/Missing.txt', skip_header=1, delimiter=',')
print(dataarray)
```

In the above code:

- `skip_header=1` skips the header row.
- `delimiter=','` specifies that the values are separated by commas.

If there are missing or non-numeric values, `genfromtxt()` converts them to `nan` (not a number). We can specify a filling value for missing or non-numeric data using the `filling_values` parameter. For example, to set missing or non-numeric values to `-999`, we can use:

```python
dataarray = np.genfromtxt('C:/vansh/Missing.txt', skip_header=1, delimiter=',', filling_values=-999, dtype=int)
print(dataarray)
```

This code replaces missing or non-numeric values with `-999`.


## Saving NumPy Arrays in Files on Disk
The savetxt() function is used to save a NumPy array to a text file.
Example:
```python
>>> np.savetxt('C:/vansh/test.txt',studentdata, delimiter=',', fmt='%i')
```
**Note:** We have used parameter fmt to specify the format in which data are to be saved. The default is float.
