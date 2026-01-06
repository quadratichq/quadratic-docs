---
description: Schedule tasks to run in your spreadsheet at set intervals.
---

# Scheduled tasks

Quadratic scheduled tasks allow you to set specific timeframes for your sheet to run automatically. Cloud runners execute your code automatically without needing your intervention.&#x20;

### Accessing scheduled tasks&#x20;

Access scheduled tasks from the sidebar

<figure><img src="../.gitbook/assets/CleanShot 2026-01-05 at 18.13.42@2x.png" alt=""><figcaption></figcaption></figure>

### Schedule your task&#x20;

#### Task types: Run file, Run sheet, Run selection&#x20;

**Run file:** executes everything in the entire spreadsheet.&#x20;

**Run sheet:** only executes a single selected sheet.&#x20;

**Run selection:** only executes a selection in a single sheet.&#x20;

### Intervals: hourly, daily, custom cron&#x20;

Set hourly, daily or custom cron timeframes.&#x20;

Cron examples:&#x20;

| Cron expression  | Translation                        |
| ---------------- | ---------------------------------- |
| 0 0 \* \* \*     | Every day at 12:00 AM              |
| 0 0 \* \* FRI    | At 12:00 AM, only on Friday        |
| 0 0 1 \* \*      | At 12:00 AM, on day 1 of the month |
| 0 \* \* \* \*    | Every hour                         |

<figure><img src="../.gitbook/assets/CleanShot 2026-01-05 at 18.18.05@2x.png" alt=""><figcaption></figcaption></figure>

