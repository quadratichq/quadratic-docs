# Neon

## Neon

You can create your Neon connection from either your team's dashboard or directly inside a spreadsheet. From the Dashboard, navigate to the Connections menu item. Or from inside a spreadsheet, press `/` and then Manage connections.

### Connection details

To connect to your Neon database, enter the following parameters in the Team connections modal. You can find them all in your Neon project's connection details:

* **Connection name** — the display name for your connection across Quadratic and your team
* **Hostname** — your Neon endpoint host (looks like `ep-xxxx.region.aws.neon.tech`)
* **Port** — `5432`
* **Database** — the database name
* **Username / Password** — credentials with the access you want available in Quadratic

Neon endpoints enforce SSL; Quadratic connects securely by default.

### IP allow-list

{% hint style="info" %}
If your Neon project uses IP Allow, add both Quadratic IP addresses:\
44.240.255.40\
54.68.134.35

* These IP addresses do not apply to self-hosted instances
{% endhint %}

Once you've made your connection, you can use it directly in spreadsheets to read data to your spreadsheets. Learn how in SQL - getting started.
