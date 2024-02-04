# Introduction to Python Libraries

Python libraries encompass a plethora of built-in modules that streamline various tasks without necessitating intricate programming. Each library in Python houses an array of modules that can be imported and utilized.

NumPy, Pandas, and Matplotlib stand as three cornerstone Python libraries in the realms of scientific and analytical endeavors. These libraries facilitate the effortless manipulation, transformation, and visualization of data.

**NumPy**, short for 'Numerical Python', is a library often introduced in the curriculum of XI grade. It serves as a package tailored for numerical data analysis and scientific computing. NumPy leverages a multidimensional array object and boasts functions and tools tailored for seamless manipulation of these arrays. By virtue of elements of an array being stored together in memory, quick access is guaranteed.

**Pandas (PANel DAta)** emerges as a high-level data manipulation tool revered for its prowess in data analysis. It offers effortless data importation and exportation capabilities, complemented by a rich suite of functions. Pandas builds upon packages like NumPy and Matplotlib, providing a unified platform for comprehensive data analysis and visualization tasks. Within Pandas, three pivotal data structures - Series, DataFrame, and Panel - streamline the process of data analysis, fostering organization, efficacy, and efficiency.

The **Matplotlib** library in Python serves as the go-to solution for graph plotting and visualization. With Matplotlib, generating publication-quality plots, histograms, bar charts, scatterplots, etc., requires only a few lines of code. As it's built upon NumPy, Matplotlib seamlessly integrates with NumPy and Pandas.

You might wonder about the necessity of Pandas when NumPy suffices for data analysis. Here are some differentiating points between Pandas and NumPy:

1. **Data Type Handling**: While a NumPy array necessitates homogeneous data, a Pandas DataFrame accommodates diverse data types (float, int, string, datetime, etc.).
2. **Interface Complexity**: Pandas offers a more straightforward interface for tasks like file loading, plotting, selection, joining, GROUP BY, which prove invaluable in data processing applications.
3. **Columnar Structure**: Pandas DataFrames, with their column names, simplify data tracking considerably.
4. **Data Format**: Pandas is preferred for tabular data formats, while NumPy excels in numeric array-based data manipulation.

## Installing Pandas

Bringing Pandas into your Python toolkit follows a similar path to integrating NumPy. It's a straightforward process:

To introduce Pandas, execute the following command in your command line interface:

``` python
pip install pandas
```

Remember, the presence of Python in the system is a prerequisite for installing Pandas (or NumPy), as well as other Python libraries.

## Data Structure in Pandas

Within the realm of programming, a data structure stands as a foundational framework housing both data values and the operations applicable to them. It serves as a cornerstone, facilitating the efficient storage, retrieval, and modification of data. Think back to our introduction to the ndarray data structure in NumPy during Class XI; consider the seamless experience of storing, accessing, and updating data facilitated by NumPy arrays.

In the domain of Pandas, two pivotal data structures take the spotlight:

- **Series**: A Pandas Series represents a one-dimensional array that can accommodate diverse data types. Acting as a labeled index array, it enables swift access and manipulation of data elements.

- **DataFrame**: The DataFrame structure serves as the bedrock of tabular data representation in Pandas. Mimicking a two-dimensional table, it encompasses rows and columns, facilitating intuitive organization, exploration, and analysis of datasets.


## Series

In the realm of Pandas, a Series serves as a unidimensional array housing a sequence of values spanning across diverse data types, including integers, floats, lists, and strings. By default, these values are allocated numeric indices commencing from zero. These numeric labels, serving as identifiers for each value, are termed as indices. Moreover, Pandas affords the flexibility of assigning values of various data types as indices, broadening its utility. Conceptually, envisioning a Pandas Series mirrors visualizing a column within a spreadsheet, where each value is meticulously associated with a specific index.

Consider the following depiction of a Pandas Series comprising names of students:

