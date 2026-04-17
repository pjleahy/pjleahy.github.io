# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static personal site for Pat Leahy: a home page (`index.html`) and a resume page (`resume.html`) sharing a single stylesheet (`css/style.css`). No build system, no dependencies, no tests — files are served as-is.

## Local preview

Open either HTML file directly in a browser, or serve the directory:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Structure conventions

- **Two-page navigation** — both pages render the same `<header><nav>` with `index.html` and `resume.html` links. The current page's nav link must carry `class="active"` so the bold-underline style applies. When adding a new page, update the nav on every page.
- **Shared stylesheet** — all styling lives in `css/style.css`. The palette is just two CSS custom properties on `:root`: `--ink` (#262a28, obsidian dark green) for all text/borders and `--paper` (#faf8f3, cream) for all backgrounds. Use these variables rather than hard-coded colours.
- **Entry styling is deliberately minimal** — `.job-entry`, `.education-entry`, and `.voluntary-entry` share a single rule: a 2px `--ink` left border, no background fill, no accent colours. Don't reintroduce per-category accent colours. `.summary-text` and `.contact-details` are plain blocks with no border or background.
- **Resume entries** use the `article.<type>-entry > img.entry-logo + div.entry-content` shape, with `h3`, `p.dates`, `span.role`, then a description `<p>` inside `entry-content`. Logos live in `images/` and are referenced directly.
- **Footer year** is hand-maintained in each HTML file (currently inconsistent: `index.html` says 2026, `resume.html` says 2025).
