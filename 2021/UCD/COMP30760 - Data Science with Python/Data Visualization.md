###### tags: `COMP30760 - Data Science with Python`

# Data Visualization

## Visualization iwth Matplotlib
- data visualization is a key part of the exploratory data analysis process try to figure out what the story the data has to tell
- *Matplotlib*: the standard python plotting library. Provides a variety of plot types. Installed by default in the anaconda distribution
- Matplotlib supports the customization of plot appearance. We can control the defaults of almost every property: figure size, colors, etc

## Figures and plots
- the main visualizatio area in Matplotlib is called a figure. It can contain one or more plots
- Each `Matplotlib` function makes some change to a figure
- States are preserved across function calls, so that it keeps track of things like the current figure and plotting area

## Matplotlib Line Plot
```python=
data = [1,2,3,4,5]
```
- a simgple line plot can be used to show the values in a standard python list. The values in the list are plotted on the y-axis

## Matplotlib Scatter plots

- Matplotlib ssumes the values are a sequence and automaticall assigns values (0,1,2,...) to the x axis
>
- We can also specify values for the x and y axis:
```python=
x = [1,2,3,4,5]
y = [0,5,3,2,5]
```

```python=
plt.figure()
plt.plot(x,y,color='green',marker='o')
plt.title("A cool title")
plt.show()
```

- Matplotlib plots can be customized in many different ways. For full documentation see: 

## Matplotlib Bar Charts
- We could represent the same data using a vertical bar chart by calling plot.bar() function:
- We can alternatively create a horizontla bar chart by using plt.barh() function

## Plotting with Pandas
- Pandas provides plotting functionlity that uses matplotlib under the hood, but a simpler interface based around series and data frames using `plot()` The default output is a line plot

```python=
df["IPad"].plot(figsize=(11,5), linewidth=2, color="darkgreen")
plt.xlabel("Date", fontsize=14)
plot.ylabel("Unit Sales Per Month", fontsize=14)
```

- if a data frane cibtaubs multiple numeric columns, we can easily plot these are seperate stuff
- We ca use a scattar plot to visualize the relationship between two columns in a Data frame

### Bar plot with Pandas
- A numeric column in a data frame can be plotted using a bar chart
- We can alternatively generate a horizontal bar chart via plot(kind="barh")
- We can plot mulitple bars, each corresponding to a different column of a Daa Frame, also via plot(kind="bar")

## Histograms
- We often want to explore the distribution for a numeric variable i.e. the set of all values that it takes
- We visualize this type of distribution using a histogram. This is a plot which divides the balues taken by a variable into bins, and counts the number of values faling into each bin

## Histograms in Pandas
- In Pandas we can use a single function hist() to calculate the frequency counts for a series and display a histogram
- The key input argumne tis the number `bins

```python=
values = []
for i in range(1000):
    values.append(random.random())
s = pd.Series(values)
```
## Other python visualization libraries:
- Seaborn
- Altair
- Bokeh
- Plot.ly
