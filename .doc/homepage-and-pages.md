# Homepage, sections ("blocks") & pages

This covers editing the homepage, rearranging or adding its sections, creating brand-new pages, and
controlling the header menu.

---

## Edit the homepage

The homepage is **`_pages/about.md`** (its `permalink` is `/`). Open it and edit the Markdown body —
the browser refreshes automatically when you save (if the local server is running).

The front matter at the top rarely needs changing:

```markdown
---
permalink: /
title: "Zhantong Qiu - Computer Systems Researcher"
author_profile: true        # shows the bio sidebar (photo + name + links)
redirect_from:
  - /about/
  - /about.html
---
```

`author_profile: true` is what shows the **left sidebar** (your photo, name, and social icons). The
content of that sidebar comes from `_config.yml`, not this page — see
**[site-settings.md](site-settings.md)**.

## Add, remove, or reorder homepage sections ("blocks")

Each "block" on the homepage is just a Markdown section started by a `##` heading. The current
homepage has these blocks, in order:

```markdown
## Current Work
## Research Interests
## Publications
## Talks
```

To work with blocks in `_pages/about.md`:

- **Add a block:** insert a new `## My New Section` heading and write content under it.
- **Reorder blocks:** cut and paste the whole `## …` section to a new position.
- **Remove a block:** delete the heading and its content.
- **Rename a block:** change the text after `##`.

> The **Publications** and **Talks** blocks are hand-maintained lists. Keep them in sync when you
> add papers/talks — see [publications.md](publications.md) and [talks.md](talks.md).

Inside a block you can use any Markdown: subheadings (`###`), bullet lists (`-`), **bold**, links
`[text](/url)`, images `![alt](/images/file.png)`, etc.

---

## Add a brand-new page

Use this for pages that aren't part of a collection (e.g. a "Contact" or "Research" page).

1. Copy `.claude/skills/website/templates/page.md` into `_pages/`, e.g. `_pages/research.md`.
2. Set the front matter:

   ```markdown
   ---
   layout: single          # or: archive (used by cv.md), splash
   title: "Research"
   permalink: /research/    # the page will live at this URL
   author_profile: true     # show the bio sidebar; set false to hide it
   ---
   ```
3. Write the page body in Markdown.
4. (Optional) Add it to the header menu — see below.
5. Preview at `http://localhost:4000/research/`, then commit & push.

`layout` options: `single` (standard page with sidebar), `archive` (used for list-style pages like
the CV), `splash` (full-width landing style).

---

## The header menu (navigation)

The top navigation bar is controlled by **`_data/navigation.yml`**, in the `main:` list:

```yaml
main:
  - title: "Publications"
    url: /publications/
  - title: "Talks"
    url: /talks/
  - title: "Teaching"
    url: /teaching/
  - title: "Portfolio"
    url: /portfolio/
  - title: "Blog Posts"
    url: /year-archive/
  - title: "CV"
    url: /cv/
  # - title: "CV"
  #   url: /cv-json/
```

- **Add a link:** add a `- title: / url:` pair.
- **Reorder:** move the pairs up/down — the order here is the order in the menu.
- **Hide a link:** delete (or comment out with `#`) its pair. The page still exists; it's just not
  in the menu.
- **Note the two CV entries:** keep exactly **one** uncommented (the markdown `/cv/` version is the
  active one; the `/cv-json/` version is an alternative — see [cv.md](cv.md)).

---

## Blog posts (not currently enabled)

There's no `_posts/` folder yet, so the blog is inactive (the "Blog Posts" menu link points to an
empty archive). To enable a blog later: create a `_posts/` folder and add files named
`YYYY-MM-DD-title.md`. Post defaults are already configured in `_config.yml`.
