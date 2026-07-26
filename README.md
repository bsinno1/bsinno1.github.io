# bsinno1.github.io

Personal academic homepage for Barea M. Sinno. Plain static HTML + one CSS file — no Jekyll,
no build step, no dependencies. Edit the HTML directly and push.

## Files

```
index.html            Home — bio, research interests, news, selected publications, education, misc
publications.html     Full publication list with All / Conference / In Progress filter buttons
teaching.html         Teaching by institution
awards.html           Honors, awards, grants
service.html          Talks, academic service, data/code releases, non-academic service
assets/css/style.css  All styling (colors live in the `:root` block at the top)
assets/img/           Put your headshot here as profile.jpg (square crop; 400×400 or larger)
```

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
  update all five, and move the `class="active"` marker to the current page.
- **News** — newest entry first; each `<li>` is a `.news-date` span followed by a content span.
- **Publications** — the filter buttons match `data-filter` on the button against `data-type` on
  each `.pub-item` and `data-section` on each `.pub-year-heading`. Keep those attributes in sync
  when adding a new category.
- **Awards** — add `class="highlighted"` to an `.award-card` for the gold treatment.

## Placeholders still to fill

Search the HTML for `<!--` comments and `<em>` italics — those mark the spots where real detail
is needed: course numbers and terms on the teaching page, fellowship names on the awards page,
reviewing venues on the service page, and dissertation chapter titles / target venues on the
publications page. Also add a Google Scholar link to the social icons in `index.html` if you have
a profile.

## Layout credit

Structure and layout follow the design of <https://wshi83.github.io>. The CSS here is an
independent implementation with its own palette.
