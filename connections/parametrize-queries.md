---
description: Insert data from sheet into your queries with parametrized queries.
---

# Parametrize queries

### Parametrized reference

You can reference sheet data in SQL. Use \{{\}} notation for references. You can only reference single cells at a time.&#x20;

```sql
SELECT * FROM {{A1}} WHERE salary > {{A4}}
```

Note in the following example where the query output changes based on what table is selected in cell B1.&#x20;

### Parametrize a reference from another sheet

```sql
select abc from def where ghi="{{'Sheet_name'!H3}}"
```

<figure><img src="../.gitbook/assets/CleanShot 2024-12-13 at 12.08.13@2x.png" alt=""><figcaption></figcaption></figure>
