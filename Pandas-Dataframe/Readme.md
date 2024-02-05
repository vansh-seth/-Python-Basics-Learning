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

### Creation of DataFrame from Series

We can create a DataFrame from one or more Pandas Series. Each Series becomes a column in the DataFrame, and the index labels of the Series become the row labels of the DataFrame.

Consider the following three Series:

```python
import pandas as pd

seriesA = pd.Series([1, 2, 3, 4, 5], index=['a', 'b', 'c', 'd', 'e'])
seriesB = pd.Series([1000, 2000, -1000, -5000, 1000], index=['a', 'b', 'c', 'd', 'e'])
seriesC = pd.Series([10, 20, -10, -50, 100], index=['z', 'y', 'a', 'c', 'e'])
```

### Creating DataFrame from a Single Series

We can create a DataFrame from a single Series:

```python
# Create DataFrame from a single Series
dFrame6 = pd.DataFrame(seriesA)
print(dFrame6)
```

Output:
```
   0
a  1
b  2
c  3
d  4
e  5
```

### Creating DataFrame from Multiple Series

To create a DataFrame from multiple Series, we pass the Series objects in a list:

```python
# Create DataFrame from multiple Series
dFrame7 = pd.DataFrame([seriesA, seriesB])
print(dFrame7)
```

Output:
```
      a     b     c     d     e
0   1.0   2.0   3.0   4.0   5.0
1  1000  2000 -1000 -5000  1000
```

### Handling Different Series Labels

If the Series objects have different labels, the DataFrame will accommodate all unique labels as columns and insert NaN for missing values:

```python
# Create DataFrame with different Series labels
dFrame8 = pd.DataFrame([seriesA, seriesC])
print(dFrame8)
```

Output:
```
      a    b     c    d      e     z     y
0   1.0  2.0   3.0  4.0    5.0   NaN   NaN
1 -10.0  NaN -50.0  NaN  100.0  10.0  20.0
```

In this DataFrame, the columns correspond to all distinct labels present in the Series objects. If a particular Series does not have a corresponding value for a label, NaN is inserted in the DataFrame column.


### Creation of DataFrame from Dictionary of Series

We can create a DataFrame from a dictionary of Pandas Series. Each key-value pair in the dictionary represents a column label and the corresponding Series, where the index values of the Series become the row labels of the DataFrame.

Consider the following example where `ResultSheet` is a dictionary of Series containing marks of 5 students in three subjects:

```python
import pandas as pd

ResultSheet = {
    'Arnab': pd.Series([90, 91, 97], index=['Maths', 'Science', 'Hindi']),
    'Ramit': pd.Series([92, 81, 96], index=['Maths', 'Science', 'Hindi']),
    'Samridhi': pd.Series([89, 91, 88], index=['Maths', 'Science', 'Hindi']),
    'Riya': pd.Series([81, 71, 67], index=['Maths', 'Science', 'Hindi']),
    'Mallika': pd.Series([94, 95, 99], index=['Maths', 'Science', 'Hindi'])
}

ResultDF = pd.DataFrame(ResultSheet)
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Science     91     81        91    71       95
Hindi       97     96        88    67       99
```

In this DataFrame:
- Each key in the dictionary (`'Arnab', 'Ramit', 'Samridhi', 'Riya', 'Mallika'`) becomes a column label.
- Each Series becomes a column in the DataFrame, where the index values of the Series become the row labels.
- The resulting index or row labels are the union of all series indexes used to create the DataFrame.

We can also see that every column in the DataFrame is indeed a Series:

```python
print(type(ResultDF['Arnab']))
```

Output:
```
<class 'pandas.core.series.Series'>
```

Additionally, if the Series have different indexes, the resulting DataFrame accommodates all unique indexes as row labels and inserts NaN for missing values, as shown in the example with `dictForUnion`.


### Operations on Rows and Columns in DataFrames

In Pandas, we can perform various operations on rows and columns of a DataFrame, including selection, deletion, addition, and renaming.

#### (A) Adding a New Column to a DataFrame

We can easily add a new column to a DataFrame. Let's consider the DataFrame `ResultDF` defined earlier containing students' marks in different subjects.

```python
# Adding a new column for student 'Preeti'
ResultDF['Preeti'] = [89, 78, 76]
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths       90     99        89    81       94      89
Science     91     98        91    71       95      78
Hindi       97     78        88    67       99      76
```

Assigning values to a new column label that does not exist will create a new column at the end of the DataFrame.

