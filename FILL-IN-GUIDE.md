# Fill-in guide — make this portfolio *yours*

This site is built on the [al-folio](https://github.com/alshedivat/al-folio) academic Jekyll
theme, customized into an **editorial + project-tiles** layout (serif headings, a teal accent,
news feed, project cards, BibTeX publications). Everything currently on it is **realistic
placeholder content for an ed-tech / learning-sciences researcher** so you can see the design.
Replace it with your own — every spot to edit is marked with `CONTENT-TODO` in the files.

> Tip: search the project for `CONTENT-TODO` to jump to every placeholder.

## Run it locally
Ruby 3.3 + Jekyll are already installed. From this folder:

```powershell
$env:Path = "C:\Ruby33-x64\bin;$env:Path"
bundle exec jekyll serve
```

Then open <http://127.0.0.1:4000/>. (Use `bundle exec jekyll build` to just build into `_site/`.)

## What to replace (in priority order)

| # | What | File |
|---|------|------|
| 1 | **Your name** | `_config.yml` → `first_name` / `middle_name` / `last_name`, and `scholar.last_name` / `scholar.first_name` |
| 2 | **Positioning line + bio + affiliation** | `_pages/about.md` (the `subtitle`, the `more_info` block, and the body: Research themes, How I work, CTA) |
| 3 | **Headshot** | replace `assets/img/prof_pic.jpg` with your photo (same filename) |
| 4 | **Contact + social links** | `_data/socials.yml` (email, Google Scholar ID, ORCID, LinkedIn, GitHub) |
| 5 | **Projects** | the 5 files in `_projects/` — keep the structure (problem → your role → outcome-with-a-number → links). Swap tile images (`img:` field) and add real screenshots. Categories are `research` / `tools`. |
| 6 | **Publications** | `_bibliography/papers.bib` — paste BibTeX from Google Scholar; mark your best 3–4 with `selected={true}` to show them on the home page |
| 7 | **News** | the dated files in `_news/` (add/remove freely; filename date sorts them) |
| 8 | **CV** | content in `_data/cv.yml`; drop your PDF at `assets/pdf/cv.pdf` and point `cv_pdf` to it in `_pages/cv.md` and `_data/socials.yml` |

## Quick design tweaks
- **Accent color & fonts:** top of `_sass/_custom.scss` (`--global-theme-color`, `$font-serif`, `$font-sans`).
- **Site width:** `max_width` in `_config.yml` (currently `1000px`).
- **Dark mode** is on by default (toggle is in the navbar).

## Optional sections you can turn back on
The theme ships a blog, bookshelf, teaching, repositories, and profiles pages. They're **excluded**
in `_config.yml` (under `exclude:`) to keep the portfolio focused. Remove a line from that list to
re-enable one — e.g. a **blog/notes** section is great for ed-tech thought leadership (set
`latest_posts.enabled: true` in `_pages/about.md` too).

## Before you publish
- Set `imagemagick.enabled: true` in `_config.yml` (GitHub Actions has ImageMagick; it gives you
  faster responsive WebP images). It's `false` locally only because ImageMagick isn't installed here.
- Set `url:` in `_config.yml` to your real domain. Keep `baseurl: ""` for a root domain; use
  `baseurl: /reponame` only if hosting at `username.github.io/reponame`.

## Deploy to GitHub Pages (free)
1. Create a GitHub repo and push this folder to the `main` branch.
2. The included workflow `.github/workflows/deploy.yml` builds the site and publishes it to a
   `gh-pages` branch automatically on every push.
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch →
   `gh-pages` / root**.
4. **Custom domain (like the inspiration site):** in **Settings → Pages**, set your custom domain
   (this creates a `CNAME` file). At your domain registrar, add a `CNAME` DNS record for `www`
   pointing to `username.github.io`, and the four GitHub Pages `A` records for the apex domain.
   Enable **Enforce HTTPS**.

More detail lives in `docs/INSTALL.md` and `docs/CUSTOMIZE.md`.
