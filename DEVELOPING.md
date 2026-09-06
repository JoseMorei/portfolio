# Developing this site

Static site built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).
All content is plain Markdown in `docs/`.

## Local preview

```bash
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/mkdocs serve
```

Then open <http://127.0.0.1:8000/portfolio/>. The server live-reloads on save.
It mounts under `/portfolio/` because that is the path in `site_url`.

## Layout

```
docs/
  index.md                          # landing page
  full-resume.md                    # LinkedIn + resume PDF + certification badges
  continuous-learning/
    index.md                        # section landing page
    <course>.md                     # one page per course/certification
    ai-solutions-architect-.../     # nested section (13 challenge write-ups)
  portfolio-experiments-labs/
    index.md
    <project>.md
  assets/                           # all images + Jose_Moreira_Resume.pdf
```

Navigation order is declared in `nav:` at the bottom of `mkdocs.yml` — edit that
to reorder or hide pages. Because `navigation.indexes` is enabled, each
section's `index.md` is reached by clicking the section title itself.

`README.md` deliberately mirrors `docs/index.md` so the repo landing page and
the site landing page read identically. If you edit one, edit the other; the
only difference is that `README.md` uses absolute URLs for its three links and
a `docs/`-prefixed image path.

## Editing

Ordinary Markdown. A few Material-specific niceties available:

- Admonitions: `!!! note`, `!!! warning`, `!!! tip`
- Card grids: `<div class="grid cards" markdown>` + a `-` list
- Code blocks get copy buttons and line numbers automatically

Always verify before pushing:

```bash
.venv/bin/mkdocs build --strict
```

`--strict` turns broken internal links and missing images into build failures,
which is what CI enforces too.

## Deploying

`.github/workflows/deploy.yml` builds with `--strict` and publishes to GitHub
Pages on every push to `main`. Pages is configured with the `workflow` build
type, so there is no `gh-pages` branch to maintain.

Live at <https://josemorei.github.io/portfolio/>.

### Custom domain

Free apart from the domain registration itself:

1. Add a `CNAME` file next to `mkdocs.yml` containing just your domain, e.g. `josemoreira.dev`.
2. At your registrar, point the apex `A`/`ALIAS` records at GitHub Pages, or a
   `CNAME` for `www` at `JoseMorei.github.io`. Current IPs are in
   [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
3. Repo **Settings → Pages → Custom domain**, then tick **Enforce HTTPS**.
4. Update `site_url:` in `mkdocs.yml` to match — Material uses it for canonical
   URLs and the sitemap, and `mkdocs serve` uses its path as the local mount point.
