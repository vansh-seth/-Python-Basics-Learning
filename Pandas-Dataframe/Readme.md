# DataFrame

In Pandas, a DataFrame is a fundamental data structure used for handling tabular data, similar to a table in a relational database. It is a two-dimensional labelled data structure with rows and columns, each of which can have a different data type such as numeric, string, boolean, etc.

Here's an example of a DataFrame representing some geographical data:

|   | State | Geographical Area (sq Km) | Area under Very Dense Forests (sq Km) |
|---|-------|---------------------------|-----------------------------------------|
| 1 | Assam | 78438                     | 2797                                    |
| 2 | Delhi | 1483                      | 6.72                                    |
| 3 | Kerala| 38852                     | 1663                                    |

In this DataFrame:

- **Row Indexes**: Each row has an index (in this case, numerical indices starting from 1).
- **Columns**: The DataFrame has multiple columns, each with a specific label and corresponding data.
- **Data Types**: Columns can contain different types of data, such as integers, floats, strings, etc.

DataFrames provide powerful functionalities for data manipulation, analysis, and exploration. They offer methods for indexing, slicing, merging, aggregating, and filtering data, making them a versatile tool for handling structured data in Python.


## Creation of DataFrame

There are several methods to create a DataFrame in Pandas. Let's explore some of them:

### (A) Creation of an Empty DataFrame

An empty DataFrame can be created using the following steps:

```python
import pandas as pd

# Creating an empty DataFrame
dFrameEmt = pd.DataFrame()

# Displaying the empty DataFrame
print(dFrameEmt)
```

Output:
```
Empty DataFrame
Columns: []
Index: []
```

This empty DataFrame has no columns or rows. It serves as a starting point for data population or as a placeholder for future data.

## Creation of DataFrame from NumPy ndarrays

We can create a DataFrame from NumPy ndarrays in various ways. Here are some examples:

### (B.1) Using a Single ndarray

Consider the following NumPy ndarrays:

```python
import numpy as np
import pandas as pd

array1 = np.array([10, 20, 30])
array2 = np.array([100, 200, 300])
array3 = np.array([-10, -20, -30, -40])

# Creating a DataFrame from a single ndarray
dFrame4 = pd.DataFrame(array1)
print(dFrame4)
```

Output:
```
    0
0  10
1  20
2  30
```

### (B.2) Using Multiple ndarrays

We can also create a DataFrame using more than one ndarray:

```python
# Creating a DataFrame using multiple ndarrays
dFrame5 = pd.DataFrame([array1, array3, array2], columns=['A', 'B', 'C', 'D'])
print(dFrame5)
```

Output:
```
     A    B    C     D
0   10   20   30   NaN
1  -10  -20  -30 -40.0
2  100  200  300   NaN
```

In the second example, we specified column labels (`'A', 'B', 'C', 'D'`) for the DataFrame created from multiple ndarrays. Note that if the arrays have different lengths, missing values (`NaN`) are automatically inserted to maintain the DataFrame structure.
