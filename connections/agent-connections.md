# Agent connections

## Agent connections

Agent connections let you pull data from third-party services — CRMs, payment processors, analytics tools, internal APIs, and more — directly into your spreadsheets. Unlike database connections, agent connections work with any service that exposes a REST API.

### Create an agent connection

1. In a sheet, press `/` in a cell and choose **Connections**, or go to **Dashboard > Connections** under the Team menu.
2. Pick a service from the catalog, or choose **Connect to anything** to set up a custom API.
3. The AI walks you through setup conversationally: it researches the service's API, proposes a connection plan, collects credentials, tests the connection, and finalizes it.

For services that use OAuth, you'll be redirected to sign in to the service and grant access. For API-key services, the AI asks for your key and stores it securely as a team secret.

{% hint style="info" %}
AI messages during agent connection setup are free — they don't count against your team's AI usage.
{% endhint %}

### Use an agent connection

Once created, agent connections can be used in two ways:

#### From AI chat

Mention the connection with `@` in the AI chat. The AI can query the connected service and combine its data with your sheet data.

#### From code cells

Agent connections are available from Python and JavaScript code cells. Requests run through Quadratic's authenticated proxy, which injects your stored credentials.

Reference team secrets with `{{SECRET_NAME}}` placeholders in URLs, headers, or request bodies — the actual values never appear in your code or your sheet:

```python
import requests
import pandas as pd

response = requests.get(
    'https://api.example.com/v1/customers',
    headers={'Authorization': 'Bearer {{EXAMPLE_API_KEY}}'}
)
df = pd.DataFrame(response.json()['data'])
df
```

### Team secrets

Secrets are managed in your team settings under **Secrets**. Each secret has a name and a value; the value is write-only after creation. Secrets are scoped to your team and only substituted for requests to the domains allowed by the connection.

### Permissions

Agent connections follow the same permission model as database connections: team editors can use connections in sheets; owners can create, edit, and remove them.
