# bsinno1.github.io

Personal academic homepage for Barea M. Sinno. Plain static HTML + one CSS file — no Jekyll,
no build step, no dependencies. Edit the HTML directly and push.

## Files

```
index.html            Home — bio, fields & methods, news, selected publications, education, misc
research.html         Research agenda, dissertation, fields & methods, research experience
publications.html     Peer-reviewed / in preparation / book reviews, with filter buttons
code.html             Public repositories — instruments, paper replication material, tooling
teaching.html         Teaching by institution + courses prepared to teach
awards.html           Awards, fellowships, research funding
service.html          Academic, community & professional service; languages & citizenship
assets/css/style.css  All styling (colors live in the `:root` block at the top)
assets/img/           Put your headshot here as profile.jpg (square crop; 400×400 or larger)
```

Content is drawn from `barea_sinno_cv_su26.pdf` (Summer 2026 CV). When the CV changes, these are
the pages to update alongside it.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Publishing to GitHub Pages

This repo is named `bsinno1.github.io`, so GitHub Pages serves it as a **user site** at
`https://bsinno1.github.io` — no project subpath, no config file needed.

```sh
gh repo create bsinno1.github.io --public --source=. --remote=origin --push
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → `master` / `(root)`**.
First build takes a minute or two.

Without the `gh` CLI:

```sh
git remote add origin https://github.com/bsinno1/bsinno1.github.io.git
git push -u origin master
```

## Editing notes

- **Headshot** — save it as `assets/img/profile.jpg`. Until then the page falls back to a
  lettered placeholder (`assets/img/placeholder.svg`) via the `onerror` attribute on the `<img>`.
- **Colors** — change `--primary`, `--accent`, and `--accent-light` in `assets/css/style.css`.
  Everything else derives from those three.
- **Navigation** — the nav block is duplicated in each HTML file. If you add or rename a page,
  update all seven, and move the `class="active"` marker to the current page.
- **News** — newest entry first; each `<li>` is a `.news-date` span followed by a content span.
- **Publications** — the filter buttons match `data-filter` on the button against `data-type` on
  each `.pub-item` and `data-section` on each `.pub-year-heading`. Keep those attributes in sync
  when adding a new category.
- **Awards** — add `class="highlighted"` to an `.award-card` for the gold treatment.

## Placeholders still to fill

Two social-icon URLs in `index.html` are marked with HTML comments — Google Scholar and LinkedIn.
The CV names both profiles but not their URLs, so those icons are omitted until you paste them in.

Deliberately **not** on the site, though they are on the CV: phone number, academic references
(Beth Leech, Junyi Jessy Li, Richard Lau), and the CV PDF itself. Add any of them if you want
them public — the CV PDF would go in `assets/` with a nav link.

## Layout credit

Structure and layout follow the design of <https://wshi83.github.io>. The CSS here is an
independent implementation with its own palette.