| Index | Value    |
|-------|----------|
| 0     | Arnab    |
| 1     | Samridhi |
| 2     | Ramit    |
| 3     | Divyam   |
| 4     | Kritika  |


## Series Creation in Pandas

Creating a Series in Pandas entails various methods, each tailored to different scenarios. Before delving into series creation, it's imperative to import the Pandas library.

### (A) Creation of Series from Scalar Values

A Series can be instantiated using scalar values, exemplified below:

```python
import pandas as pd  # Import Pandas with the alias pd
series1 = pd.Series([10, 20, 30])  # Create a Series
print(series1)  # Display the series
```

Output:
```
0    10
1    20
2    30
dtype: int64
```

The output presents two columns - the index on the left and the data value on the right. If no index is explicitly specified during series creation, the indices default to the range from 0 through N-1, where N denotes the number of data elements.

Moreover, user-defined labels can be assigned to the index, facilitating element access within a Series. In the ensuing example, a numeric index is assigned in a non-sequential order:

```python
series2 = pd.Series(["Kavi", "Shyam", "Ravi"], index=[3, 5, 1])
print(series2)  # Display the series
```

Output:
```
3    Kavi
5    Shyam
1    Ravi
dtype: object
```

Here, the data values Kavi, Shyam, and Ravi correspond to index values 3, 5, and 1, respectively. Furthermore, letters or strings can serve as indices, as demonstrated below:

```python
series3 = pd.Series([2, 3, 4], index=["Feb", "Mar", "Apr"])
print(series3)  # Display the series
```

Output:
```
Feb    2
Mar    3
Apr    4
dtype: int64
```

In this instance, the data values 2, 3, and 4 are associated with index values Feb, Mar, and Apr, respectively.

## Series Creation from NumPy Arrays

Another approach to creating a Series in Pandas involves leveraging one-dimensional NumPy arrays. This method provides seamless integration between NumPy and Pandas functionalities, as illustrated below:

```python
import numpy as np  # Import NumPy with the alias np
import pandas as pd

array1 = np.array([1, 2, 3, 4])
series3 = pd.Series(array1)
print(series3)
```

Output:
```
0    1
1    2
2    3
3    4
dtype: int32
```

The example demonstrates the creation of a Series from a one-dimensional NumPy array. By default, the Series inherits the numeric indices from the array.

Furthermore, it's feasible to assign letters or strings as indices, as showcased below:

```python
series4 = pd.Series(array1, index=["Jan", "Feb", "Mar", "Apr"])
print(series4)
```

Output:
```
Jan    1
Feb    2
Mar    3
Apr    4
dtype: int32
```

However, it's crucial to ensure that the length of the index and the array coincide. Otherwise, a ValueError will be triggered, as demonstrated in the ensuing example:

```python
series5 = pd.Series(array1, index=["Jan", "Feb", "Mar"])
```

Output:
```
ValueError: Length of passed values is 4, index implies 3
```

Here, the discrepancy between the length of the array and the index labels results in a ValueError.


## Series Creation from Dictionary

In Pandas, it's feasible to construct a Series directly from a Python dictionary, exploiting the key-value pairs inherent in dictionaries. This approach enables swift conversion of dictionary elements into Series indices and values, as elucidated below:

```python
dict1 = {'India': 'New Delhi', 'UK': 'London', 'Japan': 'Tokyo'}
print(dict1)  # Display the dictionary
```

Output:
```
{'India': 'New Delhi', 'UK': 'London', 'Japan': 'Tokyo'}
```

Here, the dictionary `dict1` consists of key-value pairs representing countries and their respective capitals.

Subsequently, a Pandas Series is instantiated from the dictionary:

```python
series8 = pd.Series(dict1)
print(series8)  # Display the series
```

Output:
```
India    New Delhi
UK          London
Japan        Tokyo
dtype: object
```

In this instance, the keys of the dictionary `dict1` serve as the indices for the Series, while the corresponding values are seamlessly integrated as the Series data values.

