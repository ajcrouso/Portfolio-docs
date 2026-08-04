# Contributing to this portfolio

This repo is a hand-built static site (plain HTML/CSS, served by GitHub Pages at
`https://ajcrouso.github.io/portfolio/`). No build step, no framework. Every project
page follows one pattern so the site reads as a single, consistent body of work.

## The case study pattern

Every case study uses the same four-part spine, in order:

1. **Hero** — one dramatic prototype photo + a one-line outcome statement + a meta row.
2. **Design Intent** — why the product looks and works the way it does (first person, short).
3. **Engineering Depth** — the longest section; the subsystem you owned, in jumpable subsections that show your reasoning and rejected alternatives.
4. **Result & Retrospective** — did it work, and what you'd change.

- **Template + full rules:** [`templates/case-study-template.md`](templates/case-study-template.md)
- **Reference implementation (the component kit):** [`uv-food-storage.html`](uv-food-storage.html)

## Making a new case study

1. Copy `templates/case-study-template.md`, fill in the spine (respect the RULES — voice, honest attribution, real numbers).
2. Copy `uv-food-storage.html` → `<project-slug>.html`. Keep the `<head>`, nav, footer, and CSS; replace the content.
3. Put optimized images in `images/<project-slug>/` (see the template for the `magick` commands). Use relative paths only.
4. Add a project card on `index.html` linking to the new page.
5. Preview via `scratchpad/serve.ps1` (localhost:8123), then commit and push.

## Non-negotiables

- **Only claim work that was yours.** Credit the team neutrally for the rest. This is what makes the portfolio trustworthy in an interview.
- **Relative paths everywhere** (the site lives under `/portfolio/`).
- **Scannable, not bloggy.** Short paragraphs, real numbers, depth over polish.
- **Never commit `Project Data/`** — it's git-ignored (raw photos, resumes, working docs stay private).
