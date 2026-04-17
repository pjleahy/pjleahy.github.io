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

- **Two-page navigation** — both pages render the same `<header><nav>` with `index.html` and `resume.html` links. The current page's nav link must carry `class="active"` so the pink-highlight style applies. When adding a new page, update the nav on every page.
- **Shared stylesheet** — all styling lives in `css/style.css`. Page-specific styles are keyed off semantic class names (`.job-entry`, `.education-entry`, `.voluntary-entry`, `.summary-text`, `.contact-details`). Each entry type has its own accent colour (Oxford blue / gold / green) following a consistent `background + border-left + border-radius` pattern — match this when adding a new entry category.
- **Resume entries** use the `article.<type>-entry > img.entry-logo + div.entry-content` shape, with `h3`, `p.dates`, `span.role`, then a description `<p>` inside `entry-content`. Logos live in `images/` and are referenced directly.
- **Footer year** is hand-maintained in each HTML file (currently inconsistent: `index.html` says 2026, `resume.html` says 2025).
