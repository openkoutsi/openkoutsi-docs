# Agents.md

This repository holds the **user-facing** documentation for openkoutsi, built with
MkDocs + Material and published to GitHub Pages.

## Scope

- This is a **user guide**: explain how to *use* each component and feature.
- It is **not** a developer or API reference. Keep deployment/API internals in the
  main `openkoutsi` repository.

## Content conventions

- Content lives in `docs/` as Markdown. Add one page per feature area.
- When you add a page, add it to the `nav` in `mkdocs.yml`.
- Keep the language end-user oriented and concise. Use admonitions
  (`!!! note`, `!!! tip`, `!!! info`) for asides.
## Localisation

- The site is localised with the [`mkdocs-static-i18n`](https://github.com/ultrabug/mkdocs-static-i18n)
  plugin in **suffix** mode. English is the default language and lives in the
  un-suffixed pages (`docs/index.md`, …); Finnish lives in `.fi.md` siblings
  (`docs/index.fi.md`, …). To translate a page, add a `<page>.fi.md` next to the
  English file with the same structure. Pages without a `.fi.md` automatically fall
  back to English, so partial translations are fine.
- Keep internal links pointing at the un-suffixed `.md` targets (e.g.
  `[…](features/activities.md)`) in both languages — the plugin rewrites them to the
  reader's language.
- When you add a page, add the un-suffixed file to the `nav` and add a Finnish title
  for it under the `fi` locale's `nav_translations` in `mkdocs.yml`.

## Before pushing

Always build the docs and make sure they pass strictly:

```console
uv run mkdocs build --strict
```

`--strict` fails on broken links and missing nav entries, which is exactly what CI
checks on pull requests. Fix any warnings before opening a PR.

To preview locally with live reload:

```console
uv run mkdocs serve
```

## Deployment

`main` is deployed automatically to GitHub Pages by `.github/workflows/deploy.yml`.
Pull requests are validated by `.github/workflows/ci.yml`. Keep the `README.md` up
to date when changing how the build or deployment works.
