# task30-Descriptive-Statistics.

## Description

Calculate and interpret the following descriptive statistics:

-   Mean
-   Median
-   Mode
-   Range
-   Variance
-   Standard deviation
-   Quartiles
-   Percentiles

## Objective

Build a foundation in the statistical concepts and techniques required
for data science.

## Tools and Libraries

-   Python
-   Pandas
-   NumPy
-   Jupyter Notebook

## Deliverables

1.  Descriptive statistics for at least three numerical variables.
2.  Calculations of central tendency and dispersion.
3.  A written interpretation of the results.

## Hints / Mini Guide

-   Use `describe()` in Pandas to generate a quick statistical summary.
-   Compare the mean and median to understand the distribution of the
    data.
-   Use quartiles to understand how the data is spread.
-   Consider using NumPy or Pandas functions to calculate individual
    statistics.

## Suggested Datasets

You can complete this task using any of these datasets:

-   Iris Dataset
-   Student Performance Dataset
-   Wine Quality Dataset

## Suggested Workflow

1.  Choose and load a dataset into a Pandas DataFrame.
2.  Inspect the dataset and identify at least three numerical columns.
3.  Check for missing or invalid values in the selected columns.
4.  Calculate mean, median, mode, and range for each selected variable.
5.  Calculate variance and standard deviation.
6.  Calculate quartiles and relevant percentiles.
7.  Use `describe()` to obtain a quick summary and compare it with your
    calculations.
8.  Explain what the results indicate about the centre and spread of
    each variable.

## Example Python Starter Code

``` python
import pandas as pd
import numpy as np

# Load your dataset (replace the file name with your dataset)
df = pd.read_csv("your_dataset.csv")

# Select at least three numerical columns
selected_columns = df.select_dtypes(include="number").columns[:3]
data = df[selected_columns]

# Quick descriptive summary
print(data.describe())

# Individual statistics
for column in data.columns:
    values = data[column].dropna()

    print(f"\n{column}")
    print("Mean:", values.mean())
    print("Median:", values.median())
    print("Mode:", values.mode().tolist())
    print("Range:", values.max() - values.min())
    print("Variance:", values.var())
    print("Standard deviation:", values.std())
    print("Quartiles:")
    print(values.quantile([0.25, 0.50, 0.75]))
    print("90th percentile:", values.quantile(0.90))
```

## Interpretation Guide

When writing your interpretation, consider:

-   **Mean:** The arithmetic average of the values.
-   **Median:** The middle value after sorting the data.
-   **Mode:** The most frequently occurring value or values.
-   **Range:** The difference between the maximum and minimum values.
-   **Variance:** A measure of how far values are spread around the
    mean.
-   **Standard deviation:** The typical spread of values around the
    mean, expressed in the original unit.
-   **Quartiles:** Values that divide sorted data into four equal parts.
-   **Percentiles:** Values below which a given percentage of
    observations fall.

Compare the mean and median. A noticeable difference may indicate that
the distribution is skewed or affected by unusually high or low values.
Use the standard deviation, range, and quartiles to describe the spread.
Interpret each statistic in the context of the dataset rather than
listing numbers alone.

## Interview Questions

Prepare to explain:

1.  What is descriptive statistics?
2.  What is the difference between mean and median?
3.  When is the median more useful than the mean?
4.  What is the difference between variance and standard deviation?
5.  What do the first, second, and third quartiles represent?
6.  What is a percentile?
7.  How can quartiles help identify the spread of a dataset?
8.  What information does Pandas `describe()` provide?
