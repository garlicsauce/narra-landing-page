# Repository Guidelines

## Project Structure & Module Organization
This repository is a static, multilingual landing page. The English page lives at `index.html`; localized variants are in `pl/`, `de/`, `es/`, and `fr/`. Shared visual rules live in `styles.css`, while each HTML page also contains critical styles and inline JavaScript for navigation, language switching, the workflow tabs, and beta-form submission. Store images and icons in `assets/`. Netlify redirects and local hosting settings are defined in `netlify.toml`.

When changing content, pricing, tracking, or interactive behavior, review all five HTML pages. Root-page asset paths use `assets/...`; localized pages use `../assets/...`.

## Build, Test, and Development Commands
There is no compilation step or package manifest.

- `python3 -m http.server 8000` serves the site locally for basic browser checks.
- `netlify dev` serves the repository with Netlify behavior when the Netlify CLI is installed.
- `git diff --check` catches whitespace errors before committing.

Use `http://localhost:8000/`, then visit `/pl/`, `/de/`, `/es/`, and `/fr/`.

## Coding Style & Naming Conventions
Keep the existing formatting: four-space indentation in HTML and inline JavaScript, two-space indentation in `styles.css`, lowercase kebab-case CSS classes such as `.language-trigger`, and semantic section IDs such as `#pricing`. Prefer shared styles in `styles.css`; keep page-specific critical styles minimal. Preserve accessible labels, focus states, `aria-*` relationships, and the Netlify honeypot field when editing forms.

## Testing Guidelines
No automated test suite is configured. Manually verify desktop and mobile layouts, menu toggling, language selection, workflow tabs, anchor links, and all beta forms. Use `netlify dev` for form-submission checks because a basic Python server cannot emulate Netlify Forms. Confirm tracking edits consistently across localized pages.

## Commit & Pull Request Guidelines
Recent commits use short, imperative subjects, for example `Align localized footers with default layout (#12)`. Keep each commit focused. Pull requests should summarize affected locales, list manual checks, link the relevant issue, and include screenshots for visible layout changes.

## Agent-Specific Instructions
Use `codebase-memory-mcp` graph tools first for code discovery: `search_graph`, `trace_path`, `get_code_snippet`, then `query_graph` or `get_architecture`. Fall back to `rg` for literal strings, configuration, and other non-code files.
