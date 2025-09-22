---
description: Create your MS SQL Server connection.
---

# MS SQL Server

You can create your MS SQL Server connection from either your team's dashboard or directly from a spreadsheet. From the dashboard, navigate to the **Connections** page or from a spreadsheet press / and then **Manage connections**.&#x20;

## Connection details&#x20;

To connect to your MS SQL Server database, you'll need to enter the parameters in the **Team connections** modal:&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-09-25 at 15.24.18@2x (1).png" alt=""><figcaption></figcaption></figure>

### Connection name

You can name your connection however you'd like. This is the display name for your connection across Quadratic and your team.&#x20;

```
example: Sales Database
```

### Host name&#x20;

This is the connection host, the direct connection to your database. It can be an IP address or URL. You might see a connection string that looks something like this:&#x20;

```
mysql://default:xyz123@mysql-hostname.com:5432
```

The hostname is the IP address or URL. From the above connection string, this would be the host, which you would add to the **Hostname** field:

```
mysql-hostname.com
```

### Port number

This is the connection port; you might see it at the end of your hostname after the colon. It is typically a four-digit number. From the above example, add this number to the **Port** field. `3306` is the default port number for MySQL.

```
3306
```

### Database name

This is the name of the database you want to connect to. Your database can have multiple tables - be sure to use the **database name** and not the name of a table. Example database name:

```
mysql_db
```

### **Username**

This is an authentication detail that depends on your database account username. Some common defaults include `admin` or `default`. This information is in your database's authentication details, found in your database's authentication settings, or received from your database administrator. Example:

```
admin
```

### **Password**

This is the password you use to connect to your database. This information is in your database's authentication details, found in your database's authentication settings, or received from your database administrator. Example:

```
1234abcd
```

## IP allow-list

{% hint style="info" %}
You must whitelist both Quadratic IP addresses to make connections, which are:\
**44.240.255.40** \
**54.68.134.35**

_\* These IP addresses do not apply to self-hosted instances_&#x20;
{% endhint %}

If you need help setting up your data sources, [contact us](https://quadratichq.com/contact). Some extra resources and instructions vary depending on where your database lives.

[AWS](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html), [Azure](../), [GCP](https://cloud.google.com/firewall/docs/firewalls)

Once you've made your connection, you can use it directly in spreadsheets to read data to your spreadsheets. Learn how [here](sql-getting-started.md#step-1-use-your-connection).&#x20;
