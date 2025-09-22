---
description: Get your data ready for analysis.
---

# Clean data

Cleaning data in Quadratic is more seamless than you may be used to, as your data is viewable in the sheet as you step through your DataFrame. Every change to your DataFrame can be reflected in the sheet in real-time. Some data cleaning steps you may be interested in taking (very much non-exhaustive!):&#x20;

1. [View select sections of your DataFrame in the sheet ](clean-data.md#1.-view-select-sections-of-your-dataframe-in-the-sheet)
2. [Drop specified columns](clean-data.md#2.-drop-specified-columns)
3. [Field-specific changes](clean-data.md#3.-field-specific-changes)
4. [Clean columns ](clean-data.md#4.-clean-columns)
5. [Delete select rows ](clean-data.md#5.-delete-select-rows)
6. [Delete empty rows](clean-data.md#6.-delete-empty-rows)
7. [Change data types](clean-data.md#7.-change-data-types)&#x20;
8. [Remove duplicates](clean-data.md#8.-remove-duplicates)&#x20;

## 1. View select sections of your DataFrame in the sheet

Assume DataFrame named `df`. With `df.head()` you can display the first x rows of your spreadsheet. With this as your last line the first x rows will display in the spreadsheet. You can do the same except with the last x rows via `df.tail()`

```python
# Display first five rows
df.head(5)

# Display last five rows
df.tail(5)
```

## 2. Drop specified columns

Deleting columns point and click can be done by highlighting the entire column and pressing `Delete`. Alternatively, do this programmatically with the code below.&#x20;

```python
# Assuming DataFrame df, pick the columns you want to drop
columns_to_drop = ['Average viewers', 'Followers']

df.drop(columns_to_drop, inplace=True, axis=1)
```

## 3. Field-specific changes

There are many ways to make field-specific changes, but this list will give you some ideas.&#x20;

<pre class="language-python"><code class="lang-python"><strong># Replace row 7 in column 'Duration' with the value of 45
</strong> df.loc[7, 'Duration'] = 45
</code></pre>

## 4. Clean columns

Going column by column to clean specific things is best done programmatically.&#x20;

```python
# Specify things to replace empty strings to prep drop 
df['col1'].replace(things_to_replace, what_to_replace_with, inplace=True)
```

## 5. Delete select rows

With the beauty of Quadratic, feel free to delete rows via point and click; in other cases, you may need to do this programmatically.&#x20;

```python
# Knowing your row, you can directly drop via
df.drop(x)

# Select a specific index, then drop that index
x = df[((df.Name == 'bob') &( df.Age == 25) & (df.Grade == 'A'))].index
df.drop(x)
```

## 6. Delete empty rows

Identifying empty rows should be intuitive in the spreadsheet via point-and-click; in other cases, you may need to do this programmatically.&#x20;

```python
# Replace empty strings to prep drop 
df['col1'].replace('', np.nan, inplace=True)

# Delete where specific columns are empty 
df.dropna(subset=['Tenant'], inplace=True)
```

## 7. Change data types

By default, Quadratic inputs will be read as strings by Python code. Manipulate these data types as you see fit in your DataFrame. &#x20;

```python
# Specify column(s) to change data type
df.astype({'col1': 'int', 'col2': 'float'}).dtypes

# Common types: float, int, datetime, string
```

## 8. Remove duplicates

Duplicates are likely best removed programmatically, not visually. Save some time with the code below.&#x20;

```python
# Drop duplicates across DataFrame
df.drop_duplicates()

# Drop duplicates on specific columns 
df.drop_duplicates(subset=['col1'])

# Drop duplicates; keep the last 
df.drop_duplicates(subset=['col1', 'col2'], keep='last')
```
