# Personal info, social links, photo, theme & files

Your name, bio, headshot, and social links all live in **`_config.yml`**. Images go in `images/`,
and downloadable files (PDFs, slides) go in `files/`.

> ⚠️ **`_config.yml` is the one file that does NOT auto-reload.** After editing it, **stop and
> restart** `jekyll serve` to see your changes. Every other file reloads live.

---

## Name, bio, photo & social links

These come from the **`author:`** block in `_config.yml`. A field left **blank** simply hides its
icon/line — so to remove a social link, clear its value; to add one, fill it in.

```yaml
author:
  avatar           : "my-headshot.jpg"     # file in images/  → images/my-headshot.jpg
  name             : "Zhantong Qiu"
  bio              : "Computer systems researcher focusing on performance evaluation…"
  location         : "Ithaca, New York"
  employer         : "UC Davis & Cornell University"
  email            : "studyztp@gmail.com"

  # Academic
  googlescholar    : "https://scholar.google.com/citations?user=aT--4hoAAAAJ&hl=en"
  orcid            : # URL — fill in to show the icon
  arxiv            : # URL

  # Code & social (most take a username, not a full URL — see the comments in _config.yml)
  github           : "studyztp"
  linkedin         : "zhantong-qiu-60165a165"
  twitter          : # X/Twitter username
```

The `author:` block has many more optional fields (Bluesky, Mastodon, ResearchGate, Instagram,
YouTube, …). Open `_config.yml` and search for `author:` — each line has a comment telling you
whether it wants a **username** or a **full URL**.

### Changing your headshot

1. Put the new image in `images/` (e.g. `images/my-headshot.jpg`).
2. Point `author: avatar:` at it (just the filename, relative to `images/`).
3. Restart the server.

---

## Site title & description

Near the top of `_config.yml`:

```yaml
title       : "Zhantong Qiu / Computer Systems Researcher"   # browser tab + masthead
description : "Computer architecture researcher focusing on performance evaluation…"
url         : https://studyztp.github.io
```

## Publication section headings

The headings used on `/publications/` are defined here:

```yaml
publication_category:
  conferences:
    title: 'Conference Papers'
  manuscripts:
    title: 'Journal Articles'
  books:
    title: 'Books'
```

Each publication's `category:` field selects one of these — see [publications.md](publications.md).

---

## Adding files & images

| You have… | Put it in… | Link it as… |
|-----------|------------|-------------|
| A PDF, slides, CV | `files/` | `/files/<name>.pdf` |
| An image (figure, logo, headshot) | `images/` | `/images/<name>.png` |

Always use a **leading `/`** (root-relative path) so the link works from any page. Example in a talk
body: `[Slides](/files/My-Slides.pdf)`.

---

## Theme & colors (advanced)

You usually won't need this, but if you want to tweak appearance:

- **Colors / light & dark themes:** `_sass/theme/_default.scss` (light) and `_sass/theme/_dark.scss`
  (dark); the switching logic is in `_sass/_themes.scss`.
- **Component styles** (masthead, sidebar, buttons, footer, listing cards): `_sass/layout/`.
- Everything is imported by `assets/css/main.scss`.
- **Layouts** (page structures) are in `_layouts/`; reusable HTML snippets are in `_includes/`
  (e.g. the bio sidebar is `_includes/author-profile.html`).

Edit Sass with care and always preview locally before pushing.
