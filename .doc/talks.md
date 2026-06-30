# Adding & editing a talk

Talks live in **`_talks/`** — one Markdown file per talk. The `/talks/` listing page is generated
automatically, and there is a **talk-location map** that updates itself (see
[Automation](#automation-the-talk-map-updates-itself)).

> ⚠️ **Remember the three places.** The file below feeds `/talks/` only. You must **also** add the
> talk by hand to `_pages/about.md` and `_pages/cv.md`.

---

## Add a new talk

### Step 1 — Create the file

Copy `.claude/skills/website/templates/talk.md` into `_talks/`, named `YYYY-MM-DD-slug.md`
(e.g. `_talks/2026-01-31-hpca-nugget.md`).

### Step 2 — Fill in the front matter

```markdown
---
title: "[HPCA 2026] Nugget: Portable Program Snippets"
collection: talks
type: "Main Conference"
permalink: /talks/2026-hpca-nugget
venue: "HPCA 2026"
date: 2026-01-31
location: "Sydney, Australia"
excerpt: "One-sentence summary of the talk."
---
```

Field notes:

| Field | Notes |
|-------|-------|
| `type` | Free-text label shown on the talk. Existing values on this site: `"Main Conference"`, `"Workshop"`, `"Tutorial"`. |
| `location` | **Use a real "City, Country" string** — it gets geocoded onto the talk map (see below). |
| `permalink` | The talk's URL. Set explicitly; it doesn't have to match the filename. |
| `venue` | Short name, e.g. `"HPCA 2026"`. |

You don't set a `layout` — talks automatically use `layout: talk` (configured in `_config.yml`).

### Step 3 — Write the body & attach slides

Below the front matter, write the talk page in Markdown. To link slides, upload the PDF to
**`files/`** and reference it:

```markdown
## Presentation Slides

[Slides](/files/Nugget-LLVM-presentation.pdf)
```

### Step 4 — Update the homepage and CV (do **not** skip)

- **`_pages/about.md`** → under `## Talks`, add an entry matching the existing style:

  ```markdown
  - **[HPCA 2026](/talks/2026-hpca-nugget)** - Accepted paper talk on Nugget (Main Conference, Sydney, Australia)
  ```

- **`_pages/cv.md`** → under `Talks and Tutorials`, add a matching bullet.

### Step 5 — Preview, commit, push

```bash
bundle exec jekyll serve -l -H localhost   # check http://localhost:4000/talks/
git add -A && git commit -m "Add <venue> talk" && git push
```

---

## Automation: the talk map updates itself

Pushing any change under `_talks/` triggers the GitHub Action
`.github/workflows/scrape_talks.yml`. It reads each talk's `location`, geocodes it, and **commits
the updated map for you** with the message *"Automated update of talk locations"*.

What this means for you:

- Just set a correct **`location`** ("City, Country"). That's all the map needs.
- **Don't hand-edit** the `talkmap/` folder or `talkmap.py` — they're generated.
- After you push a talk, **`git pull`** before your next edit to pick up the bot's commit
  (otherwise your next push may be rejected as out-of-date).

---

## Edit / remove a talk

- **Edit:** change the file in `_talks/` in place; update the matching lines in `about.md` and
  `cv.md` if the title/venue changed.
- **Remove:** delete the file and remove its entry from `about.md` and `cv.md`.

## Real examples to copy from

- `_talks/2026-01-31-hpca-nugget.md` (Main Conference)
- `_talks/2026-02-22-cgo-nugget.md` (Workshop)
- `_talks/2023-02-25-hpca-looppoint.md` (Tutorial)
