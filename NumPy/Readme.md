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

These methods offer flexibility in creating NumPy arrays with specified data types, initialization values, and custom sequences.
