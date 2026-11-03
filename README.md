# tyekbryant.com

Personal site for Tye Bryant: senior software developer who also makes games.
Served by GitHub Pages from `master`, on the custom domain in `CNAME`.

The 2019 version was built at 3am to learn Bootstrap and cope with insomnia. This one is
plain HTML and CSS: no framework, no build step, no JavaScript.

## Layout rule: full width

No max-width wrapper and no centred column, on purpose. Content runs edge to edge with a small
gutter (`--gutter`), grids stretch to fill the row, and the root font size grows with the viewport
so line lengths stay readable on big screens. Don't add a `max-width` to text or sections.

## Layout

```
index.html            the whole site, one page
404.html              GitHub Pages serves this for any missing path
assets/css/site.css   all styles; colour tokens at the top (dark default, light via prefers-color-scheme)
assets/img/           WebP screenshots/covers, favicon.svg, apple-touch-icon.png, og-image.png
CNAME                 tyekbryant.com
.nojekyll             skip Jekyll; the files are served as-is
```

## Preview locally

Asset paths are root-relative (`/assets/...`), so use a local server rather than opening the file:

```sh
python -m http.server 8000
# then open http://localhost:8000
```

## Keeping it up to date

- **Job or role change:** edit the `<article class="job">` blocks in `index.html`, the hero text, and
  `jobTitle`/`worksFor` in the JSON-LD block in the `<head>`. Source of truth is the current resume.
- **Don't publish** the phone number, referee contact details or clearance details from the resume.
- **Project:** copy one of the `<article class="project">` blocks.
  Add `project--flip` to alternate the image side on desktop.
- **Earlier game card:** copy an `<li class="card">` block. Covers are 16:9; 960×540 WebP
  keeps them sharp on high-DPI screens without being heavy.
- **Images:** keep them in `assets/img/` as WebP, and always set `width`/`height` on the
  `<img>` so the layout doesn't jump while they load.

## Share preview

`assets/img/og-image.png` (1200×630) is what Discord, LinkedIn, X and similar show when the
link is posted. If the tagline changes, regenerate it so the two still match.

The previous site lives in git history (everything before the 2026 refresh) if it's ever
needed for nostalgia.
