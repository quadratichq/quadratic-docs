# SQL - getting started

Use SQL to create live connections from your spreadsheets to your databases.&#x20;

Once established, you have a live connection that can be rerun, refreshed, read from, and written to your SQL database.&#x20;

{% hint style="warning" %}
You can both read and write to your databases from Quadratic.&#x20;
{% endhint %}

### Create a connection

Create an SQL connection by pressing `/` inside a cell. From here, you can access, add, or edit connections. Here are some helpful links to get started, or follow the [quick start guide](sql-getting-started.md#quick-start) below.&#x20;

You can also create a connection from the **Dashboard** > **Connections** under the **Team** menu.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f418">🐘</span> Connect your PostgreSQL database -></td><td></td><td></td><td><a href="postgresql.md">postgresql.md</a></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f42c">🐬</span> Connect your MySQL database -> </td><td></td><td></td><td><a href="mysql.md">mysql.md</a></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f570">🕰️</span> Request a data connection -></td><td></td><td></td><td><a href="request-a-connection.md">request-a-connection.md</a></td></tr></tbody></table>

## Quick start

### Create a connection

### Step 1: press `/`

You can create data connections from either your spreadsheets or team's dashboard. From your sheet, press `/` to open the code selection menu. You'll see both your existing connections and the prompt to manage your connections (create, edit, delete). To get started with creating a connection, choose the **Manage connections** option.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-07-17 at 14.03.17@2x.png" alt="" width="375"><figcaption></figcaption></figure>

### Step 2: pick the connection type

With the connection management screen open, you can edit an existing connection or create a new one. To create a new connection, select the connection type you want to create.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2024-07-24 at 12.34.54 PM.png" alt="SQL connection type"><figcaption><p>Select connection type screen</p></figcaption></figure>

### Step 3: follow the instructions for creating your connection

<figure><img src="../.gitbook/assets/Screenshot 2024-07-24 at 12.37.17 PM.png" alt=""><figcaption><p>Create connection screen</p></figcaption></figure>

You can also follow this same create connection process from your team's dashboard under the connections section.&#x20;

## Use connection

### Step 1: use your connection

Once your connection has been made you can use your connection directly in the sheet. Open the code cell selection menu with `/` and select your database from the list - in this example it's named **Quadratic Postgres**.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-07-17 at 13.49.12@2x.png" alt="" width="375"><figcaption></figcaption></figure>

You can now query your database from your newly opened SQL code editor. You can view the schema or open the AI assistant in the bottom.

The results of your SQL queries are returned to the sheet, with column 0, row 0 anchored to the cell location. &#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-07-17 at 14.28.45@2x (1).png" alt=""><figcaption></figcaption></figure>

You can read the data returned from queries in Python, Formulas, Javascript, etc.&#x20;

Read and manipulate your data returned from SQL to summarize results, create charts, or anything else you might want to use your data for!&#x20;

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f522">🔢</span> Learn about the SQL AI assistant -></td><td></td><td></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f513">🔓</span> Learn about permissions and security -> </td><td></td><td></td></tr></tbody></table>

## Helpful queries

If you need help generating queries, we recommend first [trying the AI assistant](sql-ai-assistant.md) in your Quadratic code editor - its outputs are very helpful with writing everything from the simplest to most complex SQL queries.&#x20;

### Read data into the spreadsheet <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

#### Query all data from single table into the spreadsheet

<pre class="language-sql"><code class="lang-sql"><strong>SELECT * FROM table_name
</strong></code></pre>

#### Query a limited selection (100 rows) from single table into spreadsheet&#x20;

```sql
SELECT * FROM table_name 
LIMIT 100
```

#### Query specific columns from single table into the spreadsheet&#x20;

```sql
SELECT column_name1, column_name2 
FROM table_name 
LIMIT 100
```

#### Query all unique values in a column&#x20;

```sql
SELECT DISTINCT column_name1 
FROM table_name 
LIMIT 100
```

#### Query data conditionally

```sql
-- selects 3 specific columns from a table where column1 equals some value
SELECT column1, column2, column3
FROM table_name
WHERE column1 = 'some_value';
```

```sql
-- selects 3 specific columns from a table where column1 equals some value and column2 equals some value 
SELECT column1, column2, column3
FROM table_name
WHERE column1 = 'some_value' AND column2 = 5;
```

#### Extra considerations

You cannot do two queries at once in SQL in Quadratic. For example, you can not create a table and then query that table in the same SQL query.&#x20;

There are some slight differences between SQL syntax across databases.&#x20;

* In Postgres it is best practice use quotes around table names and column names.&#x20;
* In MySQL it is best practice to use backticks around table names and column names.&#x20;
* In MS SQL Server it is best practice to use double quotes around table names and column names.&#x20;

Stuck? The [AI assistant in your code editor](sql-ai-assistant.md) is ready and waiting to help with your queries.&#x20;
