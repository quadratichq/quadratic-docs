---
description: Return the data from your Python code to the spreadsheet.
---

# Return data to the sheet

Quadratic is built to seamlessly integrate Python to the spreadsheet. This means being able to manipulate data in code and very simply output that data into the sheet.&#x20;

By default, the last line of code is output to the spreadsheet. This should be one of the five basic types:&#x20;

1. [Single value](return-data-to-the-sheet.md#id-1.-single-value): for displaying the single number result of a computation&#x20;
2. [List of values:](return-data-to-the-sheet.md#id-2.-list-of-values) for displaying a list of values from a computation
3. [DataFrame:](return-data-to-the-sheet.md#id-3.-dataframe) for displaying the workhorse data type of Quadratic
4. [Chart:](return-data-to-the-sheet.md#id-4.-charts) for displaying Plotly charts in Quadratic
5. [Function outputs:](return-data-to-the-sheet.md#returning-function-outputs-to-the-sheet) return the results of functions to the sheet

All code outputs by default are given names that can be referenced, regardless of their return type.&#x20;

{% hint style="info" %}
You can expect to primarily use DataFrames as Quadratic is heavily built around Pandas DataFrames due to widespread Pandas adoption in almost all data science communities!
{% endhint %}

## 1. Single Value

Note the simplest possible example, where we set `x = 5` and then return `x` to the spreadsheet by placing `x` in the last line of code.

```python
# create variable 
x = 5 

# last line of code gets returned to the sheet, so x of value 5 gets returned
x
```

<figure><img src="../.gitbook/assets/CleanShot 2025-02-28 at 12.06.12@2x.png" alt=""><figcaption></figcaption></figure>

## 2. List of values&#x20;

Lists can be returned directly to the sheet. They'll be returned as tables with default column headings. You can edit or remove those headers in the table menu. &#x20;

<pre class="language-python"><code class="lang-python"><strong># create a list that has the numbers 1 through 5 
</strong><strong>my_list = [1, 2, 3, 4, 5]
</strong>
# returns the list to the spreadsheet 
my_list
</code></pre>

<figure><img src="../.gitbook/assets/CleanShot 2025-02-28 at 12.07.12@2x.png" alt=""><figcaption></figcaption></figure>

## 3. DataFrame

You can return your DataFrames directly to the sheet by putting the DataFrame's variable name as the last line of code. DataFrames are returned to the sheet as Tables. The DataFrame's column names will be returned to the sheet as table headers.&#x20;

```python
# import pandas 
import pandas as pd
 
# create some sample data 
data = [['tom', 30], ['nick', 19], ['julie', 42]]
 
# Create the DataFrame
df = pd.DataFrame(data, columns=['Name', 'Age'])
 
# return DataFrame to the sheet
df
```

<figure><img src="../.gitbook/assets/CleanShot 2025-02-28 at 12.07.44@2x.png" alt=""><figcaption></figcaption></figure>

Note that if your DataFrame has an index it will not be returned to the sheet. If you want to return the index to the sheet use the following code:

<pre class="language-python"><code class="lang-python"><strong># use reset_index() method where df is the dataframe name
</strong><strong>df.reset_index()
</strong></code></pre>

An example of when this is necessary is any time you use the describe() method in Pandas. This creates an index so you'll need to use reset\_index() if you want to correctly display the index in the sheet when you return the DataFrame.&#x20;

## 4. Charts

Build your chart and return it to the spreadsheet by using the `fig` variable name or `.show()`

```python
# import plotly
import plotly.express as px

# replace this df with your data
df = px.data.gapminder().query("country=='Canada'")

# create your chart type, for more chart types: https://plotly.com/python/
fig = px.line(df, x="year", y="lifeExp", title='Life expectancy in Canada')

# display chart, alternatively can just put fig without the .show()
fig.show()
```

<figure><img src="../.gitbook/assets/CleanShot 2025-02-28 at 12.08.54@2x.png" alt=""><figcaption></figcaption></figure>

## 5. Function outputs

You cannot use the `return` keyword to return data to the sheet, as that keyword only works inside of Python functions. Here is an example of using a Python function to return data to the sheet.&#x20;

```python
def do_some_math(x): 
    return x+1

# returns the result of do_some_math(), which in this case is 6 
do_some_math(5)
```

<figure><img src="../.gitbook/assets/CleanShot 2025-02-28 at 12.16.50@2x.png" alt=""><figcaption></figcaption></figure>

**Note:** Quadratic returns can only support a single variable being returned. For example, if I want to return a list I must return a variable that is a single list. I can not try to return a list by attempting to return multiple variables, e.g. I can not try `x, y` as a return statement. One must combine x and y into a single variable and return that single variable.
