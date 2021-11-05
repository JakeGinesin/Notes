###### tags: `COMP30760 - Data Science with Python`

# Intro to Numpy
- Standard Python containers are convenient but not designed for large scale data analysis
- **NumPy** is the standard Python package for scientific computing:
    - Provides support for multidimentional arrays
    - Implemented closer to hardware for efficiency
    - Designed for scientnific computation, useful for linear algebra and data analysis
- NumPy can "turn Python into the equivilant of a free and more powerful form of matlab"

## Numpy Arrays
- The fundmanetal NumPy data sctructure is an array: a memory-efficient container that provides fast numerical operations
- Unlike standard Python lists, a NumPy array cna only contain a single type of value (floats, ints, etc)
- Simplest type is a vector

```python=
a = np.array([1,2,3,5])
a
a.dtype
a.shape
```
```
array([1,2,3,5])
dtype('int64')
(4,)
```

### Basic Numerical Operations
- We can apply standard numerical operations to arrays using scalars (numbers). The operations are applied entry-wise - i.e. applied seperately to every entry in the array
- The operations are much faster than if run in pure Python on a standard list structure

```python=
c = np.array([1,2,3,4])
c*10
```
```
array([10,20,30,40])
```

### Accessing Values in 1D arrays
- We can access entries in 1-dimentional array using the same position-based notation as standard Python lists
- Can perform slicing ```array[0:5]```
- Slicing creates a "view" on the original array, not a copy
    - If you make changes, it'll affect the original array

### Multidimensional Array
- An array can have > 1 dimension. A 2-dimensional array can be viewed as a matrix, with rows and columns. It has these properties: 
    - Rank of array: Number of dimensions it has
    - Shape of array: A tuple of integers giving the lenght of the array in each dimension
    - Size of array: Total number of entries it contains
> Higher Dimensions

- As well as creating 1-dimensional and 2-dimensional arrays, wecan also create arrays with > 2 dimensions
- Axes are defined for arrays with more tha one dimension - e.g. a 2-dimensional array has two corresponding axes

### Array Creation Functions

- We can create 2D arrays from a list of Python lists
- Note: Make sure to include outer [] brackets!

```python=
d = np.array([[0,4,3],[9,8,6]])
print(d)
```

```
[[0 4 3]
 [9 8 6]]
```

- Rather than using python lists, a variety of functions ar eavailable for conveniently creating and populating arrays
- Using the `zeros()` function to create an array full of zeros with required shape

```python=
np.zeros(4)
```
```
array([0., 0., 0., 0.])
```
> Similarly, there's a function called `ones()`

- We can create an array corresponding to a sequence using the `arrange()` function.
- We can also specify a step size for the values. The default step is 1.
- The range and step sizes do not have to be integers. We cna also specify floats
- The `linespace()` function creates an array with a specified number of evenly-space dsamples in a given range

```python=
y = np.linespace(1, 10, 4)
print(y)
```

```
array([1,4,7,10])
```

### Array Shape Maniuplation
- The previous functions all created 1D arrays. What if we want to create multidimensional arrays?
- We can change array shape. The origiinal values are copied to a new array with the specified shape.
> `reshape(5,3)` // creates a 5 hight 3 length array
> `reshape()` needs the same area array of the previous..

### Acesssing Multidimensional Arrays
- To access a value in a 1D array, specify the position [i] counting from 0, just like a Python list
- We can also use this notation to change the values in an existing array
>
- When working with arrays with more than one dimension, use the notation [i,j], where the position in each dimension is separated by commas.
- Axis 0 refers to the rows, Axis 1 refers to the columns 

### Slicing Multidimensional Arrays
- For multidimensional arrays, we specify the slices for each dimension, separated by commas - e.g. for 2D [i:j, p:q]

### Iterating Over Arrays
- Generally, we want to avoid iterating over the individual entries of arrays as it is extremely slow.
- NumPy arrays are designed to be use dfor vectorised operations i.e. applying one operation to every entry in an array at once
- Sometimes it might be unavoidable. We can use a for loop..
- It is better to apply for an operation to all entries in an array whenever possible, unlesss running time does not matter

### Numerical Operations
- We can run batch operations on multidimensional arrays without for loops. These operations createa a new copy of the original array

### Comparison Operations
- We can use standard boolean expressions in batch to all entries in an array. The result is a new boolean array of the same shape.
```python=
d = np.array([5,10])
d > 5
```
```
array([false, true])
```

### Basic Statistics
- NumPy arrays also have basic descriptive statistics functions, `sum()`, `min()`, `max()`, `mean()`, `std()`

## Saving NumPy Data
- The `np.savetxt()` function cna be used to save an array to a text file. The default separator/delimiter is a space
```python=
np.savetxt("out1.txt", m)
```
- We can also add extra arguments to control the delimiter and number string format

## Loading NumPy Data
- The `np.loadtxt()` function can be used to read data from a text file and create a multidimensional NumPy array from the data. Each line is a row, and should contain the same number of values. By default values are separated by spaces. 
- We can also load files with other separators, by specifying the delimiter argument

## Using Matplotlib with NumPy
- Matplotlib can be used in conjunction with NumPy arrays to visualise numeric data
- For 2D NumPy arrays, a common type of visualisation is a color plot, which can be produced using plot.pcolor()

## Pandas vs NumPy
- NumPy is primarily useful for working with arrays. Highly optimised for efficient operations on numeric arrays. 
- Pandas provides higher level daa maniuplation tools built on top of NumPy arrays, along with more semantics (e.g. indexes).
- Some operations are not as efficient, but Pnadas provides some additional functionality - e.g dictionary-style access via row or column index to tabular data
- Since Pandas is built on top of NumPy, we can easily convert values between a NumPy array and a Pandas Series 

### Arrays

- Since NuMpy arrays do not have row or column indicies, we many need to speciy these if we convert an array to a Data Frame 
