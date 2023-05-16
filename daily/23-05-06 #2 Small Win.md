---
date : "2023-05-06"
title : "#2 Small Win"
slug : "2-smallwin"
time : "4h-30m"
summary : "Finished the one small intro part"
---

Finished the first course **Introduction to python,** learned a few things related to Numpy. I forgot the last time I wrote something using Numpy. So, This felt like a complete first time learning experience with occasional *“Ahh! I know that”* moments. The topic wasn’t in too much detail yet my pace was also a bit slow as I was pretty exhausted by the day even before starting. Need to shift this activity at the start of the day rather than at the end. 

I needed a refresher on *function vs methods,* I could only think of a single point that functions are independent and methods are associated with a objects and classes. Got some help with chatGPT and here are a few more 

- Functions, being defined independently with `def` keyword can take zero or more arguments. Methods on other hand are defined inside a class and have at least one default argument which is object instance aka `self.`
- Functions can be imported in other modules while methods are to be used with associated classes and objects.

Dot notation is also used when importing from sub packages, like in the case of `import from scipy.linalg import inv`.

Numpy (Numerical Python) Arrays are strongly typed, i.e., don’t allow for intermixing of data type.

```python
# Creating numpy array from regular lists
regList = [1,3,5,7]
np_array = np.array(regList)
print(type(np_array)) #<class numpy.ndarray'>

# Numpy arrays have attributes.
a.shape # (rows, cols)

```

Subarrays Comma Notation, I really like this one as it resembles to a system developed.

```python
matrix = [[1,2,3,]
           [4,5,6],
           [7,8,9]]

matrix[0][1] = 1
matrix[0,1] # turn abvoe and below are small
matrix[a:b, c:d] # gives a new grid layout
matrix.shape # (rows, cols)
```

2D subarrays

```python
import numpy as np

# create a 2D NumPy array
a = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# create a 2D subarray
subarray = a[:2, :2]

# print the subarray
print(subarray)
```

Arithmetic with numpy arrays

```python
# direct arithematic with numpy arrays

a = [1,2,3]
a+5 #Error

b = np.array(a)
b+5 #array([6,7,8])

a #[1,2,3]
a*2 #[1,2,3,1,2,3]

b #[6,7,8]
b*2 #array([12,14,16])
```

Boolean Based Indexing (subsetiting)

```python
n = [1,2,3,4,5,6]

m = n>3 #array([False,False,False,True,True,True])

y[m] #array([4,5,6])
```

```python

# Simple Stats Functions
# a → numpy array
np.mean(a)
np.median(a)
np.std(a) # std deviation
np.corrcoef(a) # measure of linear realtionship

# Generate sample data 
np.random.normal()
```
