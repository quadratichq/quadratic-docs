---
description: Perform novel analysis on your data.
---

# Manipulate data

Manipulating data in Quadratic is easier than ever as you can view your changes in the sheet in real-time. Here is a non-exhaustive list of ways to manipulate your data in Quadratic:&#x20;

1. [Find correlations ](manipulate-data.md#1.-find-correlations)
2. [Basic stats - max, min, average, selections, etc.](manipulate-data.md#2.-basic-stats-max-min-average-selections-etc.)
3. [DataFrame math ](manipulate-data.md#3.-dataframe-math)
4. [Data selections ](manipulate-data.md#4.-data-selections)

## 1. Find correlations

```python
# Get the correlation and show the value in the sheet
data['col1'].corr(data['col2'], method='pearson')

# possible methods: pearson, kendall, spearman 
```

## 2. Basic stats - max, min, mean, selections, etc.

Reference: [https://pandas.pydata.org/docs/getting\_started/intro\_tutorials/06\_calculate\_statistics.html](https://pandas.pydata.org/docs/getting_started/intro_tutorials/06_calculate_statistics.html)

```python
# Get the max value of a column
df["col1"].max()
```

```python
# Get the min value of a column
df["col1"].min()
```

```python
# Get the mean value of a column
df["col1"].mean()
```

```python
# Get the median value of a column
df["col1"].median()
```

```python
# Get the skew for all columns
df.skew()
```

```python
# Count the values in a column
df["col1"].value_counts()
```

```python
# Get the summary of a column
df["col1"].describe()
```

## 3. DataFrame math

Do math on data in the DataFrame. Alternatively, use formulas in the sheet on the values.&#x20;

```python
# Add, subtract, multiply, divide, etc., will all work on all values in a column
df['col1'] + 1
df['col1'] - 1
df['col1'] * 2
df['col1'] / 2 
```

```python
# Do any arbitrary math column-wise with the above or do DataFrame-wise via
df + 1 
```

## 4. Data selections

Alternatively, cut/copy/paste specific values in the sheet.&#x20;

```python
# get a column 
df['col1'] 
```

```python
# get multiple columns 
df[['col1', 'col2']] 
```
