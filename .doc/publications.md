# Adding, editing & removing a publication

Publications live in **`_publications/`** — one Markdown file per paper. The `/publications/`
listing page is generated automatically from that folder.

> ⚠️ **Remember the three places.** Adding the file below makes the paper show up on
> `/publications/` only. You must **also** add it by hand to the homepage (`_pages/about.md`) and
> the CV (`_pages/cv.md`). See [step 4](#step-4-update-the-homepage-and-cv-do-not-skip).

---

## Add a new publication

### Step 1 — Create the file

Copy the template at `.claude/skills/website/templates/publication.md` into `_publications/`, named
`YYYY-MM-DD-slug.md` (the date prefix orders the list, newest first). For example:
`_publications/2026-01-31-nugget.md`.

### Step 2 — Fill in the front matter

```markdown
---
title: "Nugget: Portable Program Snippets"
collection: publications
category: conferences
permalink: /publication/2026-01-31-nugget
excerpt: "One- or two-sentence summary shown on the publications listing page."
date: 2026-01-31
venue: 'IEEE International Symposium on High-Performance Computer Architecture (HPCA)'
paperurl: 'https://arxiv.org/abs/2509.02873'
citation: 'Qiu, Z., Samani, M., & Lowe-Power, J., "Nugget: Portable Program Snippets." 2026 IEEE HPCA. Sydney, Australia.'
---
```

Field notes:

| Field | Notes |
|-------|-------|
| `category` | Controls which heading the paper appears under. One of: `conferences` → **Conference Papers**, `manuscripts` → **Journal Articles**, `books` → **Books**. (These mappings are defined in `_config.yml` under `publication_category`.) |
| `permalink` | The URL for the paper. Convention on this site: `/publication/<slug>`. Set it explicitly so the URL stays stable even if you rename the file. |
| `paperurl` | Link to arXiv/PDF/DOI. Leave as `''` if you don't have one yet. |
| `citation` | Full citation string. Use `TBD` if not finalized. |
| `excerpt` | Shown on the `/publications/` listing card. |

### Step 3 — Write the body & attach a PDF

Below the front matter, write the page in Markdown (Abstract, Main Contributions, links, etc.).
If you have a PDF, drop it in **`files/`** and link it from the body:

```markdown
[Read the full paper](/files/My-Paper.pdf)
```

(Or just link the external arXiv/DOI URL.)

### Step 4 — Update the homepage and CV (do **not** skip)

Edit both of these so the curated lists match:

- **`_pages/about.md`** → under the `## Publications` section, add an entry. Match the existing
  style, e.g.:

  ```markdown
  1. **[Nugget: Portable Program Snippets](/publication/2026-01-31-nugget)** (HPCA 2026)
     **Zhantong Qiu**, Mahyar Samani, Jason Lowe-Power
     LLVM IR-based sampling framework
  ```

- **`_pages/cv.md`** → under the `Publications` section, add a matching bullet.

Then update the CV's other forms — see **[cv.md](cv.md)** (run `bash scripts/update_cv_json.sh` and
replace `files/Zhantong_Qiu_CV.pdf`).

### Step 5 — Preview, commit, push

```bash
bundle exec jekyll serve -l -H localhost   # check http://localhost:4000/publications/
git add -A && git commit -m "Add <paper> publication" && git push
```

---

## Edit an existing publication

Open the file in `_publications/` and edit in place. Keeping the same `permalink` keeps the URL
stable. If you change the title or venue, **also update the matching lines in `_pages/about.md` and
`_pages/cv.md`**.

## Remove a publication

1. Delete the file from `_publications/`.
2. Delete its entry from `_pages/about.md` and `_pages/cv.md`.
3. Regenerate the CV JSON and PDF (see [cv.md](cv.md)).

---

## Real examples to copy from

- `_publications/2026-01-31-nugget.md` (a conference paper)
- `_publications/2025-01-08-looppoint.md` (a journal article — `category: manuscripts`)

## Bulk import (optional, advanced)

If you ever need to add many papers at once, the `markdown_generator/` folder has scripts that
generate publication files from a spreadsheet (`publications.tsv` → `publications.py`) or from
BibTeX (`pubsFromBib.py`, `OrcidToBib.ipynb`). For one or two papers, hand-editing is simpler.
