# pakkachan.github.io

Personal site. Plain text, Jekyll, GitHub Pages. No theme, no JavaScript,
no images.

## Layout

```
_config.yml        site name, description, contact links
index.html         home page: short intro + list of posts
about.md           about page
404.md
style.css          the entire stylesheet
_layouts/          default (shell), page, post
_includes/meta.html
_posts/            one markdown file per post
```

## Writing a post

Create `_posts/YYYY-MM-DD-some-title.md`:

```markdown
---
layout: post
title: "The title as it should appear"
date: 2026-08-04
---

Body in markdown.
```

The filename date sets the URL (`/2026/08/04/some-title/`) and the sort
order on the home page. Nothing else needs editing - `index.html` picks up
new posts automatically.

## Preview locally

```bash
jekyll serve
```

Then open <http://127.0.0.1:4000>. It rebuilds on save.

## Deploy

Push to `master`. GitHub Pages builds it.
