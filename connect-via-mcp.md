# Connect via MCP

## Connect via MCP

Quadratic provides a hosted Model Context Protocol (MCP) server that lets AI assistants read and write your Quadratic spreadsheets. Connect it to any MCP-compatible client to create files, import data, run code, and build analyses from outside the app.

### Connect

Add the Quadratic MCP server to your AI tool of choice:

```
https://mcp.quadratichq.com/
```

For example, in Cursor or Claude, add a remote MCP server with the URL above. The first time you use it, you'll be prompted to sign in to your Quadratic account through a browser-based flow.

### What it can do

The MCP server exposes tools for working with your files:

* **auth** — sign in and out of your Quadratic account
* **files\_read** — list your files and get file metadata
* **files\_write** — create, open, and close files
* **read\_data** — read cell data, code cell contents, table outlines, database schemas, dependencies, and search text
* **write\_data** — set cell values, write Python/JavaScript/SQL/Formula code cells, import CSV/Excel/Parquet files, create data tables, and more

Read and write tools support batching, so AI clients can perform many operations efficiently in a single call.

### Example prompts

Once connected, try prompts like:

* "Create a new Quadratic file and import this CSV."
* "Read the table in my Sales file and summarize revenue by region."
* "Add a Python chart to my Q3 report file."

### Security

The MCP server acts on your behalf using your Quadratic account. It has access to the same files and connections you do. Sessions are authenticated via OAuth and can be revoked by logging out.

{% hint style="info" %}
Prefer calling Quadratic from your own code instead of an AI agent? Use the Developer API.
{% endhint %}