Constructing a Series from a dictionary provides a concise and intuitive means of organizing and manipulating data, leveraging the inherent structure of Python dictionaries.


## Series Element Access Methods

In Pandas, accessing elements of a Series can be accomplished through indexing and slicing techniques.

## Indexing

Indexing in Series resembles NumPy arrays and enables access to individual elements. There are two types of indexes: positional and labeled.

### Positional Indexing

Positional indexing uses integer values corresponding to the element's position in the Series, starting from 0.

```python
import pandas as pd

# Example of positional indexing
seriesNum = pd.Series([10, 20, 30])
print(seriesNum[2])  # Outputs: 30
```

In this example, the value 30 is accessed using the positional index 2.

### Labeled Indexing

Labeled indexing allows the use of user-defined labels to access elements.

```python
# Example of labeled indexing
seriesMnths = pd.Series([2, 3, 4], index=["Feb", "Mar", "Apr"])
print(seriesMnths["Mar"])  # Outputs: 3
```

Here, the value 3 is accessed using the labeled index "Mar".

```python
seriesCapCntry = pd.Series(['NewDelhi', 'WashingtonDC', 'London', 'Paris'],
                           index=['India', 'USA', 'UK', 'France'])
print(seriesCapCntry['India'])  # Outputs: 'NewDelhi'
```

### Accessing Elements

Elements can also be accessed using the positional index:

```python
print(seriesCapCntry[1])  # Outputs: 'WashingtonDC'
```

Multiple elements can be accessed using lists of positional integers or index labels:

```python
print(seriesCapCntry[[3, 2]])  # Outputs: France Paris UK London
print(seriesCapCntry[['UK', 'USA']])  # Outputs: UK London USA WashingtonDC
```

## Modifying Index Values

Index values associated with a Series can be modified by assigning new index values:

```python
seriesCapCntry.index = [10, 20, 30, 40]
print(seriesCapCntry)
```

This changes the index values to [10, 20, 30, 40], respectively.


## Series Slicing

In Pandas, slicing allows us to extract specific portions of a Series, similar to slicing in NumPy arrays.

## Basic Slicing

Slicing is performed by specifying the start and end parameters `[start:end]` with the Series name. With positional indices, the value at the `end` index position is excluded.

### Positional Index Slicing

```python
import pandas as pd

# Example of positional index slicing
seriesCapCntry = pd.Series(['NewDelhi', 'WashingtonDC', 'London', 'Paris'],
                           index=['India', 'USA', 'UK', 'France'])
print(seriesCapCntry[1:3])  # Excludes the value at index position 3
```
### Output
```
USA     WashingtonDC
UK            London
dtype: object
```
In this example, only data values at indices 1 and 2 are displayed.

### Labeled Index Slicing

When using labeled indexes for slicing, the value at the end index label is included in the output.

```python
print(seriesCapCntry['USA':'France'])
```
### Output
```
USA     WashingtonDC
UK            London
France         Paris
dtype: object

```
## Reversing a Series

A Series can also be displayed in reverse order using slicing:

```python
print(seriesCapCntry[::-1])
```

### Output
```
France        Paris
UK           London
USA    WashingtonDC
India      NewDelhi
dtype: object

```

## Modifying Series Values using Slicing

Slicing can also be used to modify the values of series elements.

```python
import numpy as np

seriesAlph = pd.Series(np.arange(10, 16, 1), index=['a', 'b', 'c', 'd', 'e', 'f'])
print(seriesAlph)
# OUTPUT:
a 10
b 11
c 12
d 13
e 14
f 15
dtype: int32

# Update values using positional index slicing
seriesAlph[1:3] = 50
print(seriesAlph)

#OUTPUT:
a 10
b 50
c 50
d 13
e 14
f 15
dtype: int32

# Update values using labeled index slicing
seriesAlph['c':'e'] = 500
print(seriesAlph)

# OUTPUT:
a 10
b 50
c 500
d 500
e 500
f 15
dtype: int32
```

