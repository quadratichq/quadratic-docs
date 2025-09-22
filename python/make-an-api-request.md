---
description: Get the data you want, when you want it.
---

# Make an API request

API requests are made seamless in Quadratic by allowing you to use Python and then display the result of the request directly to the sheet.&#x20;

## Query API - GET request

Let's break our GET request down into a few different pieces.&#x20;

Import the basic requests library you're familiar with, query the API, and get the data into a Pandas DataFrame.&#x20;

<pre class="language-python"><code class="lang-python"><strong># Imports
</strong><strong>import requests
</strong>import pandas as pd

# Request
response = requests.get('your_API_url_here')

# JSON to DataFrame
df = pd.DataFrame(response.json())

# Display DataFrame in the sheet 
df
</code></pre>

## **Query API - POST request**

```python
import requests

# API url
url = 'your_API_url_here'
# API call body 
obj = {'somekey': 'somevalue'}

# create request 
x = requests.post(url, json = myobj)

# return the API response to the sheet
x.text
```

## **Going from CSV to DataFrame**&#x20;

Bringing your CSV to Quadratic is as simple as a drag and drop. Once your CSV is in the spreadsheet, reference the range of cells in Python to get your data into a DataFrame.&#x20;

You use the argument `first_row_header=True` to avoid the first row of your DataFrame being what is intended to be our header. Note that the output, in this case, is printed to the console since you already have your initial CSV in the sheet. After some manipulation of the data, perhaps you would want to display your new DataFrame. In that case, leave `df` as the last line of code.

In this case, the spreadsheet reflects `cells('A1:B161')` since we want the full span of data in both columns A and B spanning from rows 1 to 161.

```python
df = q.cells('A1:B161', first_row_header=True))
```
