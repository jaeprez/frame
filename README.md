# FRAME

Programs and protocols for the self.

A single-file terminal/HUD interface for running the things you're actually doing. **Programs** are the recurring ones — the daily and weekly habits. **Protocols** are the finite ones — projects with an end state. Everything lives in one HTML file, saves to your browser, and exports to JSON.

## Running it

Open `index.html`. That's the whole thing — no build step, no server, no dependencies.

To keep it on your phone: open the hosted URL in Safari or Chrome, then Share → Add to Home Screen. It launches fullscreen with no browser chrome.

## Hosting

GitHub Pages: Settings → Pages → Deploy from branch → `main` / `root`. Live at `username.github.io/frame` in about a minute. Note that Pages requires a public repo on free accounts — if you want this private, use Netlify or just open the file locally.

## Head tags

If they aren't in `index.html` yet, add these inside `<head>` so the icon and fullscreen behavior work:

```html
<link rel="manifest" href="manifest.json">
<link rel="icon" href="favicon.ico" sizes="any">
<link rel="icon" type="image/svg+xml" href="icons/frame-icon-b.svg">
<link rel="apple-touch-icon" href="icons/frame-icon-b-180.png">
<meta name="theme-color" content="#0A0C0E">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="FRAME">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
```

## Data

State is stored in `localStorage` under the browser and origin you opened it from. Two consequences worth knowing:

- Local file and hosted URL are separate stores. Data won't follow you between them.
- Clearing site data wipes it. Export to JSON before you clear anything, and periodically anyway.

## Files

```
index.html          the app
manifest.json       home-screen install config
favicon.ico         browser tab icon
icons/              app icons, plus the SVG source
.gitignore
```

## Icon

Bracket set inside a hairline boundary — a frame within a frame. Ice on near-black: `#E2EDF3`, `#4E6875`, `#0A0C0E`. Edit `icons/frame-icon-b.svg` to retheme, then re-export the PNGs at 1024, 512, 192, 180, 32, and 16.

## Changelog

**Build 2** — Added the outcomes layer and `hold until <reason>`. Ice set as the default theme.

**Build 1** — Programs and protocols, autosave, JSON export.
