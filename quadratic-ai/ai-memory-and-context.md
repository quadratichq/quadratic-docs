# AI memory & context

## AI memory & context

Quadratic AI can remember durable context between chats so you don't repeat yourself. Memory lives at three levels: personal, team, and connection.

### Personal memory

**Settings > AI** holds your personal memory — preferences and facts included in every chat you start. For example: "I prefer charts with a dark theme" or "Fiscal year starts in February."

You can edit it directly, and the AI may propose updates as it learns your preferences. Version history lets you review and roll back changes.

### Team memory

Your team settings hold shared context for everyone on the team: business definitions, naming conventions, metric formulas, and domain knowledge. Team editors can update it.

Example: "ARR is calculated from the `subscriptions` table excluding trials. Our customer IDs look like CUST-XXXX."

### Connection context

Each database connection can carry its own context — schema quirks, which tables matter, what joins to use. The AI reads it whenever it writes SQL against that connection.

### How the AI uses memory

Memory is automatically included in AI chats. The AI can also update memory itself when you tell it something worth remembering ("remember that we report revenue in EUR") — updates are versioned, so you can always see what changed and revert.

{% hint style="info" %}
You can disable prompt storage entirely from your team's Settings page — see AI security.
{% endhint %}
