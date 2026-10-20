---
layout: single
title: Migrate from Tempo
---

**Beta:** TrueTime is in beta. Features may change. Full release is planned for early Q4 2026.
{: .notice--warning}

Move your Tempo history into TrueTime with a CSV export.
Migration is CSV-only. TrueTime makes no API calls to Tempo.
Your Tempo token is never needed. Your data stays in Atlassian.

## Steps

1. Export your worklogs from Tempo to CSV.
2. Open **TrueTime Timesheet**.
3. Open the **Migration** tab.
4. Upload the CSV file.
5. Check the import result. The app skips invalid rows and reports each skip.
6. The app skips duplicates automatically.

## CSV format

You can upload a Tempo export as is. The app reads the Tempo columns:
Work Item Key, Logged Hours or Logged Seconds, Work Date, Work Description,
and Billable Seconds.

A simple format also works. The header is: `Date, Issue, Hours, Comment`.

Example row: `2026-10-05, PROJ-123, 2.5, Sprint work`.

## What moves with you

- Dates, issue keys, hours, comments, and the billable flag move into TrueTime.
- Imported entries become native Jira worklogs.
- Entries appear in timesheets, approvals, and reports like any other entry.

## What to know

- Migration is CSV-only. There is no Tempo API import.
- Your Tempo token is never needed and never asked for.
- Validate the import result before you uninstall Tempo.
- Keep your Tempo CSV file until you confirm the import looks right.
