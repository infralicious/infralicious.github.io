# AGENTS.md — Infralicious website

Instructions for AI agents working in this repo.
Claude Code reads these through CLAUDE.md (`@AGENTS.md`).

## What this repo is

- Jekyll site, Minimal Mistakes 4.28.1 via `remote_theme`, hosted on GitHub Pages.
- Custom domain: https://infralicious.com (CNAME file in repo root).
- Root pages are the company site. `truetime/` pages are the TrueTime for Jira docs.
- This repo holds no app code. TrueTime app code lives in `nitrocode/truetime` (separate repo, separate chat).
- Theme overrides live in `_includes/` and `_sass/`. The theme itself is remote. Do not edit theme files in place.

## Language rule

- Write everything in ASD-STE100 Simplified Technical English.
- Short sentences (max 20 words). Active voice. One idea per sentence.
- No idioms, slang, or complex words. No em dashes. Use hyphens or restructure.

## Build and check

- Pages builds on every push to main (~45-80s). Check with `gh run list --repo infralicious/infralicious.github.io --limit 1`.
- Local build: `bundle exec jekyll build` (Gemfile mirrors the Pages gem set).
- Link check runs on push: `Check links` workflow (htmlproofer). Keep it green.
- Scorecard runs on push and weekly: `Scorecard supply-chain security` workflow.

## Commits and pushes

- Sign every commit (SSH signing is configured repo-local).
- Push to main deploys the live site at once. Confirm before pushing, unless the user has told you to push freely.
- Push pattern: `git -c credential.helper='!gh auth git-credential' push origin main`.
- Small, topical commits. One change per commit.

## Content rules

- Never publish an email address on the site. The public contact is the contact form (`/contact.html`).
- `support@infralicious.com` is vendor-profile data only. It never appears on the site.
- Privacy and terms pattern: root holds generic company versions. Each app folder holds complete self-contained versions.
- Beta notices stay on TrueTime pages until the full release ships.
- Release-notes habit: publish one short post per release. Keep each post in ASD-STE100.
- Pricing facts come from the Marketplace listing copy only: free to 10 users, $2.99 per user per month above that.
- Never invent testimonials, reviews, install counts, or screenshots.
- Keep `llms.txt` in sync when docs change. Regenerate `llms-full.txt` when docs change.
- Screenshots gallery on `/truetime/` uses vendored PhotoSwipe 5.4.4 in `assets/photoswipe/`. No CDN. No dependencies. Page-local style and module script live in `truetime/index.md`.
- Presentation-only changes (gallery markup, styles) do not need an `llms-full.txt` regen. Regen it when docs prose changes.
- Keep `ai.txt` permissive: AI agents may crawl, index, summarize, and train on public pages.

## Repo settings as code

- `.github/settings.yml` is enforced by the Settings app. Change settings in that file, not in the GitHub UI.
- Main branch protection is on: no force push, no deletion. Direct pushes still work.
- Renovate owns dependency updates (`renovate.json`, best-practices preset). Dependabot is off.

## Well-known files

- `robots.txt`, `sitemap.xml` (jekyll-sitemap plugin), `security.txt` (root and `.well-known/`), `humans.txt`, `ai.txt`, `llms.txt`, `llms-full.txt`.
- `security.txt` expires 2027-10-20. Refresh it before that date.

## Do not touch

- The old `infralicious/docs` repo is private now. Leave it alone.
- Do not add a public phone number, address, or email to the site.
