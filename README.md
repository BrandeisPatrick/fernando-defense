# Fernando's PhD Defense Site

Live: https://brandeispatrick.github.io/fernando-defense/
Repo: https://github.com/BrandeisPatrick/fernando-defense (GitHub Pages, main branch)

A bilingual (español · English) one-pager for the poster QR code. Scrolling drives
a 3D journey (Three.js) through Fernando's actual research — the topological
chain with glowing edge states, Fano interference ripples between a molecule and
a quantum dot, and hydrogen picking up spin on the Weyl semimetal NbP — then
lands on publications, photos, and the defense details.

## Files

- `index.html` — the whole site (Three.js loads from CDN; STIX Two Text from Google Fonts)
- `fernando-hero.jpg`, `photo-*.jpg` — web-sized images
- `source-photos/` — originals (gitignored, not deployed)
- `qr.html` — QR generator for the poster

## Editing the defense details

Everything lives in the `SITE_CONFIG` block at the top of `index.html`
(marked `✏️ EDIT THIS BLOCK`). The same date text also appears once as static
HTML near `id="d-when"` (the no-JavaScript fallback) — update both.
Flip `confirmed: true` when the time/room are official.

Deploying changes: `git add -A && git commit -m "..." && git push` — the live
site updates in about a minute.

## Behavior notes

- White theme is the default; dark "space" theme on the moon button (remembered).
- No WebGL / reduced-motion / JS-restricted browsers get a static stacked
  version of the same content automatically.
- Debug params for QA: `?static=1` (static fallback), `?static=1&y=<px>`
  (shift content for screenshots), `?static=1&debug=1` (layout metrics in the
  page title), `?p=0.45` (freeze the 3D journey at a scroll fraction),
  `?theme=dark|light`.
