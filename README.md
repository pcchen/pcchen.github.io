# pcchen.github.io

Personal academic website for Prof. Pochung Chen (陳柏中), Department of Physics, National Tsing Hua University.

Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).

## Local development

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open http://127.0.0.1:8000.

## Build

```bash
mkdocs build
```

Output is in `site/`.

## Deployment

Pushing to `master` triggers the GitHub Actions workflow (`.github/workflows/deploy.yml`), which builds the site and deploys to the `gh-pages` branch automatically.

## Structure

```
docs/
  index.md          # Home page
  cv.md             # Brief CV
  members.md        # Research group members
  publications.md   # Publication list
  Cytnx.md          # Cytnx library notes
  teaching/         # Course pages
mkdocs.yml          # MkDocs configuration
requirements.txt    # Python dependencies
```
