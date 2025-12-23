# Copilot instructions — Table project

Purpose
- Small static site demonstrating HTML tables and a minimal stylesheet.

Big picture
- Single-page static site: main files are `index.html` and `styles.css` in the repository root.
- No build tools, no JavaScript. The site is intended to be opened in a browser or served from a static host.

What to change and why
- Preserve semantic HTML: tables use `<thead>` and `<tbody>`; keep that structure when editing rows.
- Prefer modifying `styles.css` instead of changing inline markup or adding inline styles.
- When adding new styling, create CSS classes (for example, add `class="song-table"` to a `<table>` and target `.song-table` in `styles.css`).
- Avoid introducing frameworks or build systems — this repo targets simplicity.

Key files/examples
- `index.html` — contains two example tables (Christian and Secular songs) using `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, `<td>`.
- `styles.css` — global stylesheet; notable rules:
  - `html { background-color: yellow; }` sets the page background.
  - `table { width: max-content; margin: 0 auto; border-collapse: collapse; }` centers tables and collapses borders.
  - `th` and `td` are styled globally (fonts, borders, background colors). Prefer scoped classes if adding new table types.

Developer workflow
- Local preview options (choose one):
  - VS Code Live Server extension (recommended for instant reload).
  - From project root: `python -m http.server 8000` then open `http://localhost:8000`.
  - Or: `npx serve .` (if Node is available).

Testing, linting, PRs
- There are no automated tests or linters configured. Use an HTML validator (validator.w3.org) for markup checks.
- PR guidance: keep changes minimal and semantic. If changing layout, update `styles.css` and add a short note in the PR explaining the visual change.

Integration points and external deps
- None: repository contains only static assets. If you add tooling (prettier, linter), include config files at repo root.

Examples for common agent tasks
- To add a new column to both tables: update the header rows in `index.html` and add corresponding `<td>` cells in each `<tr>`; then add CSS rules for the new column selector or a scoped class.
- To restyle only the second table: add `class="sec-table"` to the second `<table>` and target `.sec-table th` / `.sec-table td` in `styles.css`.

If anything here is unclear or you'd like different conventions (e.g., add a build step or linting), tell me which direction you prefer and I will update this file.
