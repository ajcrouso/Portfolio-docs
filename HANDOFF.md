# Portfolio — Handoff

_Last updated: 2026-08-04_

Pick-up-where-we-left-off notes for the portfolio site.

- **Live:** https://ajcrouso.github.io/portfolio/
- **Repo:** `github.com/ajcrouso/portfolio` (renamed from `portfolio-docs`)
- **Hosting:** GitHub Pages, deploy from `main` / root (confirmed active). Plain static HTML/CSS, no build step.

---

## What's live right now

| Page | File | State |
|------|------|-------|
| Landing | `index.html` | Done. Hero, About, Expertise, Work (UV only), Contact, footer nav. |
| UV case study | `uv-food-storage.html` | Done. The reference implementation. |
| Experience | `experience.html` | Done. Current role + 2 internships + 2 degrees + résumé link. |
| Design Inspiration | `inspiration.html` | **Mockup, live but unfinished** — see open items. |

- **Favicon:** gold "A" monogram — `favicon.svg` / `favicon.ico` / `apple-touch-icon.png` (root).
- **Nav:** the two extra pages are linked from the homepage footer (Experience · Design Inspiration · Résumé).

---

## Open items (next time)

1. **Design Inspiration polish.** Right now the book covers are designed CSS placeholders and the people (Dyson, Honda) use initials avatars. To finish:
   - Drop real book covers + portrait photos into `images/inspiration/`, then wire them into `inspiration.html`.
   - Confirm the author/exact title of **_A History of Great Inventions_** (left blank).
   - Verify the exact published wording of the Dyson ("5,127 prototypes…") and Honda ("Success is 99 percent failure.") quotes.
   - Keep it **small and static**. The moment it grows a posts feed / update cadence, it's working against you. It's a taste signal, not a blog.
2. **Next case study.** UV is intentionally the only project — it's the one that shows real product-design intent. The plan is to add stronger product-design stories over the next couple years and eventually replace it. Use `templates/case-study-template.md`. **Do not** turn the Honda/FSAE résumé projects into case studies (deliberate — they stay on the résumé only).
3. **UV loose end.** The cold/refrigerated battery run-time was never measured (removed from the page, reframed as a "what I'd redesign"). If it ever gets tested, add the number to §2 of `uv-food-storage.html`.

---

## How the site works (conventions)

**The case study spine (always):** Hero → Design Intent → Engineering Depth → Result. Full rules + fill-in scaffold in [`templates/case-study-template.md`](templates/case-study-template.md); pattern doc in [`CONTRIBUTING.md`](CONTRIBUTING.md).

**Non-negotiables**
- **Voice:** first person, scannable (short paragraphs, real numbers), not bloggy. No em dashes / AI-isms.
- **Attribution:** only claim work that was yours; credit the team neutrally otherwise. This is what makes it trustworthy in an interview.
- **Relative paths only** — the site lives under `/portfolio/`, so a leading-slash path (`/assets/…`) will 404.
- **Never commit `Project Data/`** — it's git-ignored (raw photos, resumes, working docs stay private).

**Making a new case study**
1. Copy `templates/case-study-template.md`, fill in the spine.
2. Copy `uv-food-storage.html` → `<slug>.html` (it's the component kit: hero, `figure.fig`/`.fig.light`, `.callout`/`.callout.team`, `.spec`, `.chain`, `table.dt`, `.berries`). Keep the head/nav/footer/CSS, swap the content.
3. Optimize images into `images/<slug>/`:
   `magick in.jpg -auto-orient -resize "1600x1600>" -strip -interlace Plane -quality 82 out.jpg`
   (white-bg renders: `-fuzz 12% -fill "#ececec" -opaque white -background "#ececec" -flatten`)
4. Add a project card on `index.html`.
5. Preview, then commit + push.

**Preview locally** — the in-app browser can't switch between local `file://` pages, so run a static server:
`powershell -File scratchpad/serve.ps1` → open `http://localhost:8123/<page>.html`
(That script is in the session scratchpad; recreate it as a simple `System.Net.HttpListener` on :8123 serving the repo root if it's gone.)

---

## Tooling / environment notes
- **ImageMagick** is installed: `C:\Program Files\ImageMagick-7.1.2-Q16-HDRI\magick.exe`.
- **`gh` (GitHub CLI) is NOT installed**, and the session's auto-approval blocks credential/API git operations and `winget` installs. Repo-level GitHub actions (rename, settings) have to be done by hand in the GitHub web UI.
- Claude keeps a persistent **memory** for this project that loads at the start of every chat, so a new conversation still knows the project state. Context does **not** otherwise carry between separate chats — if something matters, say "remember this."
