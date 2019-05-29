<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/DataScience/PythonDataScienceHandbook/02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-30 16:01:3
Modified: 	2019-05-29 15:59:24
-----
Copyright (c) 2019 shumez
-->

# 02. Introduction to Numpy

## ToC

* [02.01. Understanding Data Types in Python][0201]
    * [02.01.01. A Python Interger Is More Than Just an Integer][020101]
    * [02.01.02. A Python List Is More Than Just a List][020102]
    * [02.01.03. Fixed-Type Arrays in Python][020103]
    * [02.01.04. Creating Arrays from Python Lists][020104]
    * [02.01.05. Creating Arrays from Scratch][020105]
    * [02.01.06. NumPy Standard Data Types][020106]
* [02.02. The Basics of Numpy Arrays][0202]
    * [02.02.01. NumPy Array Attributes][020201]
    * [02.02.02. Array Indexing: Accessing Single Elements][020202]
    * [02.02.03. Array Slicing: Accessing Subarrays][020203]
        * [02.02.03.01. One-dimensional subarrays][02020301]
        * [02.02.03.02. Multidimensional subarrays][02020302]
        * [02.02.03.03. Accessing array rows and columns][02020303]
        * [02.02.03.04. Subarrays as no-copy views][02020304]
        * [02.02.03.05. Creating copies of arrays][02020305]
    * [02.02.04. Reshaping of Arrays][020204]
    * [02.02.05. Array Concatenation and Splitting][020205]
        * [02.02.05.01. Concatenation of arrays][02020501]
        * [02.02.05.02. Splitting of arrays][02020502]
