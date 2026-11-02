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
- Land changes through a pull request. Direct push to main is blocked by the Protect main ruleset.
- The ruleset requires the htmlproofer check. The ruleset allows squash merge only.
- Push pattern for branches: `git -c credential.helper='!gh auth git-credential' push -u origin <branch>`.
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
- `AGENTS.md` and `CLAUDE.md` stay in the repo for agents. They are excluded from the Jekyll build. They never render as site pages. They never appear in the sitemap or in search.

## Repo settings as code

- Settings are managed by safe-settings from the admin repo. Do not edit settings in the GitHub UI.
- Protect main ruleset is on: pull request required, htmlproofer check required, squash merge only, no force push, no deletion.
- Renovate owns dependency updates (`renovate.json`, best-practices preset). Dependabot is off.

## Best practices we follow

- Baseline is the OWASP Cheat Sheet Series. Check the relevant sheet before you decide.
- XSS prevention is followed. The calculator uses `textContent`, not `innerHTML`. No user HTML is rendered. No `eval` or `document.write` is used.
- Transport protection is followed, with limits. The custom domain uses Pages Enforce HTTPS. The site collects no passwords, cards, or PII itself.
- Secrets management is followed. No real secret lives in the repo. Only a placeholder token appears in `truetime/api.md`, with guidance to keep tokens secret.
- Dependency management is partial. Actions are SHA-pinned. Renovate owns updates. The theme is pinned at 4.28.1. The Gemfile is unpinned, with no lockfile. See issue 18.
- Input validation is followed, with limits. The calculator parses numbers with `parseInt` and a minimum of 1. All other input goes through Google Forms.
- Third-party JavaScript is followed, with limits. PhotoSwipe 5.4.4 and FontAwesome 6.7.2 are vendored. No CDN is used. Google Forms is the only third-party load, with a fallback link.
- Content Security Policy and frame policy are gaps, with limits. Pages cannot set custom headers. `SECURITY.md` documents this limit. Do not move hosting for this alone.
- Error handling is followed. The 404 page is generic. No stack trace is shown. `AGENTS.md` and `CLAUDE.md` are excluded from the build, sitemap, and search.
- OWASP Top 10 factors that apply are followed or partial, as above. Access control, auth failures, SSRF, and app logging are not applicable. The site has no login, no server input, and no app logs.
- Software integrity is followed, with limits. Commits are signed. Actions are SHA-pinned. Pull requests and the htmlproofer check are required. Squash merge is the only merge method. Do not add an SBOM for this static site.
- 12-Factor factors that apply are followed or partial, as above. Codebase, config, and build, release, and run are followed. Dependencies and dev and prod parity are partial. Port binding, processes, concurrency, disposability, app logs, and admin processes are not applicable. The site is static, with no server and no state.
- OpenSSF Scorecard is followed, with limits. Pinned dependencies, Renovate, MIT licence, minimal tokens, and branch protection are in place. Score was 6.7 on 2026-10-21. SAST, CII Best Practices, and Fuzzing are structural zeros. Do not chase them to 10.
- WCAG accessibility is followed, with limits. Gallery images have alt text. The contact iframe has a title and a fallback link. Navigation has aria labels. Controls are real buttons. Contrast, heading order, and focus have no automated check. See issue 19 for the check and issue 22 for the skip link.
- Privacy is followed, with limits. The site has no analytics, no tracking pixels, and no advertising cookies. No email is published. The site collects nothing itself. Google Forms is the only third-party, and it is disclosed. The theme preference uses localStorage, not a cookie, and it is not tracking. See issue 21 for the privacy line.
- The site threat model is not documented yet. See issue 20.
- Do not create issues for non-applicable items. That list includes port binding, processes, concurrency, disposability, admin processes, app logging, SBOM, auth hardening, SSRF, fuzzing, CII badge, SLSA, and chasing Scorecard structural zeros to 10.

## Well-known files

- `robots.txt`, `sitemap.xml` (jekyll-sitemap plugin), `security.txt` (root and `.well-known/`), `humans.txt`, `ai.txt`, `llms.txt`, `llms-full.txt`.
- `security.txt` expires 2027-10-20. Refresh it before that date.

## Do not touch

- The old `infralicious/docs` repo is private now. Leave it alone.
- Do not add a public phone number, address, or email to the site.
