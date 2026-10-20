---
layout: single
title: User Guide
---

## Log time

### Option 1: Timer

Use the timer on any Jira issue.

1. Open a Jira issue.
2. Click **View app actions**.
3. Click **TrueTime**.
4. Click **Start timer**.
5. Add a comment if you want.
6. Set **Billable** on or off.
7. Click **Stop**.
8. The app creates a native Jira worklog.

### Option 2: Manual entry

Enter time manually in the timesheet view.

1. Open **TrueTime Timesheet**.
2. Add an entry with these fields:
   - **Issue key**. Example: `PROJ-123`.
   - **Date**. Format: YYYY-MM-DD.
   - **Hours**. Example: `2.5`.
   - **Comment**. Optional.
   - **Billable**. Default is on.
3. Save the entry.

### View your week

1. Open the **Timesheet** tab.
2. The tab shows all entries for the current week.
3. Use **Prev** and **Next** to change weeks.
4. Edit or delete an entry from the grid.

### Timesheet tips

- **Keyboard shortcuts**: `←` / `→` switch weeks, `N` starts a new entry.
- **Copy last week**: one button copies last week's entries as drafts. Review them, then save all or discard.
- **Overtime flags**: days over 8h and weeks over 40h get a badge.
- Weekends are shaded in the grid. Hours round to the nearest 15 minutes.
- Deleting a worklog removes it at once.

## Approvals

### Submit your week

1. Click the **Approvals** tab.
2. Click **Submit for approval**.
3. Your approver sees it in their queue.

### Approve or reject

Approvers manage the queue in the **Approvals** tab.

1. Open **Pending approvals**.
2. Click **Approve** or **Reject**.
3. A rejection needs a reason. The author can resubmit after a rejection.

### Set up approvers

1. Open the **Approvals** tab.
2. Find the **Approvers** section.
3. Search by name or email, then add the approver.
4. Until at least one approver exists, approvals stay disabled.

## Teams

- Create a team with a name and members.
- Team leads manage members and settings.
- Team leads can approve team members' timesheets.
- Only team leads or the team creator can delete a team.
- Deleted teams go to trash for 30 days. Restore a team from the Deleted teams section. After 30 days, the team is gone for good.

## Admin settings

Open settings from **Atlassian Administration → Apps → TrueTime → Configure**, or from the **Settings** tab inside the Timesheet page.

### Auto-timers

- A timer starts when an issue moves to a selected status.
- The timer stops and writes a worklog when the issue moves to an inactive status.
- Pick statuses from the dropdowns. Defaults: active `In Progress`, inactive `Done, Closed, Resolved`.

### Lockable periods

- Lock a week so nobody can log, edit, or delete worklogs in it.
- Pick any date with the date picker. The whole week gets locked.
- Unlock a week at any time.

### Non-ticketed work

- Set a placeholder issue for work without a ticket, such as meetings or admin work.
- Type an issue key. A preview shows the summary so you can confirm the issue.
- Users then pick **Non-ticketed** in the log work form.

### Board card display

- Show total hours logged on each Jira board card.
- Create a native **Number** custom field in Jira first (Jira Settings → Issues → Custom fields).
- Pick the field from the dropdown, then add it to your board's Card Layout.
- Totals sync on worklog create, update, and delete.
- If your field is missing from the dropdown, use the **Refresh fields** button.

### Custom attributes

- Add extra fields on every worklog, such as activity type, location, or client code.
- Type is a dropdown: text, number, dropdown, checkbox, date.
- Custom attributes are stored as worklog properties. They survive uninstall.
- Deleting an attribute asks for confirmation first.

### Private labeling

- Rename the app and set a brand color and logo URL.
- Use the color picker or type a hex code. The swatch previews live.

## Reports

1. Click the **Report** tab.
2. The tab shows hours grouped by project.
3. Click **Download Excel (.xlsx)** for a spreadsheet.

## FAQ

**Where is my data?**

Your data is in Jira. Time entries are native Jira worklogs. The app sends no data to external servers.

**What happens if I uninstall TrueTime?**

Your worklogs stay in Jira. You lose only running timers, approval records, and app preferences.

**Why is there a 1-minute minimum?**

Jira requires a minimum of 60 seconds for worklogs. The app rounds up shorter timers.

**Who approves my week?**

Your Jira admin configures approvers. Ask your admin if you are not sure.
