# openkoutsi-docs

User-facing documentation for [openkoutsi](https://github.com/openkoutsi), the
self-hosted cycling coaching platform.

This site explains how to **use** openkoutsi's features. It is a user guide, not a
developer or API reference. It is built with [MkDocs](https://www.mkdocs.org/) and
the [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) theme, and
published to GitHub Pages.

📖 **Live site:** <https://openkoutsi.github.io/openkoutsi-docs/>

## Working on the docs locally

This repo uses [uv](https://docs.astral.sh/uv/) (Python 3.12).

```bash
# Install dependencies
uv sync

# Serve with live reload at http://127.0.0.1:8000
uv run mkdocs serve

# Production build (strict — fails on broken links / nav)
uv run mkdocs build --strict
```

## Structure

```
docs/                 Markdown content
  index.md            Landing / overview
  getting-started.md  First steps for a new user
  features/           One page per feature area
  faq.md
  assets/             Logo and favicon
mkdocs.yml            Site configuration
```

## Deployment

Pushes to `main` trigger the **Deploy docs** GitHub Actions workflow
(`.github/workflows/deploy.yml`), which builds the site and publishes it to GitHub
Pages. Pull requests run a strict build (`.github/workflows/ci.yml`) to catch
broken links and navigation before merge.

> **One-time setup:** in the repository's **Settings → Pages**, set the build and
> deployment **Source** to **GitHub Actions**.

## Contributing

Add or edit Markdown under `docs/`, update the `nav` in `mkdocs.yml` if you add a
page, and run `uv run mkdocs build --strict` before opening a pull request.

## License

Apache-2.0.
