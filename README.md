# Fernando's PhD Defense Site 🎓

A one-page animated site for the poster QR code: scan → quantum particle intro →
Fernando's story, science, and papers → defense details + countdown + add-to-calendar.

## Files

- `index.html` — the whole site (self-contained; fonts load from Google Fonts)
- `fernando-hero.jpg` — circular hero portrait (face crop from the winter photo)
- `photo-ramen.jpg`, `photo-lights.jpg`, `photo-cake.jpg` — the gallery, web-sized
- `source-photos/` — your original photos (kept for re-cropping; not used by the site,
  safe to exclude from deployment)
- `qr.html` — generates the poster QR code once you have the deployed URL

## Before you print the poster — 3 things to do

### 1. Set the real defense details

Open `index.html` and edit the `SITE_CONFIG` block at the very top (it's marked
`✏️ EDIT THIS BLOCK`): date, time, room, dissertation title, optional Zoom link.
The current values are **placeholders** — no public defense announcement existed
as of July 28, 2026 (I checked the Emory Chemistry calendar through Jan 2027).
Flip `confirmed: true` when it's official; until then the site shows a
"details being finalized" tag, and calendar exports carry a "details TBC" note.

The same date/location text also appears once as static HTML inside the defense
card (search for `d-when` — it's the fallback for browsers with JavaScript
disabled). Update it in both places.

### 2. Verify one research finding

Everything on the site comes from public sources (the Ribeiro Group site, ORCID,
arXiv, journal pages), but one link is inferred: Fernando appears to publish under
the author name **"L. Martinez-Gomez"** (the ORCID record 0009-0000-1743-4217
matches his lab bio exactly — UNAM nanotech B.S. 2016–2020, Emory Chemistry since
May 2021 — and he's the only Martinez ever listed in the group). **Please confirm
with Fernando** that those five papers are his before the poster goes up. If not,
delete the Papers section and the 2024–2026 timeline entries.

### 3. Deploy, then make the QR

Any static host works:

- **Netlify Drop** (fastest, free, no account needed to start): drag this folder
  onto https://app.netlify.com/drop → you get a URL in ~10 seconds.
- **GitHub Pages**: push the folder to a repo → Settings → Pages → deploy from branch.
- **Vercel**: `npx vercel` in this folder.

Then open `qr.html` (locally is fine), paste the deployed URL, download the PNG,
and put it on the poster. Print it ≥ 2.5 cm wide per meter of scanning distance
and test-scan the actual printed poster.

## Nice-to-know

- The site is white-themed by default, with a dark "space" theme on the ☾
  button (top right, remembered per visitor). Typography is STIX Two Text
  throughout — the serif used in scientific publishing. The intro always plays
  in space-dark and dissolves into the white page at the end.
- The intro animation plays once per browser session (so it's fresh for every
  QR scan, but doesn't nag on reloads). Tap anywhere, scroll, or press Esc to
  skip it. Add `?static=1` to the URL to skip all animation; it also
  auto-disables for visitors with reduced-motion enabled.
- The countdown flips to a 🎉 message automatically after the defense.
- After deploying, update the `og:image` meta tag to the absolute URL of
  `fernando-hero.jpg` so the link previews nicely in group chats.
