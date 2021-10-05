---
tags: COMP30760 - Data Science with Python
---

# Lect 1, General Python Information

## General notes


### Python typing:

- Python uses a *Dynamic Typing* model for variables
    - Variables do not need to be declared in advance
    - Variables do not have a type associated with them
- Python uses a ***Strong** dynamic typing*
    - Applying operations to incompatible types is not permitted
    - The programmer may need to remember the type of the variable used

### String formatting

- In python, we can contactinat emultiple variables of different types into a single string, using the % operator.

```python=
"<format string>" % (<var1>, <var2>, ... <varN>)
"%s was born in %s in %d" % ("John", "Philadelphia", "1984")
```

- %d = integer
- %f = Floating point
- %.Nf = Float (N Decimal places
- %s = String (or any value)
- %% = "%" Symbol
- \t = tab character
- \n = newline character

```python=
s2 = "%f" => %.0f or %.4f" % (y, y, y)
```

### Working with files in Python

#### Opening/Reading files:

- File are special types of variables in Python, which are created using the open() function. Remember to close() the file when you are finished
- **Reading Files:** After Opening a file to read, you ca use severa functions ot access plain-text data:
    - read() -> Read the full file
    - readline() -> read a full line from a file
    - readlines -> read all lines from a file into a list

```python=
f = open("test.txt", "r") #r means read
lines = f.readlines()
f.close()
for line in lines:
    line = line.strip() #need to strip line endings
    print(line)
```

#### Writing files:

- **Writing Files**: After opening a file to write, use the write() function to output strings to the file

```python=
names = ["mark","jake","scott","yosra"]
fout = open("modified.txt", "w") #w is for write
for line in fin.readlines():
    fout.write("Copy: ")
    fout.write(line)
fin.close()
fout.close()
```

```
A
B
C
D
E
```

Turns into..

```
Copy: A
Copy: B
Copy: C
Copy: D
Copy: E
```

### Exception Handling

- By default, an exception will terminate a script or notebook
- We can handle errors in a structured way by "catching" exceptions. we plan in advance for errors that might occur:

```python=
try:
    <code>
except:
    <error handling>
```

```python=
try:
    <block of code>
except<errorType>
    <handle error type>
```

- Code will still continue after a try/except

### More complex exception handling

```python=
try:
    x = int(some_string)
except ValueError:
    print("Conversion Error")
finally:
    print("will always run")

```

### Python Modules
> import module
```python=
import math
import sys, os
```
> import specific part from module
```python=
from sys import exit
from math import pi, e
```
> import everything
```python=
from sys import *
from math import *
```
> module prefix...
```python=
import math
x = math.sqrt(9)
```

```python=
from math import sqrt, log
x = sqrt(9)
y = log(2)
print(x+y)
```

> alias names

```python=
import pandas as pd
import numpy as np
```

```dir()``` function will list all functions associated with import

## Specific functions

## (psudo)random number generation

```python=
import random
for i in range(4):
    y = random.random()
    print(y)
```

```
0.094803248324932084
0.742838948847347474
0.483482843284848484
0.217305932839857090
```
> seeding
```python=
random.seed(1000)
```

> ranges

```python=
import random
for i in range(4):
    y = random.randint(10, 20)
    print(y)
```

```
20
14
20
15
```

random.choice chooses from array

### split()

```python=
names = "john;alex;anna"
names.split(";")
```
```
['john', 'alex', 'anna']
```

### str()

> Will turn anything into a string

```python=
str(27)
```
```
'27'
```

