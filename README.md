# fariha-yasmin.github.io

My personal academic website — research, projects, and reference notes.
Built with [Jekyll](https://jekyllrb.com) and the [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme, hosted on [GitHub Pages](https://pages.github.com).

**Live site:** <https://fariha-yasmin.github.io>

## Structure

| Path | What it is |
|---|---|
| `index.md` | Home page (recent posts) |
| `research.md` | Research areas, methods, workflow |
| `projects.md` + `_projects/` | Research project write-ups (Jekyll **collection**) |
| `notes.md` + `_notes/` | Theory & tools reference notes (Jekyll **collection**) |
| `publications.md` | Publications (template with format examples) |
| `cv.md` | Online CV |
| `about.md`, `contact.md` | About & contact |
| `_posts/` | Blog posts (filename must start `YYYY-MM-DD-`) |
| `_data/navigation.yml` | Top navigation menu |
| `_config.yml` | Site configuration |
| `assets/` | Styles, images, downloadable files |

## Adding content

**New note** — create `_notes/my-note.md`:

```yaml
---
title: "Note Title"
excerpt: "One-line description shown on the Notes index."
category: "Theory"        # or "Tools" — notes are grouped by this
tags: [dft, perovskites]
date: 2026-08-24
---
```

**New post** — create `_posts/2026-08-24-my-post.md` with `title` and `date` front matter.

**New project** — create `_projects/my-project.md` with `title`, `excerpt`, `layout: single`.

## Running locally

```bash
gem install bundler
bundle init && bundle add jekyll jekyll-remote-theme jekyll-include-cache
bundle exec jekyll serve
# → http://localhost:4000
```

(GitHub Pages rebuilds the site automatically on every push to `main`.)
