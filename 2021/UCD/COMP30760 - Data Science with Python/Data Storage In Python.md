###### tags: `COMP30760 - Data Science with Python`

# Data Storage in Python

> Storing data for later use! Woah! Amazing! 
> Storing/Sharing data

## Data serialisation
- Data serialisation: Process of flattening complex data structures in a programming language, into a format that can be easily stored, transferred, or shared with another program
- Analogous to a "saved game" in a video game - we save the current state, so that we can restore it at a later time
- two common approached for serialisation in Python are JSON and Pickle
- In iether case, serialisation typically invovles transforming the original values into an approprioate format

## JSON serialization
- As we have seen, the json module provides a way of converting python objects int Javascript Object Notation format, which can be stored and shared
- We can use `json.dump()` to directly serialise values to a JSON file
- Similarly, we can use `json.load()` function to directly deserialise values from a JSON file stored on disk
>
- Advantages of using JSOn for serialation
    - Based on an open standard for data interchange
    - Language agnostic. Can be read by many other languages and programs
    - Output is always text-based, can be inspected and verified by humans
- Disadvatages of JSON serialisation:
    - Does not support all Python data types (e.g. complex objects)
    - It can be slow to read/write large volumes of data
- If interoperability wit other languages/programs is not a requirement, there are other serialisation methods

## Pickle Serialization

- The built in pickle module is the main mechanism provided by Python for serialising data
- Pickle turns any Python data strucutre into a bytestream representation, which is easily stored. Then, pickle can be used to reconstruct the original data later

### Usage
- Simplest usage of Pickle invovles the `pickle.dump()` function, which can serialise any Python object to an oepn file
- Note that we need to open the file in binary format
>
- We then reconstruct the original dictionary by calling `pickle.load()`

## Using pickle with Pandas
- We often want to serialise a Pandas Data Frame so that we ca use it later
- We can easily serialise this Data Frame, using the Pndas wrapper for Pickle, via the `to_pickle()` function
- Then we can load it back later using the `pd.read_pickle()` function
- The version we have read is an exact copy of the original data frame

## Pickle Summary
- Summary of serialising/deserialising data with pickle:
```python=
import pickle
cities = ["Philly", "Dublin"]
data = [cities]
fout = open("serial.pk1")
pickle.dump(data, fout)
fout.close()
```

## Reminder: Relational Databases
- Rather than using serialisation, we will often need to read and write data using traditional relational databases, via a Structured Query Langage (SQL) interface
- Recall, the central components of relational databaes are fields, records, and tables

## SQLite
- SQLite is a relational DB management system, implemented as a C library
- Unlike many other DB systems, SQLite is not a client-server engine, but is embedded into the end program (e.g. Firefox, various mobile apps)
- Data is essentially stored in a local file, whihc is manipulate dby fuctions of the C library that implements SQLite
- SQLite is reliable, full-featured, and implements the SQL Standard
- SQLIte is not suitable for large-scale data storage and/or collaborative data access. But useful for local data storage and desktop or mobile applications

## Using SQLite with Python
- The sqlite3 module in the Python Standard Library provides an easy interface to SQLite databases. No server processes or external configuration is required
- Creating a new SQLite database is as simple as creating a connection using sqlite3
- A new database file will be created automatically the first time we try to connect to a databaes
- The next step is to instantiate a cursor object, which is used to execute SQL 

## SQLite - Inserting Data
- We can populate the table with SQL INSERT statements
- Normally we do this by creating a SQL string iwth placeholders for each field, indicated by a ? character
- We actually insert the data by calling the cursor `execute()` function, specifying the SQL string, and a tuple of values that wil fill the placeholders

## SQLite - Querying Data
- Now that we have inserted data in the table, we can use `execute()` to run SQL SELECT queries
- We could select al the data from a table, or from certain field,s and then iterate over the rows in the result set, by calling the cursor `fetchall()` function

## SQLite and Pandas
- Pandas provides functionlity that makes it easy to transfer data between Data Frames and SQL Databases
- For example, Pandas allows us to write rows stored in Data frame using the `to_sql()` function
- We do not need to create the table structure or insert the values, Pandas does this for us
- Step 1: Populate a Pandas Data Frame from a CSV file
- Step 2: Open a connection to a new SQLite file
> cont
- We cna also go to the results of a SQLite database query to a new Pandas Data Frame
- Firstly, we connect to an existing SQLite database file
- We can then redirect the results of a SELECT query to a new Data Frame, via the function `pd.read_sql_query()`
- Pandas automatically creates  adata frame with the same structure as the database table, containing rows corresponding to the matching rows in the table



