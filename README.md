# Infralicious website

[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/infralicious/infralicious.github.io/badge)](https://securityscorecards.dev/viewer/?uri=github.com/infralicious/infralicious.github.io)

Public site for Infralicious, served at https://infralicious.com/.
Built with Jekyll and the Minimal Mistakes theme, hosted on GitHub Pages.
TrueTime docs live under `/truetime/`.

Agent instructions live in [AGENTS.md](AGENTS.md).

## Local build

```sh
bundle install
bundle exec jekyll serve
```

## Checks

- Link check runs on every push (htmlproofer).
- Scorecard runs on push and weekly.
- Renovate owns dependency updates.

License: MIT. See [LICENSE](LICENSE).
