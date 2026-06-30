---
name: website
description: >-
  Use when adding, changing, removing, or previewing content or configuration on
  this Jekyll/Academic Pages site (studyztp.github.io) — publications, talks,
  teaching, portfolio, blog posts, pages, the CV, navigation menu, personal info,
  files/PDFs, styling/theme, or the talkmap/CV automation.
---

# studyztp.github.io — site maintenance guide

This is a personal academic website built on the **Jekyll / Academic Pages** template
(a detached fork of Minimal Mistakes), hosted on **GitHub Pages**. All content is
Markdown with **YAML front matter**. Deploy = push to `master`; GitHub Pages rebuilds
automatically.

> `_config.yml` is global config and is **NOT** hot-reloaded — after editing it you must
> restart `jekyll serve`. Everything else reloads live while the server runs.

Ready-to-copy front-matter skeletons live in `.claude/skills/website/templates/`
(`publication.md`, `talk.md`, `teaching.md`, `portfolio.md`, `page.md`). Copy the matching
one, fill it in, and save it to the right directory with the right filename.

## ⚠️ The #1 thing to remember (single source of truth)

The listing pages `/publications/` and `/talks/` are **auto-generated** from the collection
folders — adding a file there makes it appear automatically. **BUT** the homepage
`_pages/about.md` and the markdown CV `_pages/cv.md` keep **hand-curated copies** of the
publications and talks lists. When you add or remove a paper or a talk, you must **also edit
those two files by hand**, and consider updating the PDF CV (see [CV](#cv)). Forgetting this
is the most common way the site goes out of sync.

## Directory map

| Path | What it holds |
|------|---------------|
| `_publications/` | Publications collection (one `.md` per paper). Listing → `/publications/` |
| `_talks/` | Talks collection (one `.md` per talk; uses `layout: talk`). Listing → `/talks/` |
| `_teaching/` | Teaching collection. Listing → `/teaching/` |
| `_portfolio/` | Portfolio/projects collection. Listing → `/portfolio/` |
| `_pages/` | Standalone pages: `about.md` (homepage `/`), `cv.md`, `cv-json.md`, `404.md`, the `*.html` archive/listing pages |
| `_data/` | `navigation.yml` (header menu), `authors.yml`, `cv.json`, `ui-text.yml`, `comments/` |
| `_config.yml` | Global site config: title, author/social links, collections, defaults, plugins |
| `_layouts/` | Page templates: `default`, `single`, `talk`, `archive`, `cv-layout`, `splash` |
| `_includes/` | Reusable partials: `author-profile.html`, `archive-single*.html`, footer/head/nav, etc. |
| `_sass/` | Styles. `theme/` = light/dark colors; `layout/` = components; entry `assets/css/main.scss` |
| `assets/` | Compiled CSS/JS, fonts, webfonts |
| `images/` | Site images (avatar `my-headshot.jpg`, favicons, etc.) |
| `files/` | Downloadable PDFs/slides/CV. Served at `/files/<name>` |
| `markdown_generator/` | Python/Jupyter bulk generators (TSV/BibTeX → markdown) |
| `scripts/` | `cv_markdown_to_json.py`, `update_cv_json.sh` |
| `talkmap.py`, `talkmap/` | Talk-location map (auto-generated — don't hand-edit `talkmap/`) |
| `.github/workflows/` | CI: `scrape_talks.yml` (talkmap automation) |

The four collections are declared in `_config.yml` (the `collections:` block) and their
per-type defaults (which `layout` each uses, `author_profile`, etc.) in the `defaults:` block.

## Adding / changing / removing content

General rules:
- **Add** = create a new `.md` file in the right folder (copy the matching template).
- **Change** = edit the file in place; the front-matter `permalink` keeps the URL stable.
- **Remove** = delete the file (and remove any hand-curated mention in `about.md` / `cv.md`).
- Filenames for dated collections use `YYYY-MM-DD-slug.md`; the date prefix orders the list
  (newest first).

### Publications → `_publications/`  (template: `templates/publication.md`)
Key fields: `collection: publications`, `category:` one of `conferences` /
`manuscripts` / `books` (these map to the headings "Conference Papers" / "Journal Articles" /
"Books" defined under `publication_category` in `_config.yml`), `date`, `venue`, `paperurl`,
`citation`, `excerpt`. Permalink convention: `/publication/<slug>`.
Real examples: `_publications/2026-01-31-nugget.md`, `_publications/2025-01-08-looppoint.md`.

### Talks → `_talks/`  (template: `templates/talk.md`)
Uses `layout: talk` automatically. Key fields: `collection: talks`, `type` (free text —
existing values: "Main Conference", "Workshop", "Tutorial"), `date`, `venue`, `location`,
`excerpt`. **`location` is geocoded by the talkmap automation** — use a real "City, Country".
Slides: upload the PDF to `files/` and link it in the body as `/files/<name>.pdf`.
Real examples: `_talks/2026-01-31-hpca-nugget.md`, `_talks/2026-02-22-cgo-nugget.md`.

### Teaching → `_teaching/`  (template: `templates/teaching.md`)
Key fields: `collection: teaching`, `type`, `date`, `venue`, `location`, `excerpt`.
Real example: `_teaching/2024-winter-ecs154b.md`.

### Portfolio → `_portfolio/`  (template: `templates/portfolio.md`)
Slug-named (no date needed). Key fields: `collection: portfolio`, `excerpt`.
Currently just `_portfolio/under-construction.md`.

### Pages → `_pages/`  (template: `templates/page.md`)
Set `layout`, `permalink`, `title`. To surface a page in the header, add it to
`_data/navigation.yml`. The homepage is `_pages/about.md` (`permalink: /`).

### Blog posts (not currently active)
There is no `_posts/` directory yet. To enable a blog: create `_posts/`, add files named
`YYYY-MM-DD-title.md` (post defaults already exist in `_config.yml`). The nav already has
"Blog Posts" → `/year-archive/`.

## CV

Three representations — **keep them in sync** when CV content changes:
1. `_pages/cv.md` — the live **markdown CV** (the one linked in the nav), served at `/cv/`.
   This is the primary, hand-edited source.
2. `_data/cv.json` — **JSON Resume** data, *regenerated from* `cv.md` by running
   `bash scripts/update_cv_json.sh` (wraps `scripts/cv_markdown_to_json.py`). Powers the
   alternative `/cv-json/` page (`_pages/cv-json.md`), which is currently commented out in nav.
   Don't hand-edit `cv.json`; regenerate it.
3. `files/Zhantong_Qiu_CV.pdf` — the **downloadable PDF** (linked from `about.md` and `cv.md`).
   Replace this file manually when the CV changes.

## Navigation / header menu

Edit `_data/navigation.yml` (`main:` list) to add, reorder, or hide header links. Removing an
entry only hides it from the menu — the page still exists. Note the two CV options at the
bottom (markdown `/cv/` vs json `/cv-json/`); keep exactly one uncommented.

## Personal info & site settings

All in `_config.yml` under `author:` — `name`, `bio`, `location`, `employer`, `email`,
`avatar` (`images/my-headshot.jpg`), and every social/academic link (a field left blank hides
its icon). Site `title` / `description` / `url` are at the top of the file. Publication
category headings are under `publication_category:`. **Restart the server after editing.**

## Files & images

- PDFs/slides/CV → `files/`, referenced as `/files/<name>`.
- Images → `images/`, referenced as `/images/<name>`.
- Use root-relative paths (leading `/`) so links work from any page.

## Styling / theme

- Colors & light/dark themes: `_sass/theme/_default.scss`, `_sass/theme/_dark.scss`;
  theme-switching logic in `_sass/_themes.scss`.
- Component styles (masthead, sidebar, archive cards, buttons, footer…): `_sass/layout/`.
- Everything is imported by `assets/css/main.scss` (Sass output is `compressed`).
- Layouts in `_layouts/`; reusable HTML partials in `_includes/` (e.g. the bio box is
  `author-profile.html`; listing cards are `archive-single*.html`).

## Build, preview & deploy

Local preview (auto-reloads on change, except `_config.yml`):
```bash
bundle install                              # first time
bundle exec jekyll serve -l -H localhost    # → http://localhost:4000
```
Alternatives: `docker compose up`, or the VS Code DevContainer (both serve on :4000).
See `README.md` for dependency-install troubleshooting.

Deploy: commit and `git push` to `master`; GitHub Pages builds and publishes automatically.

## Automation

- **Talkmap** — pushing any change under `_talks/` triggers
  `.github/workflows/scrape_talks.yml`, which runs the talkmap notebook to geocode each talk's
  `location` and **auto-commits** "Automated update of talk locations" (updating `talkmap/`).
  So: just set a correct `location`; don't hand-edit `talkmap/`, and expect a follow-up bot
  commit after you push a talk.
- **Bulk content** — `markdown_generator/` has Python/Jupyter tools to generate many
  publication or talk `.md` files from a spreadsheet or BibTeX: `publications.py` (from
  `publications.tsv`), `talks.py` (from `talks.tsv`), `pubsFromBib.py` / `OrcidToBib.ipynb`.

## Common task recipes

**Add a conference paper**
1. Copy `templates/publication.md` → `_publications/YYYY-MM-DD-slug.md`; fill front matter
   (`category: conferences`, `venue`, `paperurl`, `citation`, `excerpt`) + body.
2. If there's a PDF/slides, drop them in `files/` and link as `/files/<name>.pdf`.
3. Add the paper to the lists in `_pages/about.md` **and** `_pages/cv.md`.
4. (If the CV changed) run `bash scripts/update_cv_json.sh`; update `files/Zhantong_Qiu_CV.pdf` if needed.
5. Preview locally, then commit & push.

**Add a talk**
1. Copy `templates/talk.md` → `_talks/YYYY-MM-DD-slug.md`; set `type`, `venue`, real
   `location`, `excerpt`. Upload slides to `files/` and link them.
2. Add the talk to `_pages/about.md` and `_pages/cv.md`.
3. Preview, commit & push — the talkmap bot will then auto-commit the updated map.

**Change personal info / a social link** → edit `author:` in `_config.yml`, then **restart** the server.

**Add a page to the menu** → create `_pages/<slug>.md` (template `page.md`) + add an entry in `_data/navigation.yml`.

**Update the CV** → edit `_pages/cv.md` → `bash scripts/update_cv_json.sh` → replace `files/Zhantong_Qiu_CV.pdf` → verify `about.md` still matches.
