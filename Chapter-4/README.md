# Work with Multiple Time Series Data

## Description:

In the field of Data Science, it is common to work with multiple time series simultaneously.

In this jupyter notebook, we learnt how to plot multiple time series at once, and how to discover and describe relationships between multiple time series.

---
## Contents:
1. Importing the required libraries
2. Importing & Loading the dataset
    - Knowing the dataset
    - Importing the dataset
    - Loading the dataset
3. Data Manipulations
4. Plotting the data
    - Basic Line Chart
    - Area Chart
5. Enhancing Plots
    - Clarity is Key
    - Colormap Argument
    - Adding information to plots
    - Facet Plots
6. Correlation b/w variables
    - Compute correlations
    - Correlation Matrix
    - Computing correlation matrix with pandas
    - Heat Maps
    - Cluster Maps
7. Conclusion

---
## Data Info:
The dataset contains the amount of different types of meat produced in the USA between 1944 and 2012. [(data)](https://github.com/Ravjot03/Visualizing-Time-Series-Data-in-Python/blob/main/Chapter-4/ch4_meat.csv)

---
## Theoretical Concepts & Key Pointers:

### 1. Area Chart
**Area charts** are commonly used when dealing with multiple time series, and can be leveraged to represent cumulated totals. With the `pandas` library, we can simply leverage the `.plot.area()` method to produce an area chart.

### 2. Enhancing Plots
Plotting and visualizing data that contains multiple time series can be a challenging task. While the `pandas` library can still be leveraged to perform this task, there are a number of parameters that can be applied in order to optimize the readability of the graphs.

Now, we will discuss how multiple times series can be clearly displayed simultaneously in Python.

#### 2.1 Clarity is Key
When plotting multiple time series, matplotlib will iterate through its default color scheme until all columns in the DataFrame have been plotted. Therefore, the repetition of the default colors may make it difficult to distinguish some of the time series.

#### 2.2 Colormap Argument
To remedy this, the `.plot()` method has an additional argument called `colormap`.This argument allows us to assign a wide range of color palettes with varying contrasts and intensities. We can either define our own Matplotlib colormap, or use a string that matches a colormap registered with matplotlib.

Changing line colors with the color map argument.

### 3. Facet Plots
In order to overcome issues with visualizing datasets containing time series of different scales, we can leverage the `subplots` argument, which will plot each column of a DataFrame on a different subplot. In addition, the layout of our subplots can be specified using the `layout` keyword, which accepts two integers specifying the number of rows and columns to use. It is important to ensure that the total number of subplots is greater than or equal to the number of time series in our DataFrame. We can also specify if each subgraph should share the values of their x-axis and y-axis using the `sharex` and `sharey` arguments. Finally, we need to specify the total size of our graph (which will contain all subgraphs) using the `figsize` argument.

### 4. Correlation b/w variables
One of the most widely used methods to assess the similarities between a group of time series is by using the correlation coefficient. The correlation coefficient is a measure used to determine the strength or lack of relationship between two variables. The standard way to compute correlation coefficients is by using the Pearson's coefficient, which should be used when we think that the relationship between the variables of interest is linear. Otherwise, we can use the Kendall Tau or Spearman rank coefficient methods when the relationship between the variables of interest is thought to be non-linear.

#### 4.1 Compute Correlations
In Python, we can quickly compute the correlation coefficient between two variables by using the `pearsonr`, `spearmanr` or `kendalltau` functions in the `scipy.stats` module. All three of these correlation measures return both the correlation and p-value between the two variables.
