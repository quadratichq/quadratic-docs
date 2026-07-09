# CockroachDB

## CockroachDB

You can create your CockroachDB connection from either your team's dashboard or directly inside a spreadsheet. From the Dashboard, navigate to the Connections menu item. Or from inside a spreadsheet, press `/` and then Manage connections.

CockroachDB is PostgreSQL-compatible, so the connection details mirror a Postgres connection.

### Connection details

To connect to your CockroachDB cluster, enter the following parameters in the Team connections modal:

* **Connection name** — the display name for your connection across Quadratic and your team
* **Hostname** — your cluster's host (for CockroachDB Cloud, copy it from the cluster's **Connect** dialog)
* **Port** — typically `26257`
* **Database** — the database name
* **Username / Password** — credentials with the access you want available in Quadratic

CockroachDB Cloud clusters require SSL; Quadratic connects securely by default.

### IP allow-list

{% hint style="info" %}
You must whitelist both Quadratic IP addresses to make connections, which are:\
44.240.255.40\
54.68.134.35

* These IP addresses do not apply to self-hosted instances
{% endhint %}

Once you've made your connection, you can use it directly in spreadsheets to read data to your spreadsheets. Learn how in SQL - getting started.
