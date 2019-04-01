<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/DataScience/PythonDataScienceHandbook/c02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-30 16:01:3
Modified: 	2019-04-01 21:25:59
-----
Copyright (c) 2019 shumez
-->

# 02 Introduction to Numpy

## Contents

- [02.01 Understanding Data Types in Python](#0201-Understanding-Data-Types-in-Python)
    - [02.01.01 A Python Interger Is More Than Just an Integer](#020101-A-Python-Interger-Is-More-Than-Just-an-Integer)
    - [02.01.02 A Python List Is More Than Just a List](#020102-A-Python-List-Is-More-Than-Just-a-List)
    - [02.01.03 Fixed-Type Arrays in Python](#020103-Fixed-Type-Arrays-in-Python)
    - [02.01.04 Creating Arrays from Python Lists](#020104-Creating-Arrays-from-Python-Lists)
    - [02.01.05 Creating Arrays from Scratch](#020105-Creating-Arrays-from-Scratch)
    - [02.01.06 NumPy Standard Data Types](#020106-NumPy-Standard-Data-Types)
- [02.02 The Basics of Numpy Arrays](#0202-The-Basics-of-Numpy-Arrays)
    - [02.02.01 NumPy Array Attributes](#020201-NumPy-Array-Attributes)
    - [02.02.02 Array Indexing: Accessing Single Elements](#020202-Array-Indexing-Accessing-Single-Elements)
    - [02.02.03 Array Slicing: Accessing Subarrays](#020203-Array-Slicing-Accessing-Subarrays)
        - [02.02.03.01 One-dimensional subarrays](#02020301-One-dimensional-subarrays)
        - [02.02.03.02 Multidimensional subarrays](#02020302-Multidimensional-subarrays)
        - [02.02.03.03 Accessing array rows and columns](#02020303-Accessing-array-rows-and-columns)
        - [02.02.03.04 Subarrays as no-copy views](#02020304-Subarrays-as-no-copy-views)
        - [02.02.03.05 Creating copies of arrays](#02020305-Creating-copies-of-arrays)
    - [02.02.04 Reshaping of Arrays](#020204-Reshaping-of-Arrays)
    - [02.02.05 Array Concatenation and Splitting](#020205-Array-Concatenation-and-Splitting)
        - [02.02.05.01 Concatenation of arrays](#02020501-Concatenation-of-arrays)
        - [02.02.05.02 Splitting of arrays](#02020502-Splitting-of-arrays)
- [02.03 Computation on Numpy Arrays: Universal Functions](#0203-Computation-on-Numpy-Arrays-Universal-Functions)
    - [02.03.01 The Slowness of Loops](#020301-The-Slowness-of-Loops)
    - [02.03.02 Introducing UFuncs](#020302-Introducing-UFuncs)
    - [02.03.03 Exploring NumPy's UFuncs](#020303-Exploring-NumPys-UFuncs)
        - [02.03.03.01 Array arithmetic](#02030301-Array-arithmetic)
        - [02.03.03.02 Absolute value](#02030302-Absolute-value)
        - [02.03.03.03 Trigometric functions](#02030303-Trigometric-functions)
        - [02.03.03.04 Exponents and logarithms](#02030304-Exponents-and-logarithms)
        - [02.03.03.05 Specialized ufuncs](#02030305-Specialized-ufuncs)
    - [02.03.04 Advanced Ufunc Features](#020304-Advanced-Ufunc-Features)
        - [02.03.04.01 Specifying output](#02030401-Specifying-output)
        - [02.03.04.02 Aggregates](#02030402-Aggregates)
        - [02.03.04.03 Outer products](#02030403-Outer-products)
    - [02.03.05 Ufuncs: Leanging More](#020305-Ufuncs-Leanging-More)
- [02.04 Aggregations: Min, Max, and Everything in Between](#0204-Aggregations-Min-Max-and-Everything-in-Between)
    - [02.04.01 Summing the Values in an Array](#020401-Summing-the-Values-in-an-Array)
    - [02.04.02 Minimum and Maximum](#020402-Minimum-and-Maximum)
        - [02.04.02.01 Multidimensional aggregates](#02040201-Multidimensional-aggregates)
        - [02.04.02.02 Other aggregation functions](#02040202-Other-aggregation-functions)
    - [02.04.03 Example: What Is the Average Height of US Presidents?](#020403-Example-What-Is-the-Average-Height-of-US-Presidents)
- [02.05 Computation on Arrays: Broadcasting](#0205-Computation-on-Arrays-Broadcasting)
    - [02.05.01 Introducing Broadcasting](#020501-Introducing-Broadcasting)
    - [02.05.02 Rules of Broadcasting](#020502-Rules-of-Broadcasting)
        - [02.05.02.01 Broadcasting example 1](#02050201-Broadcasting-example-1)
        - [02.05.02.02 Broadcasting example 2](#02050202-Broadcasting-example-2)
        - [02.05.02.03 Broadcasting example 3](#02050203-Broadcasting-example-3)
    - [02.05.03 Broadcasting in Practice](#020503-Broadcasting-in-Practice)
        - [02.05.03.01 Centering an array](#02050301-Centering-an-array)
        - [02.05.03.02 Plotting a two-dimensional function](#02050302-Plotting-a-two-dimensional-function)
- [02.06 Comparisons, Masks, and Boolean Logic](#0206-Comparisons-Masks-and-Boolean-Logic)
    - [02.06.01 Example: Counting Rainy Days](#020601-Example-Counting-Rainy-Days)
        - [02.06.01.01 Digging into the data](#02060101-Digging-into-the-data)
    - [02.06.02 Comparison Operators as ufuncs](#020602-Comparison-Operators-as-ufuncs)
    - [02.06.03 Working with Boolean Arrays](#020603-Working-with-Boolean-Arrays)
- [02.07 Fancy Indexing](#0207-Fancy-Indexing)
- [02.08 Sorting Arrays](#0208-Sorting-Arrays)
- [02.09 Structured Data: NumPy's Structured Arrays](#0209-Structured-Data-NumPy's-Structured-Arrays)


## 02.01 Understanding Data Types in Python

### 02.01.01 A Python Interger Is More Than Just an Integer

### 02.01.02 A Python List Is More Than Just a List

```py
L = list(range(10))
```

```py
L2 = [str(c) for c in L]
```

### 02.01.03 Fixed-Type Arrays in Python

```py
import array
L = list(range(10))
A = array.array('i', L)
```

### 02.01.04 Creating Arrays from Python Lists

### 02.01.05 Creating Arrays from Scratch


### 02.01.06 NumPy Standard Data Types


## 02.02 The Basics of Numpy Arrays

- Attributes of arrays
- Indexing of arrays
- Slicing of arrrays
- Reshaping of arrays
- Joining and splitting of arrays


### 02.02.01 NumPy Array Attributes


### 02.02.02 Array Indexing: Accessing Single Elements


### 02.02.03 Array Slicing: Accessing Subarrays

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


### 02.02.04 Reshaping of Arrays

```py
# via reshape
x.reshape((3, 1))

# via newaxis
x[:, np.newaxis]
```


### 02.02.05 Array Concatenation and Splitting

#### 02.02.05.01 Concatenation of arrays

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

#### 02.02.05.02 Splitting of arrays

## 02.03 Computation on NumPy Arrays: Universal Functions

### 02.03.01 The Slowness of Loops

CPython (Python's default implementation) very slowly

- **PyPy**: just-in-time compiled implementation of Python
- **Cython**: convert Python to C
- **Numba**: convert Python to LLVM bytecode


### 02.03.02 Introducing UFuncs

NumPy are implemented via **ufunc**


### 02.03.03 Exploring NumPy's UFuncs

- **unary ufuncs**
- **binary ufuncs**


#### 02.03.03.01 Array arithmetic

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

#### 02.03.03.02 Absolute value

#### 02.03.03.03 Trigometric functions

#### 02.03.03.04 Exponents and logarithms

#### 02.03.03.05 Specialized ufuncs


### 02.03.04 Advanced Ufunc Features

#### 02.03.04.01 Specifying output

```py
n = 100000000
x = np.arange(n)
y = np.zeros(n*2)
%timeit y[::2] = 2 ** x
%timeit np.power(2, x, out=y[::2])
```

14.2 s ± 902 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)
12.3 s ± 613 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)

#### 02.03.04.02 Aggregates

```py
np.add.reduce(x)
np.multiply.reduce(x)

np.add.accumulate(x)
np.multiply.accumulate(x)
```

#### 02.03.04.03 Outer products

```py
np.multiply.outer(x, x)
```

### 02.03.05 Ufuncs: Leanging More


## 02.04 Aggregations: Min, Max, and Everything in Between

### 02.04.01 Summing the Values in an Array

```py
sum(x)
np.sum(x)
```

### 02.04.02 Minimum and Maximum

```py
min(x)
np.min(x)
```

#### 02.04.02.01 Multidimensional aggregates

```py
M.sum(axis=0)
M.max(axis=0)
M.min(axis=1)
```


#### 02.04.02.02 Other aggregation functions


### 02.04.03 Example: What Is the Average Height of US Presidents?


## 02.05 Computation on Arrays: Broadcasting

### 02.05.01 Introducing Broadcasting


### 02.05.02 Rules of Broadcasting


#### 02.05.02.01 Broadcasting example 1


#### 02.05.02.02 Broadcasting example 2


#### 02.05.02.03 Broadcasting example 3


### 02.05.03 Broadcasting in Practice

#### 02.05.03.01 Centering an array

#### 02.05.03.02 Plotting a two-dimensional function


## 02.06 Comparisons, Masks, and Boolean Logic

### 02.06.01 Example: Counting Rainy Days

#### 02.06.01.01 Digging into the data


### 02.06.02 Comparison Operators as ufuncs


### 02.06.03 Working with Boolean Arrays



## 

[x+\frac{1}{x}=1]: https://latex.codecogs.com/gif.latex?\inline&space;x+\frac{1}{x}=1
<!-- [x+\frac{1}{x}=1]: https://latex.codecogs.com/gif.latex?x+\frac{1}{x}=1 -->

<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->