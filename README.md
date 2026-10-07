# Communication Theory in the Age of AI (Jekyll + GitHub Pages)

This repository contains a Jekyll site designed for non-technical audiences.
It provides a starter structure for explaining communication theory and applying it to 21st-century communication problems, especially those involving AI.

## Site structure

- `index.md` — home page introducing the project.
- `transmission-view-and-limits.md`
- `meaning-and-culture.md`
- `interpretation-and-power.md`
- `interpretation-and-intention.md`
- `what-the-reader-should-do.md`
- `how-i-built-this-site.md`
- `_includes/` — shared template parts (`head`, `header`, `footer`).
- `_layouts/` — page layouts.
- `assets/css/main.scss` — global visual style and color variables.
- `assets/images/` — place your images here.
- `.github/workflows/pages.yml` — build/deploy workflow for GitHub Pages.

## GitHub Pages configuration

The site is configured as a project page:

- `url: "https://bryngrant.github.io"`
- `baseurl: "/MyAwesomeSemester"`

If your username or repository name changes, update those values in `_config.yml`.

## Build and deploy workflow

The GitHub Action in `.github/workflows/pages.yml`:

- triggers on every push to `main`
- runs `bundle exec jekyll build`
- uploads `_site` as the Pages artifact
- deploys to GitHub Pages

## How to add or replace content

### 1) Edit existing pages

Open any `.md` page in the repository root and replace boilerplate paragraphs with your own writing.

Recommended pattern per page:

1. Introduce the communication problem.
2. Explain the theory lens.
3. Apply the lens to your case.
4. Summarize what this lens reveals and what it misses.

### 2) Add a new page (optional)

Create a new markdown file in the repo root:

```md
---
title: Your Page Title
---

<a class="back-link" href="{{ '/' | relative_url }}#lenses">&larr; Back to all theory lenses</a>

<article class="content-panel" aria-labelledby="page-heading">
  <h1 id="page-heading">Your Page Title</h1>
  <p>Your content...</p>
</article>
```

Then add a link to that page in `index.md` under the ordered list.

### 3) Add images

1. Put files in `assets/images/` (example: `assets/images/model-diagram.png`).
2. Reference images in markdown or HTML using `relative_url`:

```html
<img src="{{ '/assets/images/model-diagram.png' | relative_url }}" alt="Describe the image clearly" />
```

Accessibility tip: always write meaningful `alt` text.

## Styling and color customization

Edit `assets/css/main.scss` and adjust CSS variables inside `:root`.

### Core palette variables

- `--color-bg`
- `--color-surface`
- `--color-ink`
- `--color-ink-soft`
- `--color-line`
- `--color-accent`
- `--color-accent-dark`
- `--color-focus`

### Visual variables

- `--radius` (rounded corners)
- `--shadow` (panel depth)
- `--font-body`
- `--font-display`

## Accessibility notes

The starter includes:

- skip link for keyboard users
- ARIA labels on header, navigation, footer, and key sections
- visible focus styles
- semantic landmarks (`main`, `article`, headings)

When editing content, preserve heading order and descriptive link text.

## Local preview

From repository root:

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000/MyAwesomeSemester/`.

## Agent involvement statement

The repository structure, theme setup, accessibility scaffolding, workflow wiring, and boilerplate content were initialized with AI coding-agent assistance.
All final analytical content should be authored and curated by the site owner.
