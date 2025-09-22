---
description: How to connect to BigQuery from Quadratic.
---

# BigQuery

You can create your BigQuery connection from either your team's dashboard or directly inside a spreadsheet. From the **Dashboard**, navigate to the **Connections** menu item. Or from inside a spreadsheet, press `/` and then Manage connections.&#x20;

## Connection details&#x20;

To connect to your BigQuery database, you'll need to enter the parameters in the **Team connections** modal:&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-22 at 16.11.48@2x.png" alt=""><figcaption></figcaption></figure>

### Connection name

You can name this whatever you'd like. This is the name you'll see in Quadratic any time you use the connection.&#x20;

### Project ID

This can be found in the project selector at the top of our Google Cloud Console. Do not mistake the project name for the ID; they can be the same but are often different. Make sure you select the ID from the list.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-22 at 15.53.54@2x (1).png" alt=""><figcaption></figcaption></figure>

### Dataset&#x20;

Datasets can be found inside your BigQuery instance in the sidebar.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-22 at 16.09.09@2x.png" alt=""><figcaption></figcaption></figure>

### Service account configuration

Acquire your service account JSON key from the keys section under service accounts in Google Cloud Console.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-22 at 16.10.39@2x.png" alt=""><figcaption></figcaption></figure>

### IP allow-list

{% hint style="info" %}
You may need to whitelist both Quadratic IP addresses to make connections, which are:\
**44.240.255.40** \
**54.68.134.35**

_\* These IP addresses do not apply to self-hosted instances_&#x20;
{% endhint %}

If you need help setting up your data sources, [contact us](https://quadratichq.com/contact). Some extra resources and instructions vary depending on where your database lives.&#x20;
