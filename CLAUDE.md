# CLAUDE.md

## Project overview

Academic website for Prof. Pochung Chen's Qubit research group at NTHU.
Built with MkDocs Material, deployed to GitHub Pages via GitHub Actions.

## Commands

```bash
# Install dependencies
pip install -r requirements.txt

# Local preview
mkdocs serve

# Build static site
mkdocs build

# Deploy to gh-pages branch manually
mkdocs gh-deploy --force
```

## Structure

- `docs/` — all content pages (markdown)
- `docs/teaching/` — course pages
- `mkdocs.yml` — site config and navigation
- `requirements.txt` — Python dependencies
- `.github/workflows/deploy.yml` — auto-deploy on push to master

## Adding content

- New pages go in `docs/`
- Add them to the `nav:` section of `mkdocs.yml`
- MathJax is enabled via `pymdownx.arithmatex` — use `$...$` for inline and `$$...$$` for display math

## Deployment notes

GitHub Pages source must be set to the `gh-pages` branch in repo settings.
The workflow pushes built HTML there on every push to `master`.
