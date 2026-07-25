# lepablito.github.io

GitHub Pages **user site** for [@lepablito](https://github.com/lepablito). It
serves the root of `https://lepablito.github.io/`.

## Why this repo exists

`robots.txt` is a per-origin file: crawlers fetch it from the domain root
(`/robots.txt`) and from nowhere else. The portfolio lives in a *project*
site repo, which GitHub Pages serves under a subpath
(`/professional-portfolio/`), so a `robots.txt` committed there is published
at `/professional-portfolio/robots.txt` — a URL no crawler ever requests.
Its `Sitemap:` directive was therefore invisible to Google, and the sitemap
was never discovered.

This repo owns the one `robots.txt` that actually gets read, and declares the
sitemaps of every project site under the origin.

## Contents

| File | Purpose |
| --- | --- |
| `robots.txt` | The origin's real robots.txt. Declares each project site's sitemap. |
| `index.html` | Sends `/` to the portfolio, and gives crawlers a link to follow inward. |
| `.nojekyll` | Skips Jekyll processing — the files are served verbatim. |

## Maintenance

- Adding a project site with a sitemap → add a `Sitemap:` line to `robots.txt`.
- Moving the portfolio to a custom domain → the portfolio repo's own
  `public/robots.txt` lands at the root there and becomes the effective one;
  drop its sitemap line from here to avoid two sources of truth.
