# Infralicious website

Org site for Infralicious, served at https://infralicious.github.io/.
Published with GitHub Pages (Jekyll, minima theme, no build step).

Live site: https://infralicious.github.io/

## Structure

- `index.md` — Generic company landing page. Products list, contact.
- `truetime/` — All TrueTime for Jira docs.
  - `truetime/index.md` — TrueTime home, features, links.
  - `truetime/user-guide.md` — Log time, approvals, teams, admin settings.
  - `truetime/migration.md` — Migrate from Tempo via CSV only.
  - `truetime/privacy.md` — Public privacy policy.
  - `truetime/terms.md` — Terms of service.
  - `truetime/support.md` — How to get help.
- Future apps get their own subdirectory, same pattern.

## How to edit docs

1. Edit a Markdown file in this repo.
2. Keep ASD-STE100 style: short sentences, active voice, one idea each.
3. Do not promise features the app does not have.
4. Commit and push to `main`. GitHub Pages rebuilds the site.

## Note

The old repo `infralicious/docs` (https://infralicious.github.io/docs/)
is superseded by this repo. Do not delete it yet. It stays as an
archive until the Marketplace listing points at the new URLs.

## TODO

- [ ] Point infralicious.com DNS at GitHub Pages (A records / CNAME).
- [ ] Add a `CNAME` file with `infralicious.com` only after DNS is set.
      Do not add CNAME early. It would break the github.io URL.
- [ ] Update the Marketplace listing to point at the new docs URLs
      (now under `/truetime/`).
