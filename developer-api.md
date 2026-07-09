# Developer API

## Developer API

The Quadratic Developer API lets you programmatically create and edit spreadsheets: write cells, run code, import files, manage sheets, and read results. Use it to integrate Quadratic into data pipelines, internal tools, and scheduled jobs.

### Authentication

Create an API token from your team settings under **API tokens**. Tokens are team-scoped and shown once at creation — store them like passwords.

Pass the token in the Authorization header:

```
Authorization: Bearer qdx_live_...
```

### What you can do

| Area                | Capabilities                                                                                        |
| ------------------- | --------------------------------------------------------------------------------------------------- |
| Files               | List, get, create, and import files                                                                 |
| Sheets              | Add, rename, delete, duplicate, reorder, color, freeze panes                                        |
| Cells               | Get/set values, code cells (Python, JavaScript, SQL, Formula), rerun code, formats, borders, merges |
| Tables              | Create data tables, convert ranges, column settings                                                 |
| Rows & columns      | Insert, delete, resize                                                                              |
| Validations         | List, add, remove                                                                                   |
| Conditional formats | Get and update                                                                                      |
| Search & context    | File outline, cell data, text search                                                                |
| History             | Undo, redo                                                                                          |
| Connections         | List connections and fetch database schemas                                                         |

Files cannot be deleted through the API — deletion stays in the app.

### Client libraries

Generated TypeScript and Python client libraries are available, so you can call the API with typed methods instead of raw HTTP.

### Developer API vs. MCP

Both surfaces expose the same underlying operations. Use the **Developer API** for deterministic automation from your own code; use the MCP server when an AI agent should operate Quadratic on your behalf.