* [02.03. Computation on Numpy Arrays: Universal Functions][0203]
    * [02.03.01. The Slowness of Loops](#020301_The_Slowness_of_Loops)
    * [02.03.02. Introducing UFuncs](#020302_Introducing_UFuncs)
    * [02.03.03. Exploring NumPy's UFuncs](#020303_Exploring_NumPys_UFuncs)
        * [02.03.03.01. Array arithmetic](#02030301_Array_arithmetic)
        * [02.03.03.02. Absolute value](#02030302_Absolute_value)
        * [02.03.03.03. Trigometric functions](#02030303_Trigometric_functions)
        * [02.03.03.04. Exponents and logarithms](#02030304_Exponents_and_logarithms)
        * [02.03.03.05. Specialized ufuncs](#02030305_Specialized_ufuncs)
    * [02.03.04. Advanced Ufunc Features](#020304_Advanced_Ufunc_Features)
        * [02.03.04.01. Specifying output](#02030401_Specifying_output)
        * [02.03.04.02. Aggregates](#02030402_Aggregates)
        * [02.03.04.03. Outer products](#02030403_Outer_products)
    * [02.03.05. Ufuncs: Leanging More](#020305_Ufuncs_Leanging_More)
* [02.04. Aggregations: Min, Max, and Everything in Between][0204]
    * [02.04.01. Summing the Values in an Array](#020401_Summing_the_Values_in_an_Array)
    * [02.04.02. Minimum and Maximum](#020402_Minimum_and_Maximum)
        * [02.04.02.01. Multidimensional aggregates](#02040201_Multidimensional_aggregates)
        * [02.04.02.02. Other aggregation functions](#02040202_Other_aggregation_functions)
    * [02.04.03. Example: What Is the Average Height of US Presidents?](#020403_Example_What_Is_the_Average_Height_of_US_Presidents)
* [02.05. Computation on Arrays: Broadcasting][0205]
    * [02.05.01. Introducing Broadcasting](#020501_Introducing_Broadcasting)
    * [02.05.02. Rules of Broadcasting](#020502_Rules_of_Broadcasting)
        * [02.05.02.01. Broadcasting example 1](#02050201_Broadcasting_example_1)
        * [02.05.02.02. Broadcasting example 2](#02050202_Broadcasting_example_2)
        * [02.05.02.03. Broadcasting example 3](#02050203_Broadcasting_example_3)
    * [02.05.03. Broadcasting in Practice](#020503_Broadcasting_in_Practice)
        * [02.05.03.01. Centering an array](#02050301_Centering_an_array)
        * [02.05.03.02. Plotting a two-dimensional function](#02050302_Plotting_a_two-dimensional_function)
* [02.06. Comparisons, Masks, and Boolean Logic][0206]
    * [02.06.01. Example: Counting Rainy Days](#020601_Example_Counting_Rainy_Days)
        * [02.06.01.01. Digging into the data](#02060101_Digging_into_the_data)
    * [02.06.02. Comparison Operators as ufuncs](#020602_Comparison_Operators_as_ufuncs)
    * [02.06.03. Working with Boolean Arrays](#020603_Working_with_Boolean_Arrays)
        * [02.06.03.01. Counting entries](#02060301_Counting_entries)
        * [02.06.03.02. Boolean operators](#02060302_Boolean_operators)
    * [02.06.04. Boolean Arrays as Masks](#020604_Boolean_Arrays_as_Masks)
* [02.07. Fancy Indexing][0207]
    * [02.07.01. Exploring Fancy Indexing](#020701_Exploring_Fancy_Indexing)
    * [02.07.02. Combined Indexing](#020702_Combined_Indexing)
    * [02.07.03. Example: Selecting Random Points](#020703_Example_Selecting_Random_Points)
    * [02.07.04. Modifying Values with Fancy Indexing](#020704_Modifying_Values_with_Fancy_Indexing)
    * [02.07.05. Example: Binning Data](#020705_Example_Binning_Data)
* [02.08. Sorting Arrays][0208]
    * [02.08.01. Fast Sorting in Numpy: np.sort and np.argsort](#020801_fast_sorting_in_numpy_npsort_and_npargsort)
        * [02.08.01.01. Sorting along rows or columns](#02080101_sorting_along_rows_or_columns)
    * [02.08.02. Partial Sorts: Partitioning](#020802_partial_sorts_partitioning)
* [02.09. Structured Data: NumPy's Structured Arrays][0209]


## 02.01. Understanding Data Types in Python

### 02.01.01. A Python Interger Is More Than Just an Integer

### 02.01.02. A Python List Is More Than Just a List

```py
L = list(range(10))
```

```py
L2 = [str(c) for c in L]
```

### 02.01.03. Fixed-Type Arrays in Python

```py
import array
L = list(range(10))
A = array.array('i', L)
```

### 02.01.04. Creating Arrays from Python Lists

### 02.01.05. Creating Arrays from Scratch


### 02.01.06. NumPy Standard Data Types


## 02.02. The Basics of Numpy Arrays

- Attributes of arrays
- Indexing of arrays
- Slicing of arrrays
- Reshaping of arrays
- Joining and splitting of arrays


### 02.02.01. NumPy Array Attributes


### 02.02.02. Array Indexing: Accessing Single Elements


### 02.02.03. Array Slicing: Accessing Subarrays

```py
x[start:stop:step]
```

#### 02.02.03.01 One-dimensional subarrays

```py
x[1::2]
> [1 3 5 7 9]
```

```py
x[5::-2]
> [5 3 1]
```


#### 02.02.03.02 Multidimensional subarrays


#### 02.02.03.03 Accessing array rows and columns

#### 02.02.03.04 Subarrays as no-copy views

```py
x2_sub = x2[:2, :2]

x2_sub[0, 0] = 99
x2
```

original array is changed 


#### 02.02.03.05 Creating copies of arrays

```py
x2_sub_copy = x2[:2, :2].copy()
```

original array is NOT changed


### 02.02.04. Reshaping of Arrays

```py
# via reshape
x.reshape((3, 1))

# via newaxis
x[:, np.newaxis]
```


### 02.02.05. Array Concatenation and Splitting

#### 02.02.05.01. Concatenation of arrays

```py
x = np.array([1, 2, 3])
grid = np.array([[9, 8, 7], 
                 [6, 5, 4]])
np.vstack([x, grid])

y = np.array([[99], 
              [99]])
np.hstack([grid, y])

z = np.array([[-2, -1, 0], 
              [-5, -4, -3]])
np.dstack([grid, z])
```

#### 02.02.05.02. Splitting of arrays

## 02.03. Computation on NumPy Arrays: Universal Functions

### 02.03.01. The Slowness of Loops

CPython (Python's default implementation) very slowly

- **PyPy**: just-in-time compiled implementation of Python
- **Cython**: convert Python to C
- **Numba**: convert Python to LLVM bytecode


### 02.03.02. Introducing UFuncs

NumPy are implemented via **ufunc**


### 02.03.03. Exploring NumPy's UFuncs

- **unary ufuncs**
- **binary ufuncs**


#### 02.03.03.01. Array arithmetic

```py
np.add(x, 5)
np.subtract(x, 5)
np.negative(x)
np.multiply(x, 2)
np.divide(x, 2)
np.floor_divide(x, 2)
np.power(x, 2)
np.mod(x, 2)
```

| operator | ufunc           |
|----------|-----------------|
| +        | np.add          |
| -        | np.subtract     |
| -        | np.negative     |
| *        | np.multiple     |
| /        | np.divide       |
| //       | np.floor_divide |
| **       | np.power        |
| %        | np.mod          |

#### 02.03.03.02. Absolute value

#### 02.03.03.03. Trigometric functions

#### 02.03.03.04. Exponents and logarithms

#### 02.03.03.05. Specialized ufuncs


### 02.03.04. Advanced Ufunc Features

#### 02.03.04.01. Specifying output

```py
n = 100000000
x = np.arange(n)
y = np.zeros(n*2)
%timeit y[::2] = 2 ** x
%timeit np.power(2, x, out=y[::2])
```

14.2 s ± 902 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)
12.3 s ± 613 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)

#### 02.03.04.02. Aggregates

```py
np.add.reduce(x)
np.multiply.reduce(x)

np.add.accumulate(x)
np.multiply.accumulate(x)
```

#### 02.03.04.03. Outer products

```py
np.multiply.outer(x, x)
```

### 02.03.05 Ufuncs: Leanging More


## 02.04. Aggregations: Min, Max, and Everything in Between

### 02.04.01. Summing the Values in an Array

```py
sum(x)
np.sum(x)
```

### 02.04.02. Minimum and Maximum

```py
min(x)
np.min(x)
```

#### 02.04.02.01. Multidimensional aggregates

```py
M.sum(axis=0)
M.max(axis=0)
M.min(axis=1)
```


#### 02.04.02.02. Other aggregation functions


### 02.04.03. Example: What Is the Average Height of US Presidents?


## 02.05. Computation on Arrays: Broadcasting

### 02.05.01. Introducing Broadcasting


### 02.05.02. Rules of Broadcasting


#### 02.05.02.01. Broadcasting example 1


#### 02.05.02.02. Broadcasting example 2


#### 02.05.02.03. Broadcasting example 3


### 02.05.03. Broadcasting in Practice

#### 02.05.03.01. Centering an array

#### 02.05.03.02. Plotting a two-dimensional function


## 02.06. Comparisons, Masks, and Boolean Logic

### 02.06.01. Example: Counting Rainy Days

#### 02.06.01.01. Digging into the data


### 02.06.02. Comparison Operators as ufuncs

| operator | ufunc            |
|----------|------------------|
| ==       | np.equal         |
| !=       | np.not_equal     |
| <        | np.less          |
| <=       | np.less_equal    |
| >        | np.greater       |
| >=       | np.greater_equal |

### 02.06.03. Working with Boolean Arrays

#### 02.06.03.01. Counting entries

```py
np.count_nonzero(x < 6)
```

```py
np.sum(x < 6)
```

```py
np.sum(x < 6, axis=1)
```


#### 02.06.03.02. Boolean operators

| operator  | ufunc             |
|-----------|-------------------|
| `&`	    | `np.bitwise_and`  |
| `|`	    | `np.bitwise_or`   |
| `^`	    | `np.bitwise_xor`  |
| `~`	    | `np.bitwise_not`  |


### 02.06.04. Boolean Arrays as Masks

```py
x < 5

x[x < 5]
```


## 02.07. Fancy Indexing

- simple indices `arr[0]`
- slices `arr[:5]`
- Boolean masks `arr[arr > 0]`


**fancy indexing**


### 02.07.01. Exploring Fancy Indexing

```py
ind = np.array([[3, 7], 
                [4, 5]])
x[ind]
> 
[[71 86]
 [60 20]]
```

```py
X = np.arange(12).reshape((3, 4))
row = np.array([0, 1, 2])
col = np.array([2, 1, 3])

X[row, col]
> 
[ 2  5 11]
```


```py
X[row[:, np.newaxis], col]

> 
[[ 2  1  3]
 [ 6  5  7]
 [10  9 11]]
```


### 02.07.02. Combined Indexing


### 02.07.03. Example: Selecting Random Points


### 02.07.04. Modifying Values with Fancy Indexing


### 02.07.05. Example: Binning Data


## 02.08. Sorting Arrays

```py
def selection_sort(x):
    for i in range(len(x)):
        swap = i + np.argmin(x[i:])
        (x[i], x[swap]) = (x[swap], x[i])
    return x
```

```py
def bogosort(x):
    while np.any(x[:-1] > x[1:]):
        np.random.shuffle(x)
    return x
```

### 02.08.01. Fast Sorting in Numpy: np.sort and np.argsort

```py
np.sort(x)
```

```py
x.sort()
```

```py
x = np.array([2, 1, 4, 3, 5])
i = np.argsort(x)
x[i]
```

#### 02.08.01.01. Sorting along rows or columns

```py
rand = np.random.RandomState(42)
X = rand.randint(0, 10, (4, 6))
```

```py
np.sort(X, axis=0)
```

```py
np.sort(X, axis=1)
```

### 02.08.02. Partial Sorts: Partitioning


## 
<!-- tof -->
[0201]: #0201_understanding_data_types_in_python
[020101]: #020101_a_python_interger_is_more_than_just_an_integer
[020102]: #020102_a_python_list_is_more_than_just_a_list
[020103]: #020103_fixed-type_arrays_in_python
[020104]: #020104_creating_arrays_from_python_lists
[020105]: #020105_creating_arrays_from_scratch
[020106]: #020106_numpy_standard_data_types
[0202]: #0202_the_basics_of_numpy_arrays
[020201]: #020201_NumPy_Array_Attributes
[020202]: #020202_Array_Indexing_Accessing_Single_Elements
[020203]: #020203_Array_Slicing_Accessing_Subarrays
[02020301]: #02020301_One-dimensional_subarrays
[02020302]: #02020302_Multidimensional_subarrays
[02020303]: #02020303_Accessing_array_rows_and_columns
[02020304]: #02020304_Subarrays_as_no-copy_views
[02020305]: #02020305_Creating_copies_of_arrays
[020204]: #020204_Reshaping_of_Arrays
[020205]: #020205_Array_Concatenation_and_Splitting
[02020501]: #02020501_Concatenation_of_arrays
[02020502]: #02020502_Splitting_of_arrays

[0203]: #0203_computation_on_numpy_arrays_universal_functions

[0204]: #0204_aggregations_min_max_and_everything_in_between

[0205]: #0205_computation_on_arrays_broadcasting

[0206]: #0206_comparisons_masks_and_boolean_logic

[0207]: #0207_fancy_indexing

[0208]: #0208_sorting_arrays

[0209]: #0209_structured_data_numpys_structured_arrays

<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->