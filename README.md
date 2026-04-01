# Vanderbilt NeuroTech — GitHub Pages

Static site for [Vanderbilt NeuroTech](https://github.com/vysha-exe/Vanderbilt-NeuroTech-Git-Pages), built with [Jekyll](https://jekyllrb.com/) so we get a **blog-style Updates** section without any backend. GitHub Pages builds it automatically on every push.

**Live URL:** `https://vysha-exe.github.io/Vanderbilt-NeuroTech-Git-Pages/`

## Repo layout (no separate frontend/backend)

GitHub Pages only serves **static files**. There is no server or API, so you do **not** need `frontend/` and `backend/` folders. Everything lives in the usual Jekyll layout:

| Path | Purpose |
|------|---------|
| `_layouts/`, `_includes/` | HTML templates |
| `_posts/` | Blog / recent updates (Markdown) |
| `_projects/` | Project detail pages (Markdown; linked from **Projects**) |
| `_data/board.yml` | Team names, roles, majors, optional `show_major: false`, photos |
| `_data/gallery.yml` | List of club photos (`file` + optional `caption`) |
| `_data/newsletters.yml` | Newsletter archive (`issues:` with `date`, `title`, `url` or `file`) |
| `assets/css/`, `assets/js/` | Styles and scripts |
| `assets/files/newsletter/` | Optional PDFs linked from `newsletters.yml` |
| `assets/images/board/` | Headshots → paths in `board.yml` |
| `assets/images/gallery/` | Club photos → paths in `gallery.yml` |

**Main URLs:** `/newsletter/`, `/team/` (Our Team), `/projects/`, `/gallery/` (Photos), `/contact/`. Old `/board/` redirects to `/team/`.

## Enable GitHub Pages

1. On GitHub: **Settings → Pages**.
2. **Build and deployment → Source:** GitHub Actions is *not* required for this setup; use **Deploy from a branch**.
3. **Branch:** `main`, folder **`/ (root)`**.
4. Save. The first build may take a minute; check **Actions** or the Pages settings for the published URL.

## Push this project to the remote

If this folder is not yet a git repo:

```powershell
cd path\to\NeuroTech-Github-Pages
git init
git add .
git commit -m "Add Vanderbilt NeuroTech Jekyll site"
git branch -M main
git remote add origin https://github.com/vysha-exe/Vanderbilt-NeuroTech-Git-Pages.git
git push -u origin main
```

If the remote already has a commit (e.g. only a README), either `git pull origin main --rebase` first, or follow GitHub’s instructions to merge.

## Blog posts (recent updates)

1. Create a file in `_posts/` named **`YYYY-MM-DD-short-title.md`** (date = post date).
2. Use this front matter:

```yaml
---
layout: post
title: "April 2026 — Your title"
date: 2026-04-01
---

Your markdown content here.
```

3. Commit and push. The **Updates** page and home page will list new posts automatically.

## Team photos and majors

Edit **`_data/board.yml`**:

- Set **`major:`** for student officers; for faculty/advisers with no major line, set **`show_major: false`** (hides the major row entirely).
- Add **`photo:`** as a path under the site root, e.g. `assets/images/board/paige.jpg`, after adding the image file.

If **`photo`** is empty, the site shows **initials** in a circular placeholder.

## Projects

Add a Markdown file under **`_projects/`** with front matter, for example:

```yaml
---
layout: project
title: My project
short_description: One line for the card on the Projects page.
status: Active
order: 10
github: https://github.com/org/repo
website: https://example.com
---
Longer description in Markdown. Links appear as buttons when `github` / `website` / `docs` / `video_url` are set.
```

Use **`order:`** (number) to sort cards on `/projects/`. Leave **`github:`** blank to hide the GitHub button. Set **`video_url:`** (e.g. YouTube) to show a **Tutorial video** button; remove the placeholder HTML block in that project’s Markdown once the link is live if you like.

Optional **`signup_url:`** — Google Form (or similar) link; shows a **Sign up to collaborate** button. If **`status: Recruiting`** and **`signup_url`** is empty, the page shows **Express interest** instead (links to **Contact us**).

## Photo gallery

1. Add images under **`assets/images/gallery/`**.
2. Edit **`_data/gallery.yml`** and append to **`items:`**:

```yaml
items:
  - file: assets/images/gallery/your-photo.jpg
    caption: Optional caption
```

## Newsletter archive (`/newsletter/`)

Edit **`_data/newsletters.yml`** and add under **`issues:`** (any order; the page sorts newest first):

```yaml
issues:
  - date: 2026-03-31
    title: "Spring planning + lab tour recap"
    url: https://drive.google.com/file/d/...
  - date: 2026-03-17
    title: "Issue 11"
    file: assets/files/newsletter/2026-03-17.pdf
```

Use **`url`** for Google Drive, Substack, Mailchimp archive links, etc., or **`file`** for a PDF committed under `assets/files/newsletter/`.

## Local preview (optional)

Install Ruby + Bundler, then:

```powershell
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000/Vanderbilt-NeuroTech-Git-Pages/` (Jekyll prints the exact URL).

## Theme notes

The design uses **black** with **gold** and **teal/cyan** accents. CSS variables at the top of `assets/css/style.css` control colors if you want to tweak.
