# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Is

A Jekyll-based academic personal website using the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme. Hosted on GitHub Pages at `darioaromero.github.io`.

## Commands

```bash
# Install dependencies (first time)
bundle install

# Local development server (live reload at http://localhost:4000)
bundle exec jekyll serve

# Build for production
bundle exec jekyll build

# Build with incremental regeneration (faster for large sites)
bundle exec jekyll serve --incremental
```

## Site Architecture

The site has four main pages defined in `_pages/`: `research.md`, `teaching.md`, `appointments.md`, `gallery.md`. Navigation order is set in `_data/navigation.yml`.

**Homepage** (`index.md`): Uses a `feature_row` layout from Minimal Mistakes to display research paper tiles. Each tile has an image, excerpt, and PDF link. Images are stored in `images/research/` and paper PDFs in `images/documents/Papers/`.

**Content hierarchy:**
- `_config.yml` — site-wide settings, author bio/links, plugin config
- `_data/navigation.yml` — top nav menu items
- `_pages/` — the four static pages
- `images/` — all static assets (photos, PDFs, figures); this is the primary content store, not `assets/`
- `_layouts/` and `_includes/` — inherited from Minimal Mistakes gem; do not edit unless overriding theme behavior

## Key Conventions

**Adding/updating a paper:** Edit `_pages/research.md` (the table rows) and `index.md` (the `feature_row` block if it should appear on the homepage). PDFs go in `images/documents/Papers/`, figures in `images/research/`.

**CV:** The CV PDF is at `images/documents/CV/Romero_cv.pdf`. The link in `_config.yml` under `author.links` points to it.

**Theme skin:** Set in `_config.yml` as `minimal_mistakes_skin`. Current value is `"default"`. Options: `air`, `aqua`, `contrast`, `dark`, `neon`, `mint`, `plum`, `sunrise`.

**Layouts:** All pages use `layout: single` with `author_profile: true` (shows sidebar bio). The homepage uses `layout: single` with the `feature_row` Liquid include for the paper tiles.

**Markdown styling:** Notices like `{: .notice--success}` (green), `{: .notice--warning}` (yellow), `{: .notice--danger}` (red) are used as section headers in `research.md`.
