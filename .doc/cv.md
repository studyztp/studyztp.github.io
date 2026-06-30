# Updating the CV

The CV exists in **three forms that must be kept in sync**. The markdown file is the source of
truth; the other two are derived from it.

| Form | File | How it's maintained |
|------|------|---------------------|
| **Markdown CV** (the page at `/cv/`) | `_pages/cv.md` | **Hand-edited — this is the master.** |
| **JSON Resume data** | `_data/cv.json` | **Generated** from `cv.md` by a script. Don't hand-edit. |
| **Downloadable PDF** | `files/Zhantong_Qiu_CV.pdf` | Replaced **manually** when the CV changes. |

---

## The normal update flow

### 1. Edit the markdown CV

Open **`_pages/cv.md`** and edit the relevant section. Its sections use the underline heading style:

```markdown
Education
======
* Master of Science in Computer Science, UC Davis, Fall 2023 - Spring 2026 (expected)
* ...
```

The sections are: *Introduction, Education, Publications, Talks and Tutorials, Research Experience,
Course Projects, Teaching Experience, Organizations and Service, Skills.*

> If your change is a new **paper** or **talk**, you'll also have updated `_publications/`/`_talks/`
> and `_pages/about.md` — see [publications.md](publications.md) / [talks.md](talks.md). The
> `Publications` and `Talks and Tutorials` sections of `cv.md` are the CV's own copies of those
> lists.

### 2. Regenerate the JSON

From the repo root, run:

```bash
bash scripts/update_cv_json.sh
```

This reads `_pages/cv.md` and rewrites `_data/cv.json`. At the end it asks *"Would you like to build
the Jekyll site to see the changes? (y/n)"* — answer **`n`** if you're already running the site
locally (or `y` to have it start a server for you).

`_data/cv.json` powers an alternative JSON-rendered CV page (`/cv-json/`), which is currently
disabled in the menu. Even though it's disabled, regenerate the JSON so it doesn't drift.

### 3. Replace the PDF

Export/produce your updated CV PDF and save it over **`files/Zhantong_Qiu_CV.pdf`** (keep the same
filename so the existing download links keep working). This PDF is linked from both the homepage
(`_pages/about.md`) and the CV page (`_pages/cv.md`).

### 4. Commit & push

```bash
git add -A && git commit -m "Update CV" && git push
```

---

## Quick checklist

- [ ] Edited `_pages/cv.md`
- [ ] Ran `bash scripts/update_cv_json.sh` (regenerates `_data/cv.json`)
- [ ] Replaced `files/Zhantong_Qiu_CV.pdf`
- [ ] If a publication/talk changed, the homepage `_pages/about.md` matches too
- [ ] Previewed `/cv/` locally, then committed & pushed