Notice that updating values using slicing excludes the value at the end index position. However, it changes the value at the end index label when slicing is done using labels.


## Series Attributes

In Pandas, certain properties called attributes of a Series can be accessed using the Series name.

## Example: Attributes of a Series

Consider a Series named `seriesCapCntry`:

```python
import pandas as pd

# Example Series
seriesCapCntry = pd.Series(['NewDelhi', 'WashingtonDC', 'London', 'Paris'],
                            index=['India', 'USA', 'UK', 'France'])
print(seriesCapCntry)
```

The output displays:

```
India        NewDelhi
USA      WashingtonDC
UK             London
France           Paris
dtype: object
```

## Attributes of a Series

### `dtype`

The `dtype` attribute represents the data type of the elements in the Series.

```python
print(seriesCapCntry.dtype)
```

Output:

```
object
```

The dtype of the Series is `object`.

### `index`

The `index` attribute returns the index labels of the Series.

```python
print(seriesCapCntry.index)
```

Output:

```
Index(['India', 'USA', 'UK', 'France'], dtype='object')
```

The index labels are `India`, `USA`, `UK`, and `France`.

### `values`

The `values` attribute returns the actual data values of the Series.

```python
print(seriesCapCntry.values)
```

Output:

```
['NewDelhi' 'WashingtonDC' 'London' 'Paris']
```

These are the values contained in the Series.


## Attributes of Pandas Series

Attributes in Pandas Series provide valuable information about the Series object, its data, and its structure. Below are some key attributes commonly used with Pandas Series:

### 1. `name`

- **Purpose**: Assigns a name to the Series.
- **Example**:
  ```python
  seriesCapCntry.name = 'Capitals'
  print(seriesCapCntry)
  ```
  Output:
  ```
  India        NewDelhi
  USA      WashingtonDC
  UK             London
  France           Paris
  Name: Capitals, dtype: object
  ```

### 2. `index.name`

- **Purpose**: Assigns a name to the index of the series.
- **Example**:
  ```python
  seriesCapCntry.index.name = 'Countries'
  print(seriesCapCntry)
  ```
  Output:
  ```
  Countries
  India        NewDelhi
  USA      WashingtonDC
  UK             London
  France           Paris
  Name: Capitals, dtype: object
  ```

### 3. `values`

- **Purpose**: Prints a list of the values in the series.
- **Example**:
  ```python
  print(seriesCapCntry.values)
  ```
  Output:
  ```
  ['NewDelhi' 'WashingtonDC' 'London' 'Paris']
  ```

### 4. `size`

- **Purpose**: Prints the number of values in the Series object.
- **Example**:
  ```python
  print(seriesCapCntry.size)
  ```
  Output:
  ```
  4
  ```

### 5. `empty`

- **Purpose**: Prints `True` if the series is empty, and `False` otherwise.
- **Example**:
  ```python
  print(seriesCapCntry.empty)
  ```
  Output:
  ```
  False
  ```

  - Creating an empty series:
    ```python
    seriesEmpt = pd.Series()
    print(seriesEmpt.empty)
    ```
    Output:
    ```
    True
    ```


## Methods of Series

This section discusses some of the methods available for Pandas Series. Consider the following series named `seriesTenTwenty`:

```python
import numpy as np
import pandas as pd

seriesTenTwenty = pd.Series(np.arange(10, 20, 1))
print(seriesTenTwenty)
```

Output:
```
0    10
1    11
2    12
3    13
4    14
5    15
6    16
7    17
8    18
9    19
dtype: int32
```

### 1. `head()`

- **Purpose**: Returns the first n rows of the series.
- **Example**:
  ```python
  print(seriesTenTwenty.head(3))
  ```
  Output:
  ```
  0    10
  1    11
  2    12
  dtype: int32
  ```

### 2. `tail()`

- **Purpose**: Returns the last n rows of the series.
- **Example**:
  ```python
  print(seriesTenTwenty.tail(3))
  ```
  Output:
  ```
  7    17
  8    18
  9    19
  dtype: int32
  ```