If the column already exists in the DataFrame, the assignment statement will update the values of the existing column:

```python
# Updating values for the existing column 'Ramit'
ResultDF['Ramit'] = [99, 98, 78]
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths       90     99        89    81       94      89
Science     91     98        91    71       95      78
Hindi       97     78        88    67       99      76
```

We can also change the data of an entire column to a particular value in a DataFrame:

```python
# Setting marks=90 for all subjects for the column name 'Arnab'
ResultDF['Arnab'] = 90
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths       90     99        89    81       94      89
Science     90     98        91    71       95      78
Hindi       90     78        88    67       99      76
```

In this way, we can manipulate the columns in a DataFrame by adding new columns, updating existing ones, or setting values for entire columns.

### (B) Adding a New Row to a DataFrame

We can add a new row to a DataFrame using the `DataFrame.loc[]` method. Let's consider the DataFrame `ResultDF` that contains marks for three subjects: Maths, Science, and Hindi.

```python
# Adding marks for the English subject to ResultDF
ResultDF.loc['English'] = [85, 86, 83, 80, 90, 89]
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths       90     92        89    81       94      89
Science     91     81        91    71       95      78
Hindi       97     96        88    67       99      76
English     85     86        83    80       90      89
```

We cannot use this method to add a row with an already existing (duplicate) index value (label). In such cases, the row with the specified index label will be updated.

```python
# Updating marks for the English subject in ResultDF
ResultDF.loc['English'] = [95, 86, 95, 80, 95, 99]
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths       90     92        89    81       94      89
Science     91     81        91    71       95      78
Hindi       97     96        88    67       99      76
English     95     86        95    80       95      99
```

We can also use the `DataFrame.loc[]` method to change the data values of a row to a particular value. For example, the following statement sets marks in 'Maths' for all columns to 0:

```python
# Setting marks in 'Maths' for all columns to 0
ResultDF.loc['Maths'] = 0
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths        0      0         0     0        0       0
Science     91     81        91    71       95      78
Hindi       97     96        88    67       99      76
English     95     86        95    80       95      99
```

Attempting to add a row with fewer values than the number of columns in the DataFrame results in a `ValueError`. Similarly, if we try to add a column with fewer values than the number of rows in the DataFrame, it results in a `ValueError`. 

We can also set all values of a DataFrame to a particular value:

```python
# Set all values in ResultDF to 0
ResultDF[:] = 0
print(ResultDF)
```

Output:
```
         Arnab  Ramit  Samridhi  Riya  Mallika  Preeti
Maths        0      0         0     0        0       0
Science      0      0         0     0        0       0
Hindi        0      0         0     0        0       0
English      0      0         0     0        0       0
```

### (C) Deleting Rows or Columns from a DataFrame

We can use the `DataFrame.drop()` method to delete rows and columns from a DataFrame. We specify the names of the labels to be dropped and the axis from which they need to be dropped. To delete a row, the parameter `axis` is assigned the value 0, and for deleting a column, the parameter `axis` is assigned the value 1.

Consider the following DataFrame:

```python
>>> ResultDF
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Science     91     81        91    71       95
Hindi       97     96        88    67       99
English     95     86        95    80       95
```

The following example shows how to delete the row with label 'Science':

```python
>>> ResultDF = ResultDF.drop('Science', axis=0)
>>> ResultDF
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Hindi       97     96        88    67       99
English     95     86        95    80       95
```

To delete the columns having labels 'Samridhi', 'Ramit', and 'Riya':

```python
>>> ResultDF = ResultDF.drop(['Samridhi','Ramit','Riya'], axis=1)
>>> ResultDF
         Arnab  Mallika
Maths       90       94
Hindi       97       99
English     95       95
```

If the DataFrame has more than one row with the same label, the `DataFrame.drop()` method will delete all the matching rows. For example:

```python
>>> ResultDF
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Science     91     81        91    71       95
Hindi       97     96        88    67       99
Hindi       97     89        78    60       45
```

To remove the duplicate rows labeled ‘Hindi’, we write the following statement:

```python
>>> ResultDF = ResultDF.drop('Hindi', axis=0)
>>> ResultDF
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Science     91     81        91    71       95
```

### (D) Renaming Row Labels of a DataFrame

We can change the labels of rows and columns in a DataFrame using the `DataFrame.rename()` method. To rename the row indices from 'Maths' to 'Sub1', 'Science' to 'Sub2', 'Hindi' to 'Sub3', and 'English' to 'Sub4', we can use the following statement:

