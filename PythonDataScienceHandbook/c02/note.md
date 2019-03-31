<!--
Filename: 	note.md
Project: 	/Users/shume/Developer/DataScience/PythonDataScienceHandbook/c02
Author: 	shumez <https://github.com/shumez>
Created: 	2019-03-30 16:01:3
Modified: 	2019-03-31 20:35:17
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
- [02.04 Aggregations: Min, Max, and Everything in Between](#0204-Aggregations-Min,-Max,-and-Everything-in-Between)
- [02.05 Computation on Arrays: Broadcasting](#0405-Computation-on-Arrays-Broadcasting)
- [02.06 Comparisons, Masks, and Boolean Logic](#0406-Comparisons,-Masks,-and-Boolean-Logic)
- [02.07 Fancy Indexing](#0407-Fancy-Indexing)
- [02.08 Sorting Arrays](#0408-Sorting-Arrays)
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



## 

[x+\frac{1}{x}=1]: https://latex.codecogs.com/gif.latex?\inline&space;x+\frac{1}{x}=1
<!-- [x+\frac{1}{x}=1]: https://latex.codecogs.com/gif.latex?x+\frac{1}{x}=1 -->

<!-- <style type="text/css">
	img{width: 50%; float: right;}
</style> -->