### 3. `describe()`

- **Purpose**: Generates descriptive statistics of the series.
- **Example**:
  ```python
  print(seriesTenTwenty.describe())
  ```
  Output:
  ```
  count    10.000000
  mean     14.500000
  std       2.872281
  min      10.000000
  25%      12.250000
  50%      14.500000
  75%      16.750000
  max      19.000000
  dtype: float64
  ```

### 4. `sum()`

- **Purpose**: Computes the sum of the values in the series.
- **Example**:
  ```python
  print(seriesTenTwenty.sum())
  ```
  Output:
  ```
  145
  ```

### 5. `mean()`

- **Purpose**: Computes the mean of the values in the series.
- **Example**:
  ```python
  print(seriesTenTwenty.mean())
  ```
  Output:
  ```
  14.5
  ```

## Mathematical Operations on Series

In Pandas, we can perform basic mathematical operations on two Series objects. Similar to NumPy arrays, these operations are conducted on each corresponding pair of elements, taking into account index matching. Any missing values are filled with `NaN` by default.

Consider the following series: `seriesA` and `seriesB` for understanding mathematical operations on Series in Pandas:

```python
import pandas as pd

seriesA = pd.Series([1, 2, 3, 4, 5], index=['a', 'b', 'c', 'd', 'e'])
print(seriesA)
```

Output:
```
a    1
b    2
c    3
d    4
e    5
dtype: int64
```

```python
seriesB = pd.Series([10, 20, -10, -50, 100], index=['z', 'y', 'a', 'c', 'e'])
print(seriesB)
```

Output:
```
z     10
y     20
a    -10
c    -50
e    100
dtype: int64
```

### Addition Operation

```python
addition_result = seriesA + seriesB
print(addition_result)
```

Output:
```
a     -9.0
b      NaN
c    -47.0
d      NaN
e    105.0
y      NaN
z      NaN
dtype: float64
```

### Subtraction Operation

```python
subtraction_result = seriesA - seriesB
print(subtraction_result)
```

Output:
```
a     11.0
b      NaN
c     53.0
d      NaN
e    -95.0
y      NaN
z      NaN
dtype: float64
```

### Multiplication Operation

```python
multiplication_result = seriesA * seriesB
print(multiplication_result)
```

Output:
```
a    -10.0
b      NaN
c   -150.0
d      NaN
e    500.0
y      NaN
z      NaN
dtype: float64
```

### Division Operation

```python
division_result = seriesA / seriesB
print(division_result)
```

Output:
```
a   -0.100000
b         NaN
c   -0.060000
d         NaN
e    0.050000
y         NaN
z         NaN
dtype: float64
```

These examples illustrate how mathematical operations between two Series objects in Pandas work, considering index matching and handling missing values gracefully with `NaN`.

## Addition of Two Series

Adding two Series in Pandas can be done in two ways. The first method simply adds the two series together, where the operation results in `NaN` if one or both elements have no value.

### Method 1: Direct Addition
```python
result_direct_addition = seriesA + seriesB
print(result_direct_addition)
```

Output:
```
a     -9.0
b      NaN
c    -47.0
d      NaN
e    105.0
y      NaN
z      NaN
dtype: float64
```

### Method 2: Using `add()` Method with `fill_value`

The `add()` method allows explicit specification of a fill value for any missing element in either series. This method replaces missing values with the specified value during addition.

```python
result_filled_addition = seriesA.add(seriesB, fill_value=0)
print(result_filled_addition)
```

Output:
```
a     -9.0
b      2.0
c    -47.0
d      4.0
e    105.0
y     20.0
z     10.0
dtype: float64
```

