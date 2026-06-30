# Editing this site — start here

These guides explain how to maintain **studyztp.github.io** by hand. Read this page once to get the
mental model, then jump to the task you need.

## The 60-second mental model

- The site is **[Jekyll](https://jekyllrb.com/)** (Academic Pages template) on **GitHub Pages**.
- **Content = Markdown files with a YAML "front matter" header** (the `--- … ---` block at the top).
- You don't build anything manually. **To publish, commit and `git push` to `master`** — GitHub
  Pages rebuilds the live site automatically in a minute or two.
- To **see changes before publishing**, run the site locally — see
  **[running-locally.md](running-locally.md)**.

### Front matter, in one example

Every content file starts with a fenced block of key/value settings, then the page body:

```markdown
---
title: "My Page Title"
permalink: /my-url/
---

The page body, written in **Markdown**.
```

`permalink` is the URL the page lives at. The body is normal Markdown (headings with `##`, links
with `[text](url)`, bold with `**…**`, etc.).

## How the site is organized

| Folder / file | What it is |
|---------------|------------|
| `_publications/` | One file per paper → listed at `/publications/` |
| `_talks/` | One file per talk → listed at `/talks/` |
| `_teaching/` | One file per teaching role → listed at `/teaching/` |
| `_portfolio/` | One file per project → listed at `/portfolio/` |
| `_pages/about.md` | **The homepage** (`/`) |
| `_pages/cv.md` | The CV page (`/cv/`) |
| `_pages/` (other) | Any other standalone page |
| `_data/navigation.yml` | The header menu |
| `_config.yml` | Site-wide settings: your name, bio, photo, social links |
| `images/` | Images (your headshot, etc.) → linked as `/images/<name>` |
| `files/` | Downloadable PDFs/slides/CV → linked as `/files/<name>` |
| `.claude/skills/website/templates/` | Ready-to-copy front-matter templates |

The four collection folders (`_publications`, `_talks`, `_teaching`, `_portfolio`) and the rules
for each are declared in `_config.yml`. You rarely need to touch that wiring — just add files.

## ⚠️ The single most important rule

**Publications and talks are stored in three places, and you must keep them in sync by hand.**

When you add (or remove) a paper or talk, edit **all** of these:

1. The collection file — `_publications/…md` or `_talks/…md` *(this alone updates the
   `/publications/` and `/talks/` listing pages automatically)*
2. The homepage — `_pages/about.md` (it has its own hand-written Publications / Talks lists)
3. The CV — `_pages/cv.md` (also hand-written), then regenerate `_data/cv.json` and replace the
   PDF CV (see **[cv.md](cv.md)**)

The listing pages auto-update; **the homepage and CV do not.** Forgetting this is the #1 cause of
the site looking inconsistent.

## Pick your task

- **[publications.md](publications.md)** — add / edit / remove a paper
- **[talks.md](talks.md)** — add a talk (and how the talk-location map auto-updates)
- **[teaching-and-portfolio.md](teaching-and-portfolio.md)** — teaching roles & portfolio projects
- **[homepage-and-pages.md](homepage-and-pages.md)** — edit the homepage, add/rearrange its
  sections ("blocks"), create new pages, and manage the header menu
- **[cv.md](cv.md)** — keep the three CV forms (markdown, JSON, PDF) in sync
- **[site-settings.md](site-settings.md)** — name, bio, headshot, social links, theme, adding files
- **[running-locally.md](running-locally.md)** — preview the site and publish

## A safe workflow for any change

1. Run the site locally (`bundle exec jekyll serve -l -H localhost`) and open
   <http://localhost:4000>.
2. Make your edit; the browser refreshes automatically (restart the server only if you edited
   `_config.yml`).
3. Check it looks right locally.
4. `git add -A && git commit -m "…" && git push`.
5. If you touched a talk, `git pull` afterward to grab the bot's talk-map commit.
