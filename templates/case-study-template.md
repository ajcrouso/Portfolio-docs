<!--
  CASE STUDY TEMPLATE  ·  portfolio scaffold
  Reference implementation: /uv-food-storage.html
  Copy this file to templates/drafts/<project-slug>.md, fill it in, then build the
  HTML page from /uv-food-storage.html (that file IS the component kit).

  This is written to future-Aidan. Read the RULES first, then fill the SPINE.
-->

# Case Study Template

## RULES (don't skip — this is the whole point)

**Voice**
- First person, past tense. You are talking to a hiring manager, not writing a blog.
- Scannable over wordy. Short paragraphs (2–4 sentences). Lead each subsection with the point, then support it. If a paragraph is longer than ~4 lines, cut it or make it a list.
- No AI-tells: no em dashes, no "it's not just X, it's Y", no rule-of-three padding, no inflated adjectives.
- Depth over polish. An engineer should finish the Engineering section knowing *how you think*, not just what the product does.

**Attribution (non-negotiable — this is what makes it trustworthy)**
- Only claim what was yours. Write your reasoning and decisions in first person where the work was yours.
- For work that wasn't yours, use neutral phrasing ("the team built…", "a teammate designed…"). You don't have to name who — just don't claim it.
- If a doc/resume line overstates your role, the case study wins. Interviewers drill into this; an honest, narrower claim beats an impressive one you can't defend.

**Evidence**
- Quantify everything quantifiable (specs, run time, part counts, cost, FOS, cycles).
- Don't invent numbers. If you need one you don't have, write `[NEED: …]` and fill it before publishing.
- Prototype photos beat renders. Use one clean render only for architecture/exploded views. Real "guts" photos are good even when messy — they read as authentic.

**Images**
- Live in `/images/<project-slug>/`. Reference with relative paths (the site deploys under `/portfolio/`, so never use leading-slash absolute paths).
- Optimize before committing: `magick in.jpg -auto-orient -resize "1600x1600>" -strip -interlace Plane -quality 82 out.jpg` (photos), quality 88–90 for renders.
- Render on a white/transparent background? Flatten it and use the `.fig.light` card: `magick in.png -fuzz 12% -fill "#ececec" -opaque white -background "#ececec" -flatten out.jpg`.

---

## SPINE (four parts, always in this order)

### 1 · HERO
> One dramatic prototype photo + a one-line outcome statement + a meta row.
> The one-liner states the *outcome* and *your scope*, not the process.

- **Kicker:** `Case Study · <Category>`
- **Title:** `<Project Name>`
- **Lead (1–2 sentences):** what it does + the part you owned.
- **Hero image:** the single best shot. Dramatic > tidy.
- **Meta row:** Context · Team · My scope · Read time.

### 2 · DESIGN INTENT
> Why the product looks and works the way it does. First person.
> Keep it short — this is framing, not the main event. 2–3 tight paragraphs or a decision list.

- What was the brief / the real problem (not the assignment)?
- The 2–4 top-level decisions that shaped everything (form factor, key constraint, what differentiates it).
- End by pointing at the subsystem you owned → hands off to section 3.

### 3 · ENGINEERING DEPTH  *(the longest section — this is the case study)*
> Your scope, in subsections a technical reader can jump between.
> Each subsection = one decision or problem. Show the reasoning and the alternatives you rejected.

Suggested subsections (adapt per project):
- **The constraint** — what made this hard (environment, packaging, tolerance, cost). Bullet it.
- **The core decision(s)** — what you chose, why, and what you rejected and why. This is where "how you think" lives.
- **The numbers** — a spec block and/or table. Real values.
- **A diagram** — block diagram, stack-up, gear train, power chain. Build it in HTML (see `.chain`) or embed a clean figure.
- **Validation / integration** — how you proved it, or how it fit with the rest of the system.
- Mark any boundary that wasn't your work with a neutral "not my work" callout.

### 4 · RESULT & RETROSPECTIVE
> Did it work, and what you'd change. Honest.

- **Result:** the outcome, ideally a before/after or a measured number.
- **What I'd redesign:** 2–3 concrete next steps. Framing untested things as "next step" is honest and fine.
- **What I took from it:** what you actually learned (skills, cross-functional, judgment). In your words.

---

## HTML / NAV / CONFIG CONVENTIONS

- **Filename:** `<project-slug>.html` at repo root (e.g. `engine-stay-redesign.html`).
- **Build from:** copy `/uv-food-storage.html` — it holds every component (hero, `figure.fig` / `.fig.light`, `.callout` / `.callout.team`, `.spec`, `.chain`, `table.dt`, `.berries`) and the full CSS. Swap the content, keep the shell.
- **Head:** set `<title>`, `<meta name="description">`, and keep the three favicon `<link>`s.
- **Nav:** brand → `index.html`, back link → `index.html#work`.
- **Link it:** add a project card on `index.html` (`<a class="project" href="<slug>.html">`) with a thumbnail from `/images/<slug>/`.
- **Paths:** always relative. The site is served from `https://ajcrouso.github.io/portfolio/`.
- **Preview locally:** the in-app preview can't switch between local file:// pages. Run `scratchpad/serve.ps1` (PowerShell static server on :8123) and open `http://localhost:8123/<slug>.html`.

## Backlog of strong candidates (from resume/portfolio)
- **Engine Stay Redesign** — production Honda part, plug-and-play, CAE FOS 1.7/1.2/1.4, 5-revision design evolution, passed 6-evaluator review. Strong individual-ownership engineering story.
- **Rambo Roller Redesign** — 35 → 8 parts, doubled durability, installed on a live production line (1,000+ impacts/day). Impact + simplicity, and it shipped.
- **Brake Dynamometer** — MATLAB AGMA screen over 13,000+ gears, ground-vs-hardened cost trade study. Computational + tradeoff depth.
