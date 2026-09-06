# Jose Moreira — portfolio

Static portfolio site built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).
Migrated off Notion; all content is plain Markdown in `docs/`.

## Local preview

```bash
python3 -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/mkdocs serve
```

Then open <http://127.0.0.1:8000>. The server live-reloads on save.

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

The site tree mirrors the old Notion page hierarchy 1:1. Navigation order is
declared in `nav:` at the bottom of `mkdocs.yml` — edit that to reorder or hide
pages. Because `navigation.indexes` is enabled, each section's `index.md` is
reached by clicking the section title itself.

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

## Deploying to GitHub Pages (free)

1. Create a public repo (e.g. `JoseMorei/portfolio`) and push this directory to `main`.
2. Repo **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Push. `.github/workflows/deploy.yml` builds with `--strict` and publishes.

Site lands at `https://JoseMorei.github.io/portfolio/`.

### Custom domain

Free apart from the domain registration itself:

1. Add a `CNAME` file next to `mkdocs.yml` containing just your domain, e.g. `josemoreira.dev`.
2. At your registrar, point the apex `A`/`ALIAS` records at GitHub Pages, or a
   `CNAME` for `www` at `JoseMorei.github.io`. Current IPs are in
   [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).
3. Repo **Settings → Pages → Custom domain**, then tick **Enforce HTTPS**.
4. Update `site_url:` in `mkdocs.yml` to match — Material uses it for canonical
   URLs and the sitemap.

## Re-running the Notion migration

The one-off scripts that generated `docs/` live in the parent directory
(`crawl.py`, `fetch_assets.py`, `convert.py`, `sync_nav.py`). They are **not**
part of the site and are not needed again unless you want to re-pull from Notion.
Note that `convert.py` deletes and regenerates all of `docs/`, so once you start
editing Markdown by hand, stop running it.
