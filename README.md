# studyztp.github.io

My personal academic website, built on the **[Academic Pages](https://academicpages.github.io/)**
Jekyll template (a detached fork of Minimal Mistakes) and hosted on **GitHub Pages**.

All content is plain **Markdown with YAML front matter**. There is no build step to run by hand:
**deploy = commit and `git push` to `master`**, and GitHub Pages rebuilds the live site automatically.

---

## ✍️ How do I edit my site?

Everything you'll commonly want to change has a short, step-by-step guide in the **[`.doc/`](.doc/)**
folder. Start there:

| I want to… | Guide | Files I'll touch |
|------------|-------|------------------|
| Understand how the site is wired together | **[.doc/README.md](.doc/README.md)** | — |
| Add / edit / remove a **publication** | **[.doc/publications.md](.doc/publications.md)** | `_publications/`, `_pages/about.md`, `_pages/cv.md` |
| Add / edit a **talk** | **[.doc/talks.md](.doc/talks.md)** | `_talks/`, `_pages/about.md`, `_pages/cv.md` |
| Add **teaching** or **portfolio** items | **[.doc/teaching-and-portfolio.md](.doc/teaching-and-portfolio.md)** | `_teaching/`, `_portfolio/` |
| Edit the **homepage**, its sections ("blocks"), or add a **new page** | **[.doc/homepage-and-pages.md](.doc/homepage-and-pages.md)** | `_pages/about.md`, `_pages/`, `_data/navigation.yml` |
| Update my **CV** | **[.doc/cv.md](.doc/cv.md)** | `_pages/cv.md`, `_data/cv.json`, `files/…CV.pdf` |
| Change my **name, bio, photo, social links**, or theme | **[.doc/site-settings.md](.doc/site-settings.md)** | `_config.yml`, `images/`, `files/` |
| **Preview locally** and **publish** | **[.doc/running-locally.md](.doc/running-locally.md)** | — |

> ### ⚠️ The one rule that bites everyone
> Publications and talks live in **three places**: the collection file (`_publications/` or
> `_talks/`), the homepage (`_pages/about.md`), **and** the CV (`_pages/cv.md`). The
> `/publications/` and `/talks/` listing pages update themselves — but the homepage and CV are
> **hand-curated copies**. When you add or remove a paper or talk, update all three (plus the PDF
> CV). See [.doc/publications.md](.doc/publications.md) and [.doc/talks.md](.doc/talks.md).

---

## Preview locally (quick version)

```bash
bundle install                              # first time only
bundle exec jekyll serve -l -H localhost    # → http://localhost:4000
```

The browser auto-refreshes on every save **except** for `_config.yml`, which needs a server
restart. Full setup, Docker, and troubleshooting are in
**[.doc/running-locally.md](.doc/running-locally.md)**.

## Publish

```bash
git add -A
git commit -m "Describe your change"
git push          # to master
```

GitHub Pages rebuilds and publishes within a minute or two. If you added a **talk**, an automated
bot then pushes a follow-up "Automated update of talk locations" commit — run `git pull` before
your next edit.

---

## Prefer to let Claude do it?

This repo ships with a Claude Code **`website` skill** (`.claude/skills/website/`) that knows all
of the above. In Claude Code you can just say e.g. *"add my HPCA 2026 paper"* or *"update my
homepage research interests"* and it will follow the same steps documented in `.doc/`. The ready-made
front-matter templates it uses live in `.claude/skills/website/templates/`.

---

## Credits & license

Built on the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template,
itself a detached fork of the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)
Jekyll theme (© Michael Rose). Released under the MIT License — see [LICENSE](LICENSE).
