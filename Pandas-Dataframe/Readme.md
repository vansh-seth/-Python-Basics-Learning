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

### Creation of an Empty DataFrame

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

### Creation of DataFrame from List of Dictionaries

We can create a DataFrame from a list of dictionaries in Pandas. Each dictionary in the list represents a row in the DataFrame, where the keys become the column labels and the values become the row values.

Here's how to create a DataFrame from a list of dictionaries:

```python
import pandas as pd

# Create a list of dictionaries
listDict = [{'a': 10, 'b': 20}, {'a': 5, 'b': 10, 'c': 20}]

# Create DataFrame from the list of dictionaries
dFrameListDict = pd.DataFrame(listDict)
print(dFrameListDict)
```

Output:
```
    a   b     c
0  10  20   NaN
1   5  10  20.0
```

In this DataFrame:
- The dictionary keys are taken as column labels (`'a', 'b', 'c'`).
- The values corresponding to each key in the dictionaries become the row values.
- The number of rows in the DataFrame is equal to the number of dictionaries in the list.
- The number of columns in the DataFrame is equal to the maximum number of keys in any dictionary of the list.
- If a corresponding value for a column is missing in any dictionary, `NaN` (Not a Number) is inserted in the DataFrame.

### Creation of DataFrame from Dictionary of Lists

DataFrames can also be created from a dictionary of lists in Pandas. Each key-value pair in the dictionary represents a column label and the corresponding list of values, respectively.

Here's how to create a DataFrame from a dictionary of lists:

```python
import pandas as pd

# Dictionary of lists
dictForest = {
    'State': ['Assam', 'Delhi', 'Kerala'],
    'GArea': [78438, 1483, 38852],
    'VDF': [2797, 6.72, 1663]
}

# Create DataFrame from the dictionary
dFrameForest = pd.DataFrame(dictForest)
print(dFrameForest)
```

Output:
```
    State  GArea      VDF
0   Assam  78438  2797.00
1   Delhi   1483     6.72
2  Kerala  38852  1663.00
```

In this DataFrame:
- The dictionary keys become column labels (`'State', 'GArea', 'VDF'`).
- The lists become the rows in the DataFrame.
- Each key in the dictionary corresponds to a column in the DataFrame.

We can also change the sequence of columns in a DataFrame by specifying the desired sequence in the `columns` parameter:

```python
# Creating DataFrame with custom column sequence
dFrameForest1 = pd.DataFrame(dictForest, columns=['State', 'VDF', 'GArea'])
print(dFrameForest1)
```

Output:
```
    State      VDF  GArea
0   Assam  2797.00  78438
1   Delhi     6.72   1483
2  Kerala  1663.00  38852
```

In the output, the 'VDF' column is displayed in the middle instead of being the last column as in the original DataFrame.
