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


