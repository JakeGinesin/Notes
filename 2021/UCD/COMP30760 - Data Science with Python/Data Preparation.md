---
tags: COMP30760 - Data Science with Python
---

> No actual programming yet...

# Lect 3, Data Preparation

## Intro Points
 
 - Data in real world rarely arrives in a clean and homogeneous form
 - Typically, datasets tend to be incomplete, noisy, and inconsistent
 - Often, need to invest condideratble time and effort to address these issues before any sort of modeling occurs
 - **Up to 80% of typical data scientist projects consist of cleaning data,** while remaining 40% are for analysis

## Data Prep Steps

- The following tasks must be done in order to prep data:
    - **Data cleaning**: Fix erroneous feature values in the raw data
    - **Data selection**: Filter the full dataset to find a useful subset to work with, removing noisy cases
    - **Duplicate elimination**: remove duplicate cases
    - **Normalization**: Scale numeric values to conform to minimum and maximum values
    - **Handling missing values**: Filling in data, etc
    - **Feature Engineering**: Building specific tools
    - **Data integration**

## Pandas Package for Python

 - Manipulating and cleaning data can be slow and tedious. Python can partially simplify and automate this process
 - Pandas is an open source package providing high-performanc edata structures and analysis tools for python
 - It provides a python equiv of the data analysis and manipulation functionality in the R programming language

### What does Pandas offer?

 - Pandas offers two new data structures optimized for data analysis and manpiulation
     - **Data Frame**: Flexible two-dimensional, potentially heterogeneous tabular data structure
     - **Data Series**: a data structure for a single column of a data frame

### Pandas Series

- **Series**: One dimensional array capable of holding any data type
- The key difference between a series and a standard python list is that, as  well as having a numberic position, the elements in the array can have a custom name, or index of any type

#### Creating a Pandas Series:

> You can add certain indexes to arrays as well as the typical numerical ascending series..

```python=
s = pd.Series([5,6,10,20],["China", "America", "Ireland", "UK"])
print(s)
```
```
China          5
America        6
Ireland       10
UK            20
```

#### In pandas, you can use:

> Creation bit...
```python=
s = pd.Series([5,6,10,20],["China", "America", "Ireland", "UK"])
print(s)
```

> Slicing!

```python=
print(s[0:2])
```
```
China          5
America        6
```

> Specific Access!

```python=
print(s["China"])
print(s[0])
```
```
5
5
```

#### Filtering Data in Pandas

> Will create a new series

```python=
print(s[s>9])
```
```
Ireland       10
UK            20
```

#### Series Statistics

- .min()
- .max()
- .median()
- .std() //standard deviation
- .sum()
- .mean()
- .describe() //shows all the above

### Data Frames

#### Creating Data Frames

- An easy way to create a DataFrame is to pass the ```pd.DataFrame()``` function a dictionary of lists, where each list will be a column

```python=
countries = pd.DataFrame({"Country":["America", "China"]},
						 {"Population":["300 mil", "1.5 bil"]},
						 {"Average Age":["30", "40"]})
```

#### Data Frame Statistics

- Once we have loaded a Data Frame, the ```describe()``` function gives a useful summary table with statistics for each column
- We can also get individual stats from each column

#### Accessing Values in Data Frames

- Columns in a Data Frame can be accessed using the index name of the column to give a single series

```python=
countries["Population"]
```

```
America      300 mil
China        1.5 bil
```

- We can acess rows in a Data Frame in different ways.
	- We can access a single row by numeric position using ```iloc[]```
	- We can access a single row by index name using ```loc[]```

- We can vroom to it:

```python=
countries["China"]["Population"]
```
```
1.5 bil
```

> We can also do this with norma numerical values! i.e. ```countries[1][1]```


### Loading CSV Data
- The CSV ("Comma Separated Values") file format is often used to exhcnage tabular data between different applications (e.g. Excel)
- Essentially a plain text file
- We read a Data frame from a CSV file vi the ```read_csv()``` function. 
- The first line contains the column index names, each subsequent line will be a row in the frame

> Provide columns..

- We can also tel the ```read_csv()``` function to use one of the columns as the inex for rows in our data

### Sorting Data
- To sort a Seires by its values, use the ```sort_values()``` function. By default they are sorted in ascending order (i.e. smallest to largest)
	- Ascending by default... 
	- Can change this by doing: ```sort_values(ascending=False)```
- When sorting a data Frame, we can specify one or more columns as the sort keys using parameters
	- ```sortValues("Population")```

### Aggregating Data
- We can use the ```groupby()``` function to group data based on the values in a categorical column
- The result of a groupby object. Nothing has been computed yet, but the object can be used to apply different operations to each of the groups which result in a new Data Frame
- We could apply the same grouping approach for other colimns
- Note that, when we compute mean values, non-numeric columns are automatically dropped

