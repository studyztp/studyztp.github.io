# Teaching & portfolio items

These two collections work just like publications and talks — one Markdown file per item, with the
listing page generated automatically. They are **simpler**: there are no hand-curated copies to keep
in sync (unlike publications/talks). The CV does list teaching separately, though — if you add a
teaching role, also add it to `_pages/cv.md` (see [cv.md](cv.md)).

---

## Teaching → `_teaching/`

One file per course/role; listed at `/teaching/`.

### Steps

1. Copy `.claude/skills/website/templates/teaching.md` into `_teaching/` with a descriptive name,
   e.g. `_teaching/2024-winter-ecs154b.md`.
2. Fill in the front matter:

   ```markdown
   ---
   title: "ECS 154B: Computer Architecture Teaching Assistant"
   collection: teaching
   type: "Teaching Assistant"
   permalink: /teaching/2024-winter-ecs154b
   venue: "University of California, Davis"
   date: 2024-01-01
   location: "Davis, California"
   excerpt: "One-sentence summary of the course / your role."
   ---
   ```

   `type` is free text (e.g. `"Teaching Assistant"`, `"Instructor"`, `"Guest Lecturer"`).
3. Write the body in Markdown (course overview, responsibilities, topics, outcomes, links).
4. (Optional but recommended) Add a bullet under `Teaching Experience` in `_pages/cv.md`.
5. Preview, commit, push.

**Real example:** `_teaching/2024-winter-ecs154b.md`.

---

## Portfolio → `_portfolio/`

One file per project; listed at `/portfolio/`. Portfolio items are **slug-named — no date prefix
needed**.

### Steps

1. Copy `.claude/skills/website/templates/portfolio.md` into `_portfolio/`, e.g.
   `_portfolio/my-project.md`.
2. Fill in the front matter:

   ```markdown
   ---
   title: "Project Title"
   excerpt: "One-sentence summary shown on the /portfolio/ listing page."
   collection: portfolio
   # permalink: /portfolio/my-project   # optional; omit to auto-derive from the filename
   ---
   ```

   If you omit `permalink`, Jekyll derives the URL from the filename
   (`/portfolio/my-project/`).
3. Write the body (description, screenshots, links to code/demo).
4. Preview, commit, push.

**Current content:** only `_portfolio/under-construction.md` exists — you can replace it with real
projects or leave it as a placeholder.
