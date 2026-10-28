---
layout: single
title: Log time with the Jira REST API
description: "Create time entries with the Jira REST API."
---

**Beta:** TrueTime is in beta. Features may change. Full release is planned for Q4 2026.
{: .notice--warning}

TrueTime entries are native Jira worklogs.
You can create them with the Jira REST API.
Scripts and AI agents can use the same calls.
TrueTime has no public API of its own today.

## What you need

- Your Jira site URL, for example `https://your-site.atlassian.net`.
- An Atlassian API token for your account.
  Create one at id.atlassian.com under Security, then API tokens.
- An issue key to log time on.

Keep the token secret. The token acts with your full account rights.

## Create an entry

```bash
curl -s -X POST \
  -u "you@example.com:YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  "https://your-site.atlassian.net/rest/api/3/issue/MP-15/worklog" \
  -d '{
    "timeSpentSeconds": 28800,
    "started": "2026-10-12T09:00:00.000+0000",
    "comment": {
      "type": "doc",
      "version": 1,
      "content": [
        { "type": "paragraph", "content": [
          { "type": "text", "text": "Design review" } ] }
      ]
    }
  }'
```

The call returns HTTP 201 and the new worklog ID.
`started` sets the day and the start time, in your account timezone.

Read, update, and delete use the same base path:

- Read: `GET /rest/api/3/issue/{key}/worklog`
- Update: `PUT /rest/api/3/issue/{key}/worklog/{worklogId}`
- Delete: `DELETE /rest/api/3/issue/{key}/worklog/{worklogId}`

## What this path skips

The app checks each entry at write time. The Jira API path skips these checks:

1. **Future dates.** The app rejects an entry dated in the future.
2. **24 hour cap.** The app rejects an entry over 24 hours.
3. **Locked periods.** The app refuses writes into a locked week.
4. **Submitted weeks.** The app refuses writes into a submitted or approved week. An API write lands anyway and then disagrees with the submitted counts. Do not write into a submitted week.
5. **Overlap warnings.** The app warns when two entries overlap in time.
6. **Comment cleanup.** The app trims and sanitizes comment text.
7. **Delete audit.** The app records a snapshot of a deleted entry. An API delete leaves no snapshot.

Jira still applies its own rules. You need worklog permission on the issue.

## Billable and other flags

The app stores flags as worklog properties.
An entry with no properties reads as non-billable in the app.
Set the billable flag with a second call:

```bash
curl -s -X PUT \
  -u "you@example.com:YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  "https://your-site.atlassian.net/rest/api/3/issue/MP-15/worklog/10153/properties/truetime-billable" \
  -d '{ "billable": true }'
```

Other keys: `truetime-capex-opex` with body `{ "type": "capex" }`, and `truetime-real-started` with body `{ "realStart": true }` when `started` is the true start time.

## What the API cannot do

Week submission lives in the app, not in Jira.
No API call can submit, approve, or withdraw a week.
Use the Team tab in the TrueTime page for those steps.
