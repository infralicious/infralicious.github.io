# Infralicious website and TrueTime docs

Org site for Infralicious, served at https://infralicious.github.io/.
It hosts the public documentation for TrueTime for Jira.

Published with GitHub Pages (Jekyll, minima theme, no build step).

Live site: https://infralicious.github.io/

## Pages

- `index.md` — Overview, features, links.
- `user-guide.md` — Log time, approvals, teams, admin settings.
- `migration.md` — Migrate from Tempo via CSV only.
- `privacy.md` — Public privacy policy.
- `terms.md` — Terms of service.
- `support.md` — How to get help.

## How to edit docs

1. Edit a Markdown file in this repo.
2. Keep ASD-STE100 style: short sentences, active voice, one idea each.
3. Do not promise features TrueTime does not have.
4. Commit and push to `main`. GitHub Pages rebuilds the site.

## Note

The old repo `infralicious/docs` (https://infralicious.github.io/docs/)
is superseded by this repo. Do not delete it yet. It stays as an
archive until the Marketplace listing points at the new URLs.

## TODO

- [ ] Point infralicious.com DNS at GitHub Pages (A records / CNAME).
- [ ] Add a `CNAME` file with `infralicious.com` only after DNS is set.
      Do not add CNAME early. It would break the github.io URL.
- [ ] Update the Marketplace listing to point at the new docs URLs.
