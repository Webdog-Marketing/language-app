# Revision cards: Polish & Brazilian Portuguese

Flashcards, quizzes and full reference tables for Polish and Brazilian Portuguese verbs, days, times of day, clock time and months.

It's a plain static site with no build step: everything lives in `index.html`.

## Files

| File | What it does |
| --- | --- |
| `index.html` | The whole app: card data, styles and code |
| `manifest.webmanifest` | Lets phones install it to the home screen |
| `sw.js` | Makes it work offline after the first visit |
| `icon-*.png`, `apple-touch-icon.png`, `favicon.png` | App icons |
| `vercel.json` | Stops the offline file being cached too long |

## Deploying on Vercel

Import the repo in Vercel and leave everything on the defaults: Framework preset **Other**, no build command, no output directory.

## Adding or changing cards

Edit `index.html` in GitHub (pencil icon), commit, and Vercel redeploys automatically. Card data sits in clearly labelled blocks near the top of the `<script>`: `PLV` (Polish verb tables), `PL_MEAN`, `PL_DAYS`, `PTV` (Portuguese verb tables), `PT_MEAN`, and so on. The Tables tab builds itself from the same data, plus the `REF` and `NOTES` blocks.

When you change the app, bump the version in `CACHE = "revision-cards-v2"` in `sw.js` (v2 → v3, and so on) so phones pick up the new version straight away.

Progress (known cards, best scores) is saved in each browser, so it doesn't sync between devices.
