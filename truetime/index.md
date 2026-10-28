---
layout: single
title: TrueTime
---

**Beta:** TrueTime is in beta. Features may change. Full release is planned for Q4 2026. [Join the beta](/truetime/beta.html).
{: .notice--warning}

TrueTime is a Forge-native timesheet app for Jira.
Your data never leaves Atlassian.
TrueTime has no servers.

## Key features

- **One-click timers.** Open a Jira issue. Click Start. Click Stop. The app creates a native Jira worklog.
- **Weekly timesheets.** See your week at a glance. Log time manually. Edit entries. Delete mistakes.
- **One-click approvals.** Submit your week with one click. Your manager approves or rejects.
- **Billable tracking.** Mark time as billable or non-billable. The flag stays in Jira. It survives uninstall.
- **Excel export.** One click. Real .xlsx file. Includes hours, billable flags, project totals.
- **Tempo import via CSV.** Export Tempo data to CSV. Upload it into TrueTime. Your history moves with you.
- **Teams.** Create teams, manage members, and control who can approve timesheets.
- **Free for up to 10 users.** $2.99 per user per month above that.

## Screenshots

Product views from our test site, captured by the E2E suite. Click an image to enlarge it.

<style>
.tt-gallery { display: grid; grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 1em; }
.tt-gallery figure { margin: 0; }
.tt-gallery img { width: 100%; height: auto; border: 1px solid #ddd; border-radius: 4px; }
.tt-gallery figcaption { font-size: 0.85em; margin-top: 0.25em; }
</style>

<div class="tt-gallery" id="tt-gallery">
  <figure>
    <a href="/assets/images/e2e-timesheet-grid.png" data-pswp-width="1280" data-pswp-height="1000">
      <img src="/assets/images/e2e-timesheet-grid.png" alt="TrueTime weekly timesheet grid">
    </a>
    <figcaption><strong>Weekly timesheet.</strong> Week grid, day totals, manual entry.</figcaption>
  </figure>
  <figure>
    <a href="/assets/images/e2e-reports.png" data-pswp-width="1280" data-pswp-height="1000">
      <img src="/assets/images/e2e-reports.png" alt="TrueTime weekly report view">
    </a>
    <figcaption><strong>Reports.</strong> Weekly totals by project, issue, or day.</figcaption>
  </figure>
  <figure>
    <a href="/assets/images/e2e-team-approvals.png" data-pswp-width="1280" data-pswp-height="300">
      <img src="/assets/images/e2e-team-approvals.png" alt="TrueTime approvals view">
    </a>
    <figcaption><strong>Approvals.</strong> Submit a week for approval.</figcaption>
  </figure>
  <figure>
    <a href="/assets/images/e2e-settings.png" data-pswp-width="1280" data-pswp-height="1000">
      <img src="/assets/images/e2e-settings.png" alt="TrueTime settings view">
    </a>
    <figcaption><strong>Admin settings.</strong> About the app, admin settings, feedback.</figcaption>
  </figure>
  <figure>
    <a href="/assets/images/e2e-issue-panel-timer.png" data-pswp-width="645" data-pswp-height="485">
      <img src="/assets/images/e2e-issue-panel-timer.png" alt="TrueTime timer panel on a Jira issue">
    </a>
    <figcaption><strong>Issue timer.</strong> Start timer, log time manually.</figcaption>
  </figure>
</div>

<link rel="stylesheet" href="/assets/photoswipe/photoswipe.css">
<script type="module">
import PhotoSwipeLightbox from '/assets/photoswipe/photoswipe-lightbox.esm.min.js';
const lightbox = new PhotoSwipeLightbox({
  gallery: '#tt-gallery',
  children: 'a',
  pswpModule: () => import('/assets/photoswipe/photoswipe.esm.min.js')
});
lightbox.init();
</script>

## Docs

- [User Guide](/truetime/user-guide.html) — Log time, approvals, teams, admin settings.
- [Migrate from Tempo](/truetime/migration.html) — Move your history with a CSV export.
- [Log time with the Jira REST API](/truetime/api.html) — Create entries from scripts and AI agents.
- [Privacy Policy](/truetime/privacy.html) — What TrueTime stores and where.
- [Terms of Service](/truetime/terms.html) — License, tiers, liability.
- [Support](/truetime/support.html) — How to get help.
- [FAQ](/faq.html) — Costs, data location, migration, uninstall, support.
- [Why switch from Tempo](/truetime/switch.html) — Price and feature comparison.
- [Savings Calculator](/calculator.html) — Compare Tempo and TrueTime costs.
- [Join the beta](/truetime/beta.html) — Early access and feedback.

## Support

Use the [contact form](/contact.html).
We respond to every message.

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "TrueTime for Jira",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Jira Cloud",
  "url": "https://infralicious.com/truetime/",
  "author": {"@type": "Organization", "name": "Infralicious"},
  "offers": [
    {"@type": "Offer", "price": "0", "priceCurrency": "USD", "description": "Free for up to 10 users"},
    {"@type": "Offer", "price": "2.99", "priceCurrency": "USD", "description": "Per user per month above 10 users"}
  ]
}
</script>
