# Agent guide: home (academic site)

Instructions for AI agents (and humans) working in this repository.

Live site: [https://de4liu.github.io/home/](https://de4liu.github.io/home/) · Source: `de4liu/home` (GitHub Pages from `master`)

---

## Mental model (read first)

| Concept | Meaning |
|---------|---------|
| **What this is** | Personal academic website for Dr. De Liu (Jekyll + [academicpages](https://academicpages.github.io/) theme) |
| **What this is not** | SmartPAL eng ops, PhD coordinator tools, or private vita scratchpads |
| **Hosting** | GitHub Pages — **push to `master` deploys** |
| **Canonical content** | Hand-edited Markdown under `_pages/` (not the unused Jekyll collections) |
| **Static assets** | PDFs in `files/`; photos/icons in `images/` |

```
edit _pages/*.md + files/*.pdf
 ──commit──► master ──GitHub Pages──► https://de4liu.github.io/home/
```

Primary pages (nav in `_data/navigation.yml`):

| Path | File | Role |
|------|------|------|
| `/` | `_pages/about.md` | Home / bio |
| `/cv/` | `_pages/cv.md` | CV (links `files/liu_cv.pdf`) |
| `/publications/` | `_pages/publications.md` | Journal list + PDF links |
| `/wp/` | `_pages/wp.md` | Working papers |
| `/teaching/` | `_pages/teaching.md` | Teaching + PhD students |
| `/awards/` | `_pages/awards.md` | Awards |
| `/contact/` | `_pages/contact.md` | Office / email |

Site-wide author/profile/SEO: `_config.yml`. Local override: `_config.dev.yml`.

---

## Hard rules

1. **This repo is public.** Never commit secrets, private notes, tokens, student data, or unpublished personal scratch.
2. **Do not commit `buffer.md` / `*.task` in this public repo** — local `buffer.md` is gitignored.
   Durable copy: `personal-admin/research/home-site/buffer.md`.
3. **Do not commit or push** unless the user explicitly asks. Pushing `master` updates the live site.
4. **Minimize scope** — one page or asset concern per change; do not reintroduce academicpages demo content.
5. Prefer **linking PDFs from `files/`** on the publications page over relying on remote `idsdl.csom.umn.edu` hosts when a local copy exists.
6. Keep **FERPA / private drafts** out of this repo entirely.

---

## Repository layout

| Path | Purpose |
|------|---------|
| `_config.yml` | Site title, author, URL/`baseurl`, plugins, collections |
| `_data/navigation.yml` | Top nav |
| `_pages/` | **Real site pages** (edit here) |
| `_includes/` / `_layouts/` / `_sass/` / `assets/` | Theme chrome — change only when styling/behavior needs it |
| `files/` | Public PDFs (CV + papers). Filenames must match hrefs in `_pages/` |
| `images/` | Avatar (`de_liu.jpg`), logos, favicons |
| `markdown_generator/` | Optional scripts to generate collection Markdown from TSV/BibTeX — **not** how the live pubs page is maintained today |
| `_posts/` `_talks/` `_teaching/` `_portfolio/` `_publications/` | Collection dirs kept empty (`output: false`). Do not dump template demos here |
| `Gemfile` / `Gemfile.lock` | Ruby/Jekyll deps for local preview |

---

## Local preview

```bash
cd /home/deliu/personal/home
# Ruby + bundler required
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
# open http://127.0.0.1:4000/home/
```

If Windows-era gems in `Gemfile.lock` fail on Linux, delete `Gemfile.lock` and re-run `bundle install` (upstream academicpages note).

`baseurl` is `/home` — local and production URLs are under `/home/...`.

---

## Common agent tasks

### A) Update bio, CV text, teaching, awards, contact

1. Edit the matching file under `_pages/`.
2. Preview locally if layout-sensitive.
3. Commit/push only when asked.

### B) Add or update a publication PDF

1. Drop the PDF in `files/` with a stable short name (e.g. `voicebot.pdf`).
2. Add/adjust the list item and `<a href="/home/files/….pdf">PDF</a>` in `_pages/publications.md` (or working-paper entry in `_pages/wp.md`).
3. Do not leave orphan PDFs unlinked without noting why.

### C) Replace the CV PDF

1. Replace `files/liu_cv.pdf`.
2. Confirm `_pages/cv.md` still points at `/home/files/liu_cv.pdf`.

### D) Nav change

1. Edit `_data/navigation.yml`.
2. Ensure the target page exists under `_pages/` with a matching `permalink`.

### E) Theme / CSS / JS

Touch `_sass/`, `assets/`, or `_includes/` only when necessary; prefer content edits in `_pages/`.

---

## Safety checklist (before push)

- [ ] No `buffer.md`, task lists, passwords, or private correspondence
- [ ] No student PII or unpublished partner material
- [ ] New PDFs are intentional public copies (copyright/author rights OK to host)
- [ ] Links use `/home/files/...` (respect `baseurl`)
- [ ] Diff is limited to intended pages/assets

---

## Anti-patterns

| Don't | Do instead |
|-------|------------|
| Re-add academicpages sample posts/talks/portfolio | Keep collections empty / `output: false` |
| Store vita scratch (`buffer.md`) in this repo | Keep scratch in a private personal repo |
| Push WIP to `master` casually | Preview locally; push when ready to publish |
| Invent new collection workflows without need | Edit `_pages/publications.md` (current SSOT) |
| Commit `.env`, tokens, or private PDFs | Keep them out of this public tree |
| Enable Analytics/Disqus with empty IDs | Leave `analytics.provider` / `comments.provider` false until configured |

---

## Related

| Repo / place | Relationship |
|--------------|--------------|
| [`personal-admin`](../personal-admin) | Private personal tooling / notes (not this public site) |
| [`smartpal-web`](../../repos/smartpal-web) | SmartPAL marketing site (separate) |
| Upstream [academicpages](https://github.com/academicpages/academicpages.github.io) | Theme origin — do not treat CONTRIBUTING.md as if this were still the generic template |

When unsure, **edit `_pages/` only, preview locally, and ask before pushing `master`.**
