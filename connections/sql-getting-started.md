# SQL - getting started

## SQL - getting started

Use SQL to create live connections from your spreadsheets to your databases.

Once established, you have a live connection that can be rerun, refreshed, read from, and written to your SQL database.

{% hint style="warning" %}
You can both read and write to your databases from Quadratic.
{% endhint %}

#### Supported connections

**Databases**: PostgreSQL, MySQL, MS SQL Server, Snowflake, BigQuery, CockroachDB, MariaDB, Supabase, Neon

**SaaS & analytics** (synced connections): Mixpanel, Google Analytics, QuickBooks

**Financial institutions**: bank accounts, brokerages, and credit cards via Plaid

**Anything with a REST API**: see Agent connections

#### Create a connection

Create an SQL connection by pressing `/` inside a cell. From here, you can access, add, or edit connections. Here are some helpful links to get started, or follow the [quick start guide](sql-getting-started.md#quick-start) below.

You can also create a connection from the **Dashboard** > **Connections** under the **Team** menu.

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f418">🐘</span> Connect your PostgreSQL database -></td><td></td><td></td><td></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f42c">🐬</span> Connect your MySQL database -></td><td></td><td></td><td></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f570">🕰️</span> Request a data connection -></td><td></td><td></td><td></td></tr></tbody></table>

### Quick start

#### Create a connection

#### Step 1: press `/`

You can create data connections from either your spreadsheets or team's dashboard. From your sheet, press `/` to open the code selection menu. You'll see both your existing connections and the prompt to manage your connections (create, edit, delete). To get started with creating a connection, choose the **Manage connections** option.

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2FzPsTwAQS0IO8kXSUogyU%2FCleanShot%202024-07-17%20at%2014.03.17%402x.png?alt=media&#x26;token=24a8cb54-1268-4a1d-9c69-ff03c5047a28" alt="" width="375"><figcaption></figcaption></figure>

#### Step 2: pick the connection type

With the connection management screen open, you can edit an existing connection or create a new one. To create a new connection, select the connection type you want to create.

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2FJ2haE4X17IJqH02oxVFm%2FScreenshot%202024-07-24%20at%2012.34.54%E2%80%AFPM.png?alt=media&#x26;token=0cb73940-54e9-4224-a20c-092de362bb68" alt="SQL connection type"><figcaption><p>Select connection type screen</p></figcaption></figure>

#### Step 3: follow the instructions for creating your connection

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2F2pvbBh6NXidpRZsh0kjO%2FScreenshot%202024-07-24%20at%2012.37.17%E2%80%AFPM.png?alt=media&#x26;token=28001b29-66c4-4bfe-96b7-b8df8ff7710c" alt=""><figcaption><p>Create connection screen</p></figcaption></figure>

You can also follow this same create connection process from your team's dashboard under the connections section.

### Use connection

#### Step 1: use your connection

Once your connection has been made you can use your connection directly in the sheet. Open the code cell selection menu with `/` and select your database from the list - in this example it's named **Quadratic Postgres**.

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2FN1vGMfXGwUOFAYoB73Nl%2FCleanShot%202024-07-17%20at%2013.49.12%402x.png?alt=media&#x26;token=bddebef8-2f6e-4bd5-8b1d-2485a29a79ba" alt="" width="375"><figcaption></figcaption></figure>

You can now query your database from your newly opened SQL code editor. You can view the schema or open the AI assistant in the bottom.

The results of your SQL queries are returned to the sheet, with column 0, row 0 anchored to the cell location.

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2FbwUeXy7Ny0c61rUISEqg%2FCleanShot%202024-07-17%20at%2014.28.45%402x.png?alt=media&#x26;token=3e0c6ad8-64e1-42ad-9416-bc1bd9eb8d05" alt=""><figcaption></figcaption></figure>

You can read the data returned from queries in Python, Formulas, Javascript, etc.

Read and manipulate your data returned from SQL to summarize results, create charts, or anything else you might want to use your data for!

<table data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f522">🔢</span> Learn about the SQL AI assistant -></td><td></td><td></td></tr><tr><td><span data-gb-custom-inline data-tag="emoji" data-code="1f513">🔓</span> Learn about permissions and security -></td><td></td><td></td></tr></tbody></table>

#### Synced connections

Mixpanel, Google Analytics, QuickBooks, and Plaid connections sync data into your sheet on a schedule rather than running live queries. Once connected, pick the datasets to sync and Quadratic keeps them refreshed automatically.

#### AI context for connections

Each connection can store AI context — notes about schemas, important tables, and join patterns. The AI assistant reads it every time it writes SQL for that connection, so set it up once and every query gets smarter.

### Helpful queries

If you need help generating queries, we recommend first trying the AI assistant in your Quadratic code editor - its outputs are very helpful with writing everything from the simplest to most complex SQL queries.

#### Read data into the spreadsheet <a href="#block-9871b7ac3fa341da856503066f6f8e8c" id="block-9871b7ac3fa341da856503066f6f8e8c"></a>

**Query all data from single table into the spreadsheet**

```sql
SELECT * FROM table_name
```

**Query a limited selection (100 rows) from single table into spreadsheet**

```sql
SELECT * FROM table_name 
LIMIT 100
```

**Query specific columns from single table into the spreadsheet**

```sql
SELECT column_name1, column_name2 
FROM table_name 
LIMIT 100
```

**Query all unique values in a column**

```sql
SELECT DISTINCT column_name1 
FROM table_name 
LIMIT 100
```

**Query data conditionally**

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

**Extra considerations**

You cannot do two queries at once in SQL in Quadratic. For example, you can not create a table and then query that table in the same SQL query.

There are some slight differences between SQL syntax across databases.

* In Postgres it is best practice use quotes around table names and column names.
* In MySQL it is best practice to use backticks around table names and column names.
* In MS SQL Server it is best practice to use double quotes around table names and column names.

Stuck? The AI assistant in your code editor is ready and waiting to help with your queries.
