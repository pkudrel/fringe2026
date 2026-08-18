# Fringe 2026 — show browser

A simple static page for browsing the **Edinburgh Festival Fringe 2026** programme and building your own plan. No backend — runs on GitHub Pages and locally.

**Live:** https://pkudrel.github.io/fringe2026/

## Features

- **Search** — title, artist, venue, genre
- **Filters** — day (whole 17–22 window or a specific day), genre, TOP ★ only, free only, in-plan only
- **Sorting** — click a column header (time sorts chronologically)
- **"In plan ✔" column** — your working plan; saved locally in the browser (`localStorage`)
- **💾 Save plan / 📂 Load plan** — export/import the plan as `my_plan.json` (portable between devices)
- **Length column** — each show's running time
- **Clash detection** — a planned show whose time overlaps another (15 min travel buffer) is highlighted with a **red row**
- **TOP ★** — critically-tipped shows (4–5★); extra manual picks live in `EXTRA_TOP` in `index.html`
- **EdFringe ↗** — quick link next to each title to search/buy on edfringe.com

## Files

| File | Role |
|---|---|
| `index.html` | The presentation — all UI and logic |
| `fringe_data.js` | The data — `window.FRINGE_DATA = [...]` (shows playing 17–22 August) |

Both must sit in the **same directory** (repo root). `index.html` loads `fringe_data.js` via a relative path.

## Running

- **Online:** GitHub Pages (Settings → Pages → Deploy from a branch → `main` / `/root`).
- **Locally:** because of `file://` restrictions in some browsers, the two-file version works best served (Pages) or via a local server (`python -m http.server`).

## Data & disclaimer

Data comes from the official Fringe 2026 programme (print edition). **Times and prices may have changed** — confirm and buy tickets only in the official **EdFringe** app / at edfringe.com. Prices include the £1.50 Fringe Box Office fee. The parser is heuristic, so among ~2,500 entries minor inaccuracies are possible.
