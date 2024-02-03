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

```

```
## Reversing a Series

A Series can also be displayed in reverse order using slicing:

```python
print(seriesCapCntry[::-1])
```

## Modifying Series Values using Slicing

Slicing can also be used to modify the values of series elements.

```python
import numpy as np

seriesAlph = pd.Series(np.arange(10, 16, 1), index=['a', 'b', 'c', 'd', 'e', 'f'])
print(seriesAlph)

# Update values using positional index slicing
seriesAlph[1:3] = 50
print(seriesAlph)

# Update values using labeled index slicing
seriesAlph['c':'e'] = 500
print(seriesAlph)
```

Notice that updating values using slicing excludes the value at the end index position. However, it changes the value at the end index label when slicing is done using labels.
