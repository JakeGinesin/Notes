###### tags: `COMP30760 - Data Science with Python`

# Lect 4, Data Preparation (Part 2) & Data Formats

## Missing Values

- Many real datasets have mising values, either becuase the data existed but was not collected, or because it never existed. In Pandas missing data can be represented in 2 ways:
    - NaN (Not a Number): Indicating a missing floating point value
    - None: A standard Python null value for anoy other type of value
- we can use the functions  `isnull()` and `notnull()` to identify and count missing and non-missing values

## Handling Missing Values
- There are two general approaches to handling missing values. The appropriate approach depends on the data and the task at hand
    - 1. **Filter out missing data**
        - Filter by example: delete any row containing missing values from the dataset
        - Filter by feature: Delete any column containing missing values from the dataset
    - 2. **Fill in missing data**
        - Fill with a global constant: Replace all missing values in the dataset with a fixed value
        - Fill with mean/median: Replace missing values based on the row or column mean/median from existing data
        - Prediction: Trying to predict the data based on other data

## Filtering out Missing Data
- Filtering eliminates the presence of rows and/or columns in a Data Frame which contain one or more missing values
- However, this can also remove potentially useful data
- We can call `drop()` to remove one or more rows from a Data Frame, by specifying a list of row indexes. Not this creates a copy o the Original Data Frame
- Instead of manually specifying rows, we can call `dropna()` to remove all rows containing missing values
- We can also use `drop()` and `dropna()` to remove columns containing missing values from a Data Frame by specifying `axis=1'
- We could fill in all missing values in a Data Frame with the same value using `fillna()`. This creates a copy of the Data Frame
    - `df2 = df.fillna(0) # replace every missing value with 0`
- A more senible approach would be to fill in missing values using a column's mean value

## Data Formats: CSV
- Data is generated in different domains (e.g. financ,e healthcare) and stored in many different formats
- **CSV ("Comma Separated Values")**: a file format often used to exchange tabular data between different applications (e.g. Excel)
- Essentially a plain text file where values are split by a comma
- Alternatively can use a different separator
- Generally includes a header line with column names. The first value on each line is also sometimes a unique identifier in that row

### Reading CSV
- A simple wa to read CSV files is to use `read_csv()` in Pandas to load data into a Data Frame
- if the CSV contains a unique identifier column, we can specify the `index_col` parameter to se tthis as the row index

## Data Formats: JSON
- **JSON (Javascript Object Notation)**: a lightweight format which is becoming increasingly popular for online data exchange. Based originally on the Javascript language and relatively easy for humans to read and write
- Json Files are built from two different structures:
    - **Object**: A collection of name/value pairs - like a python dictionary
    - **Array**: A list of values separated by commas, like  a python list. Begins and ends with brackets "[]"
>
- White space does *not* matter in JSOn, it only makes the data more readable for humans

### Objects
```
{"firstname": "Jake", "age": "19"}
```
```
{"Ford", "BMW","Fiat"}
```

> Can mix objects and arrays

```
{"Codes": ["Pog", "Pog2", "Pog3"]}
```

### Using JSON in Python

- Json is a language-agnostic. many parsers are available
- The built in module `json` provides an easy way to encode and decode data in JSOn in Pthon. Two main functions:
    - json.dumps(): Turn a python data strcutre into a JSON string
    - json.loads(): Load a pthon data strcuture from a JSON string

>
- To translate a string continaing JSOn data into a Python value, pass it to the `json.loads()` function
- Python automatically converts JSON values into variables of the appropriate type

## Data Formats: XML

- XML: A markup language used to describe data in a strctured way using tags. Tags are not predefined, but are user defined. Many schemas exist that recommend standardised usage of tags.
- Tags must be opened <tag> and closed </tag>
- Tags cna contain values as plain text and other nested tags

```
<note>
    <to>Alice</to>
    <from>Jake</from>
    <subject>How are you?</subject>
    <body>Just wondering how you're doing!</body>
</note>
```

- Tags can also have zero or mroe name/value attribute pairs, whch add extra information to a tag

### XML Hierarchy

- XML i an inherently hierarchal data format, and the most natural way to represent it is iwth a tree with nodes at different levels
- The document itself is the root node of the tree. Other nodes are child nodes. If they contain nodes themselves, they are parent nodes. The lowest level of the tree contains leaf nodes. 

### XML Access

- Several Python built in modules for parsing XML data
- XML data is accessable by: `body.message.footer` (this is an example)

### XML represnts data

- HTML is also a markup language ismilar to XML. Key differences: 
    - XML describes data, HTML describes data and presents it
    - in practice HTML is usually badly written and invalid

## Web Scraping
- Web Scraping: A technique used to extract data from web sites using a tool that acts as a web browser
- **Basic Steps**
    - Data identification
    - Data collection
    - Data extraction
    - Data Cleaning
- The "Rules" of web scraping:
    - Check a site's terms and conditions before you scrape thier pages
    - Do not hammer a site with too many automatated requests
    - Sites often change their layout, so scrapers often break and need to be maintained
    - 

### Web Data Collection
- The Built-in python urlib.request module has functions which help in downloading content from HTTP URLs using minimal code
- There are many ways to parse HTML pages in Python. The third-party *Beautiful Soup* package is useful for working with badly written HTML pages

### Web APIs
- Instead of manually scraping HTML data, some web sites provide a convenient "official" way of retrieving their data
- *Web Application Programming Interface (API)*: A web service consisting of a set of HTTP request messages with a definition of the expected structure of the response
- In contrast to a static website or a fixed dataset (e.g. a single CSV file hosted online), an API can accept a query or a call for particular data and respond dynamically with the required result
- APIs can use different data formates to encode calls and responses. Sometimes this can be plain text, but more commonly JSON or XML
    - Many APIs have rate limits. Can only make limited number of calls from a given IP address/account during a fixed period of time
    - Some APIs require authentifation - i.e. first need to register a user account, and retrieve an authentication token/passwor