### Details of Addition Using `add()` Method
| Index | Value from seriesA | Value from seriesB | seriesA + seriesB |
|-------|--------------------|--------------------|-------------------|
| a     | 1                  | -10                | -9.0              |
| b     | 2                  | 0                  | 2.0               |
| c     | 3                  | -50                | -47.0             |
| d     | 4                  | 0                  | 4.0               |
| e     | 5                  | 100                | 105.0             |
| y     | 0                  | 20                 | 20.0              |
| z     | 0                  | 10                 | 10.0              |

Note that the second method using `add()` replaces missing values with 0, resulting in a different output compared to the direct addition method. Similarly, subtraction, multiplication, and division operations can also be performed using corresponding mathematical operators or explicit method calls.

## Subtraction of Two Series

Subtracting one Series from another in Pandas can be accomplished in two ways. Similar to addition, subtraction can be done directly or by using the `sub()` method with a specified fill value for missing elements.

### Method 1: Direct Subtraction

Performing subtraction using the subtraction operator `-` directly between the two Series:

```python
result_direct_subtraction = seriesA - seriesB
print(result_direct_subtraction)
```

Output:
```
a     11.0
b      NaN
c     53.0
d      NaN
e    -95.0
y      NaN
z      NaN
dtype: float64
```

### Method 2: Using `sub()` Method with Fill Value

Subtracting one Series from another using the `sub()` method with a specified fill value for missing elements:

```python
result_filled_subtraction = seriesA.sub(seriesB, fill_value=1000)
print(result_filled_subtraction)
```

Output:
```
a      11.0
b    -998.0
c      53.0
d    -996.0
e     -95.0
y     980.0
z     990.0
dtype: float64
```

### Details of Subtraction

| Index | Value from seriesA | Value from seriesB | seriesA - seriesB |
|-------|--------------------|--------------------|-------------------|
| a     | 1                  | -10                | 11.0              |
| b     | 2                  | NaN                | NaN               |
| c     | 3                  | -50                | 53.0              |
| d     | 4                  | NaN                | NaN               |
| e     | 5                  | 100                | -95.0             |
| y     | NaN                | 20                 | NaN               |
| z     | NaN                | 10                 | NaN               |

The second method using `sub()` replaces missing values with 1000, resulting in a different output compared to the direct subtraction method. Similarly, other mathematical operations like multiplication and division can also be performed using corresponding operators or explicit method calls.

## Multiplication of Two Series

Multiplying two Series in Pandas can be achieved in two different ways, similarly to addition and subtraction. The first method involves using the multiplication operator `*` directly between the two Series. The second method utilizes the `mul()` method with a specified fill value for missing elements.

### Method 1: Direct Multiplication

Performing multiplication using the multiplication operator `*` directly between the two Series:

```python
result_direct_multiplication = seriesA * seriesB
print(result_direct_multiplication)
```

Output:
```
a    -10.0
b      NaN
c   -150.0
d      NaN
e    500.0
y      NaN
z      NaN
dtype: float64
```

### Method 2: Using `mul()` Method with Fill Value

Multiplying one Series by another using the `mul()` method with a specified fill value for missing elements:

```python
result_filled_multiplication = seriesA.mul(seriesB, fill_value=0)
print(result_filled_multiplication)
```

Output:
```
a    -10.0
b      0.0
c   -150.0
d      0.0
e    500.0
y      0.0
z      0.0
dtype: float64
```

### Details of Multiplication

| Index | Value from seriesA | Value from seriesB | seriesA * seriesB |
|-------|--------------------|--------------------|-------------------|
| a     | 1                  | -10                | -10.0             |
| b     | 2                  | NaN                | 0.0               |
| c     | 3                  | -50                | -150.0            |
| d     | 4                  | NaN                | 0.0               |
| e     | 5                  | 100                | 500.0             |
| y     | NaN                | 20                 | 0.0               |
| z     | NaN                | 10                 | 0.0               |

The second method using `mul()` replaces missing values with 0, resulting in a different output compared to the direct multiplication method. Similarly, other mathematical operations like addition, subtraction, and division can also be performed using corresponding operators or explicit method calls.
