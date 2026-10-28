---
layout: single
title: "Migrate from Tempo with a CSV export"
date: 2026-10-27
excerpt: "Move Tempo worklogs into TrueTime with a CSV file. No Tempo token is needed."
---

Move your Tempo history into TrueTime with a CSV export.
Migration is CSV-only. TrueTime makes no API calls to Tempo.
Your Tempo token is never needed. Your data stays in Atlassian.

Follow these steps.

1. Export your worklogs from Tempo to CSV.
2. Open **TrueTime Timesheet**.
3. Open the **Migration** tab.
4. Upload the CSV file.
5. Check the import result.
6. The app skips invalid rows and reports each skip.
7. The app skips duplicates automatically.

Dates, issue keys, hours, comments, and the billable flag move into TrueTime.
Imported entries become native Jira worklogs.
Entries appear in timesheets, approvals, and reports like any other entry.

Validate the import result before you uninstall Tempo.
Keep your Tempo CSV file until you confirm the import looks right.
Read the full [migration guide](/truetime/migration.html) for CSV formats.
