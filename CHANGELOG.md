# Changelog

All notable changes to this site are documented here.
Format: [Keep a Changelog](https://keepachangelog.com/). Versioning: [SemVer](https://semver.org/).

## [1.0.0] — 2026-09-03

Major cleanup of the academicpages fork. Removes all template demo content,
adds local copies of every publication PDF, generates proper favicon assets,
and adds an `AGENTS.md` guide.

### Added

- `AGENTS.md` — agent/maintainer guide for the repo
- 17 older publication PDFs copied from Google Drive (`files/`) — every journal
  paper now has a local PDF
- Favicon PNG set generated from `de_liu.jpg` (apple-touch-icon, android-chrome,
  favicon sizes) — resolves missing icon 404s
- `.gitkeep` in empty collection dirs (`_posts/`, `_talks/`, etc.)

### Changed

- **Publications page**: all 17 `idsdl.csom.umn.edu` / `csom-idsdl.oit.umn.edu`
  PDF links rewired to local `/home/files/…`; added missing PDF link for
  Interleaved Design (MIS Quarterly 2023); fixed Meaningful Engagement link to
  local copy; fixed voicebot link label (`.` → `PDF`)
- **`_config.yml`**: collections set to `output: false` (no demo URLs);
  analytics/comments disabled; Jekyll `exclude` list expanded (AGENTS, CHANGELOG,
  markdown_generator, talkmap, buffer scratch)
- **`.gitignore`**: hardened (`.env`, `venv/`, `*.task`, caches)
- **`Gemfile`**: modernised (added `webrick`, `jekyll-redirect-from`, `jemoji`;
  dropped `hawkins`)
- **`README.md`**: replaced upstream template README with site-specific content
- **`_data/navigation.yml`**: cleaned up commented-out entries
- **`_includes/head/custom.html`**: shortcut icon now uses `{{ base_path }}`
- **`images/manifest.json`**: updated name to "Dr. De Liu", simplified icon paths

### Removed

- `buffer.task` — personal scratch (buffer.md kept and tracked)
- `CONTRIBUTING.md` — upstream template file, not applicable
- All **template demo content**: sample blog posts, talks, teaching, portfolio,
  publications collection items, draft post
- Demo/unused **pages**: `markdown.md`, `non-menu-page.md`,
  `archive-layout-with-content.md`, `terms.md`, `portfolio.html`,
  `talkmap.html`, `year-archive.html`, `category-archive.html`,
  `tag-archive.html`, `collection-archive.html`, `page-archive.html`
- **talkmap** tooling (`talkmap/`, `talkmap.py`, `talkmap.ipynb`)
- Unused/duplicate **PDFs**: `CrowdVoting.pdf` (dup), `zap.pdf` (dup of badges),
  `credential.pdf` (unreferenced)
- Demo **images**: `bio-photo*.jpg`, `500x300.png`, `foo-bar-identity*`,
  `image-alignment-*`, `paragraph-*`, `editing-talk.png`, `profile.png`,
  `site-logo.png`, generic stock photo
