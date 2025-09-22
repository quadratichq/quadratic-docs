---
description: Details for permissions and security of connections.
---

# Security

## User permissions&#x20;

User permissions are based on a team member's credentials. To edit team member permissions, visit the members page in your team's dashboard.

**Owner:** has access to create, delete, use, and edit all connections

**Editor:** has access to use all connections but cannot create, delete, or edit connections

**Viewer:** has no access to connections but can view data displayed from connections&#x20;

## Database access

By default, Quadratic allows all the queries and table access granted by the database user credentials. This means if the database user credentials used in the connection are granted full permissions, then Quadratic users of that connection will have the same permissions. Only make database connections that align with what access you want your users to have.&#x20;

{% hint style="warning" %}
If you want your users to have read-only access to Quadratic, consider creating read-only database users for connections. Only create connections with access to the tables you want your users to have.&#x20;
{% endhint %}

## IP allow-list

{% hint style="info" %}
You must whitelist both Quadratic IP addresses to make connections, which are:\
**44.240.255.40** \
**54.68.134.35**
{% endhint %}

If you need help whitelisting, you can [contact us](https://quadratichq.com/contact) to help set up your data sources. Here are some extra resources; instructions vary depending on where your database lives.

[AWS](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-security-groups.html), [Azure](../), [GCP](https://cloud.google.com/firewall/docs/firewalls)

## Data security and compliance

Quadratic is partnered with Vanta for our security and data controls. You can view our live trust center here: [https://trust.quadratichq.com/](https://trust.quadratichq.com/)

### Certifications

Quadratic is currently in the audit period for SOC II and HIPAA compliance.&#x20;

Need more details about our security, or are you seeking a self-hosted option? Feel free to [contact us](https://quadratichq.com/contact).
