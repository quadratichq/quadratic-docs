---
description: Schedule tasks to run in your spreadsheet at set intervals.
---

# Scheduled tasks

## Scheduled tasks

Quadratic scheduled tasks run your sheet automatically on a schedule you set. Cloud runners execute your code without needing your browser open — connect a data source, schedule a refresh, and your sheet stays current.

#### Accessing scheduled tasks

Access scheduled tasks from the sidebar. The panel lists every task in the file with its schedule and run history. You can also filter your dashboard's file list to show only files with scheduled tasks.

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2F4ezkeYCWNf31EvG6VTSp%2FCleanShot%202026-01-05%20at%2018.13.42%402x.png?alt=media&#x26;token=768e681a-bd21-4809-8612-e0e573769744" alt=""><figcaption></figcaption></figure>

#### Schedule your task

**Task types: Run file, Run sheet, Run selection**

**Run file:** executes everything in the entire spreadsheet.

**Run sheet:** only executes a single selected sheet.

**Run selection:** only executes a selection in a single sheet.

#### Intervals: hourly, daily, custom cron

Set hourly, daily or custom cron timeframes.

* **Daily** — pick the days of the week and a time.
* **Hourly** — runs at a chosen minute past each hour.
* **Custom cron** — full cron expressions for anything else.

Pick your timezone when creating the task — schedules are stored in UTC and displayed in the timezone you choose.

{% hint style="warning" %}
Tasks can run at most once per hour. Custom cron expressions more frequent than hourly are rejected.
{% endhint %}

Cron examples:

| Cron expression | Translation                        |
| --------------- | ---------------------------------- |
| 0 0 \* \* \*    | Every day at 12:00 AM              |
| 0 0 \* \* FRI   | At 12:00 AM, only on Friday        |
| 0 0 1 \* \*     | At 12:00 AM, on day 1 of the month |
| 0 \* \* \* \*   | Every hour                         |

<figure><img src="https://2438361843-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Ff1Y5UzPF2x1oIzVJbUK8%2Fuploads%2Flk5yqoQlgPAiIuy22T6U%2FCleanShot%202026-01-05%20at%2018.18.05%402x.png?alt=media&#x26;token=adb1c781-8eb6-4f19-a62f-01fc559fe2dc" alt=""><figcaption></figcaption></figure>

#### Manage tasks with AI

Ask the AI to manage schedules for you: "run this sheet every weekday at 7am" creates the task. You can also ask it to list, edit, pause, or delete tasks and to summarize recent run history.
