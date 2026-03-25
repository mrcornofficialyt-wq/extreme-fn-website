# Extreme FN Macros — Website

> Host this on GitHub Pages.

## Setup

1. Create a GitHub repo (e.g. `extreme-fn`)
2. Upload the contents of this `website/` folder to the repo root
3. Go to **Settings → Pages → Deploy from branch → main → / (root)**
4. Your site will be at `https://YOUR-USERNAME.github.io/extreme-fn/`

## Required Changes Before Deploying

### `index.html`
- No changes required for static functionality
- The code input uses `localStorage` as fallback when no backend API is present
- For full server-side code validation, you need the bot running on Railway

## Files
- `index.html` — main site
- `icon.png` — app logo (upload this!)
- `downloads/ExtremeFN-Setup.exe` — place your built .exe here

## Connecting to the Bot (Railway)
The website makes API calls to:
- `POST /api/validate-code` — validate access codes
- `POST /api/track-visit` — log visitors
- `POST /api/track-exit` — log time on site

Update the `fetch` URLs in `index.html` to point to your Railway deployment URL.

```js
// In index.html, find:
const res = await fetch('/api/validate-code', ...);
// Change to:
const res = await fetch('https://YOUR-APP.railway.app/api/validate-code', ...);
```
