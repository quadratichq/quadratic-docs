---
description: Create your Supabase connection.
---

# Supabase

You can create your Supabase connection from either your team's dashboard or directly inside a spreadsheet. From the **Dashboard**, navigate to the **Connections** menu item. Or from inside a spreadsheet, press `/` and then Manage connections.&#x20;

## Connection details&#x20;

To connect to your Supabase database, you'll need to enter the parameters in the **Team connections** modal:&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-11 at 12.19.44@2x.png" alt=""><figcaption></figcaption></figure>

## Credentials

To find your Supabase credentials, click the connect button at the top of your Supabase dashboard. &#x20;

<figure><img src="../.gitbook/assets/CleanShot 2025-07-11 at 12.25.50@2x.png" alt=""><figcaption></figcaption></figure>

Once in this screen, you must use the Session Pooler options. Press view parameters and use the associated details to create the connection in Quadratic.

<figure><img src="../.gitbook/assets/CleanShot 2025-07-11 at 12.28.23@2x.png" alt=""><figcaption></figcaption></figure>

You can ignore the "pool\_mode" parameter. All others should be copied exactly as they appear into Quadratic.&#x20;

## IP allow-list

{% hint style="info" %}
You may need to whitelist both Quadratic IP addresses to make connections, which are:\
**44.240.255.40** \
**54.68.134.35**

_\* These IP addresses do not apply to self-hosted instances_&#x20;
{% endhint %}

If you need help setting up your data sources, [contact us](https://quadratichq.com/contact). Some extra resources and instructions vary depending on where your database lives.

Once you've made your connection, you can use it directly in spreadsheets to read data to your spreadsheets. Learn how [here](sql-getting-started.md#step-1-use-your-connection).&#x20;
