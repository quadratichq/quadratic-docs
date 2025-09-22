---
description: Reference cells from Python.
---

# Reference cells

In Quadratic, [reference tables](reference-cells.md#block-9871b7ac3fa341da856503066f6f8e8c) and named outputs from Python for simplest references, [reference individual cells](reference-cells.md#block-9871b7ac3fa341da856503066f6f8e8c) from Python for single values or [reference a range of cells](reference-cells.md#block-aea52dff303745f6b08db8ab3b24c4f6) for multiple values.&#x20;

## Referencing tables (and named outputs)  <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

Much of Quadratic's data is formatted in Data Tables for ease of use. Data Tables also make references more straightforward. To reference a table you can use `q.cells` which will bring the table into a DataFrame.&#x20;

```python
# Note: uses same table reference style as Formulas
# References entire table, including headers 
df = q.cells("Table1[#ALL]")

# Reads the values in Table1 and places them into variable df
# Note: this only retrieves the values, not the column names/headers
df_values = q.cells("Table1")

# Get a single column out of table into DataFrame
# Note: this only retrieves the column's data, not the header
df_column = q.cells("Table1[column_name]")

# Creates an empty DataFrame with just the headers as column names of the table referenced
df_headers = q.cells("Table1[#HEADERS]")

# Reference a range of columns from a table
df_columns = q.cells("Table1[[Column 1:Column 3]]")
```

All code outputs are also named and in tables by default; they can be referenced in the same fashion, using their names. Wherever possible you are encouraged to perform references using tables for simplest possible user experience.&#x20;

## Referencing individual cells <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

To reference an individual cell, use the global function `q.cells` which returns the cell value.

<pre class="language-python"><code class="lang-python"><strong># NOTE: uses the same A1 notation as Formulas
</strong><strong># Reads the value in cell A1 and places in variable x 
</strong><strong>x = q.cells("A1")
</strong></code></pre>

You can reference cells and use them directly in a Pythonic fashion.&#x20;

```python
q.cells("A1") + q.cells("A2") # Adds the values in cells A1 and A2 
```

Any time cells dependent on other cells update, the dependent cell will also update. This means your code will execute in one cell if it is dependent on another. This is the behavior you want in almost all situations, including user inputs in the sheet that cause calculation in a Python cell.&#x20;

## Referencing a range of cells <a href="#block-aea52dff303745f6b08db8ab3b24c4f6" id="block-aea52dff303745f6b08db8ab3b24c4f6"></a>

To reference a range of cells, use the same global function `q.cells()` which returns a [Pandas DataFrame](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.html).

<pre class="language-python"><code class="lang-python"><strong>q.cells("A1:A5") # Returns a 1x5 DataFrame spanning from A1 to A5
</strong><strong>
</strong><strong>q.cells("A1:C7") # Returns a 3x7 DataFrame spanning from A1 to C7
</strong><strong>
</strong><strong>q.cells("A") # Returns all values in column A into a single-column DataFrame
</strong><strong>
</strong><strong>q.cells("A:C") # Returns all values in columns A to C into a three-column DataFrame
</strong><strong>
</strong>q.cells("A5:A") # Returns all values in column A starting at A5 and going down

q.cells("A5:C") # Returns all values in column A to C, starting at A5 and going down

q.cells("A1:1") # Returns all values in row 1, starting at column A

q.cells("C5:5") # Returns all values in row 5, starting at column C
</code></pre>

If the first row of cells is a header, you should set `first_row_header` as an argument. This makes the first row of your DataFrame the column names, otherwise will default to integer column names as 0, 1, 2, 3, etc.

Use first\_row\_header when you have column names that you want as the header of the DataFrame. This should be used very commonly. You can tell when a column name should be a header when the column name describes the data below.&#x20;

```python
# first_row_header=True will be used any time the first row is the intended header for that data.
q.cells("A1:B9", first_row_header=True) # returns a 2x9 DataFrame with first rows as DataFrame headers
```

## Referencing another sheet

To reference another sheet's table, individual cells, or range of cells use the following:&#x20;

<pre class="language-python"><code class="lang-python"><strong># Use the sheet name as an argument for referencing range of cells 
</strong><strong>q.cells("'Sheet_name_here'!A1:C9")
</strong><strong>
</strong><strong># For individual cell reference 
</strong>q.cells("'Sheet_name_here'!A1")

# Since tables are global to a file, they can be referenced across sheets without defining sheet name
q.cells("Table1")
</code></pre>

## Unbounded references

### Unbounded column references

To reference all the data in a column or set of columns without defining the range, use the following syntax.&#x20;

Unbounded column references span from the row set (row 1 if not defined) to wherever the content in that column ends. Ranged references are always returned as DataFrames. Wherever gaps in data exist, `None` is filled in instead.

<pre class="language-python"><code class="lang-python"># references all values in the column from row 1 to the end of the content 
<strong>q.cells("A") # returns all the data in the column starting from row 1 to end of data 
</strong>
q.cells("A:D") # returns all the data in columns A to D starting from row 1 to end of data in longest column

q.cells("A5:A") # returns all values from A5 to the end of the content in column A 

q.cells("A5:C") # returns all values from A5 to end of content in C

q.cells("A:C", first_row_header=True) # same rules with first_row_header apply 

q.cells("'Sheet2'!A:C", first_row_header=True) # same rules to reference in other sheets apply
</code></pre>

### Unbounded row references

To reference all the data in a row or set of rows without defining the range, use the following syntax.&#x20;

Row references span from the row set to wherever the content in that row ends.&#x20;

```python
# Returns all values in Row 1
q.cells("1") 

# Returns all values in rows 1 to 3 
q.cells("1:3") 

# Returns all values in Row 1 starting at column A
q.cells("A1:1")

# Returns all values in Row 1 starting at column C
q.cells("C1:1")

# Returns all values in Row 3 starting at column A
q.cells("A3:3")

# Returns all values in Row 3 starting at column C 
q.cells("C3:3")
```

## Relative vs absolute references

By default when you copy paste a reference it will update the row reference unless you use `$` notation in your references.&#x20;

```python
# Copy pasting this one row down will change reference to A2
q.cells("A1")

# Copy pasting this one row down will keep reference as A1
q.cells("A$1")

# Example using ranges - row references will not change
q.cells("A$1:B$20")

# Only A reference will change when copied down
q.cells("A1:B$20")
```
