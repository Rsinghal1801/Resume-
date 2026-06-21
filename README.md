# Raghav Singhal — Command Deck (3D Resume World)

An interactive, real-time 3D resume built with **Three.js**. A sci-fi space-station
"command deck": scroll to fly the camera through 7 holographic stations, or click a
node on the left rail to jump. Features a custom-built quadcopter, an autonomous car,
a holographic **RS** monogram core, and bloom-lit neon visuals.

## Files
- `index.html` — the entire site (self-contained, Three.js loaded from CDN)
- `raghav_singhal_resume.pdf` — your résumé, wired to the download buttons
- `.claude/launch.json` — local preview config (not needed for hosting)

## Run locally
Any static server works. Easiest:
```bash
# from this folder
python -m http.server 8123
# then open http://localhost:8123
```
> Opening `index.html` directly with `file://` mostly works, but a server is
> recommended so the PDF download and CDN modules load reliably.

## Deploy to a live URL (pick one)

### Option A — Netlify (no account-config, drag & drop)
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page.
3. You get a live URL instantly (rename it in Site settings).

### Option B — Vercel
```bash
npm i -g vercel
vercel        # run in this folder, accept defaults
vercel --prod # promote to production URL
```

### Option C — GitHub Pages
```bash
git init
git add .
git commit -m "3D resume world"
git branch -M main
git remote add origin https://github.com/Rsinghal1801/<repo-name>.git
git push -u origin main
```
Then on GitHub: **Settings → Pages → Source: Deploy from branch → `main` / root**.
Your site goes live at `https://rsinghal1801.github.io/<repo-name>/`.

## Customize
- **Text / sections:** edit the `<section class="panel">` blocks in `index.html`.
- **Rotating headline:** the `roles` array in the `<script>`.
- **Colors:** the `--cyan` / `--purple` / `--pink` CSS variables at the top, plus
  the `CY`, `PU`, `PK` constants in the script (keep them in sync).
- **Links:** search for `Rsinghal1801`, `raghav-singhal18`, and the email to update.
- **Add a real photo later:** drop it into a panel's `.card` — the layout flexes.

## Notes
- Works on desktop + mobile (touch scroll). Respects `prefers-reduced-motion`.
- Camera path nodes live in the `NODES` array; add/remove a station by editing
  `NODES`, the matching `LABELS`, and adding a `.panel` + a `.panelStop` div.