```python
>>> ResultDF
         Arnab  Ramit  Samridhi  Riya  Mallika
Maths       90     92        89    81       94
Science     91     81        91    71       95
English     97     96        88    67       99
Hindi       97     89        78    60       45

>>> ResultDF = ResultDF.rename({'Maths':'Sub1', 'Science':'Sub2', 'English':'Sub3', 'Hindi':'Sub4'}, axis='index')
>>> print(ResultDF)
         Arnab  Ramit  Samridhi  Riya  Mallika
Sub1        90     92        89    81       94
Sub2        91     81        91    71       95
Sub3        97     96        88    67       99
Sub4        97     89        78    60       45
```

The parameter `axis='index'` is used to specify that the row label is to be changed. If no new label is passed corresponding to an existing label, the existing row label is left as it is. For example:

```python
>>> ResultDF = ResultDF.rename({'Maths':'Sub1', 'Science':'Sub2', 'Hindi':'Sub4'}, axis='index')
>>> print(ResultDF)
         Arnab  Ramit  Samridhi  Riya  Mallika
Sub1        90     92        89    81       94
Sub2        91     81        91    71       95
English     97     96        88    67       99
Sub4        97     89        78    60       45
```

In this case, the label 'English' remains unchanged because it was not included in the renaming dictionary.


### Renaming Column Labels of a DataFrame

To alter the column names of `ResultDF`, we can again use the `rename()` method, as shown below. The parameter `axis='columns'` implies that we want to change the column labels:

```python
>>> ResultDF = ResultDF.rename({'Arnab':'Student1', 'Ramit':'Student2', 'Samridhi':'Student3', 'Mallika':'Student4'}, axis='columns')
>>> print(ResultDF)
         Student1  Student2  Student3  Riya  Student4
Sub1           90        92        89    81        94
Sub2           91        81        91    71        95
Sub3           97        96        88    67        99
Sub4           97        89        78    60        45
```

Note that the column 'Riya' remains unchanged since we did not pass any new label for it.


### Accessing DataFrame Elements through Indexing

Data elements in a DataFrame can be accessed using indexing. There are two ways of indexing DataFrames: Label-based indexing and Boolean Indexing.

#### (A) Label-Based Indexing

There are several methods in Pandas to implement label-based indexing. `DataFrame.loc[]` is an important method that is used for label-based indexing with DataFrames. Let's continue to use the `ResultDF` created earlier.

As shown in the following example, a single row label returns the row as a Series:

```python
>>> ResultDF.loc['Science']
Arnab       91
Ramit       81
Samridhi    91
Riya        71
Mallika     95
Name: Science, dtype: int64
```

Also, note that when the row label is passed as an integer value, it is interpreted as a label of the index and not as an integer position along the index:

```python
>>> dFrame10Multiples = pd.DataFrame([10, 20, 30, 40, 50])
>>> dFrame10Multiples.loc[2]
0    30
Name: 2, dtype: int64
```

When a single column label is passed, it returns the column as a Series:

```python
>>> ResultDF.loc[:, 'Arnab']
Maths      90
Science    91
Hindi      97
Name: Arnab, dtype: int64
```

Also, we can obtain the same result, i.e., the marks of 'Arnab' in all the subjects by using the command:

```python
>>> print(df['Arnab'])
Maths      56
Science    91
English    97
Hindi      97
Name: Arnab, dtype: int64
```

To read more than one row from a DataFrame, a list of row labels is used as shown below. Note that using `[]` returns a DataFrame:

```python
>>> ResultDF.loc[['Science', 'Hindi']]
          Arnab  Ramit  Samridhi  Riya  Mallika
Science       91     81        91    71       95
Hindi         97     96        88    67       99
```

### Boolean Indexing

Boolean indexing allows us to select subsets of data based on the actual values in the DataFrame rather than their row/column labels. We can use conditions on column names to filter data values. Consider the DataFrame `ResultDF`, the following statement displays True or False depending on whether the data value satisfies the given condition or not.

```python
>>> ResultDF.loc['Maths'] > 90
Arnab      False
Ramit       True
Samridhi   False
Riya       False
Mallika     True
Name: Maths, dtype: bool
```

To check in which subjects 'Arnab' has scored more than 90, we can write:

```python
>>> ResultDF.loc[:, 'Arnab'] > 90
Maths      False
Science     True
Hindi       True
Name: Arnab, dtype: bool
```

Boolean indexing is a powerful tool for filtering data based on specific conditions, allowing us to extract relevant information from our DataFrame.
