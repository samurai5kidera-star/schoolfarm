# School Farm — Dev Notes

## Project Overview
Static single-page HTML site (Japanese corporate website for "School Farm").
No backend, no build system, no external dependencies. All CSS and JS are inline
in `schoolfarm_v5.html` (~6MB). `README.md` is a near-identical copy of the same HTML.

## Running the App
```
docker compose -f docker-compose.base44.yml up -d
```
- Served by `npx serve` (static file server) on host port 3000.
- `index.html` is a tiny redirect page → `/schoolfarm_v5` (serve's clean-URL route).
- No credentials or external services required.
- Google Fonts are loaded from CDN at runtime (browser-side).

## Editing
Edit `schoolfarm_v5.html` directly. There is no live-reload dev server; after
changes, call `reload_preview` so the user sees the update.

## Preview Screenshot Note
The page is ~6MB of HTML with complex inline CSS. `preview_screenshot` will time
out on it (too heavy for the foreignObject capture method). The iframe IS alive
and the page renders correctly — verify via `preview_execute_code` (DOM checks)
instead of screenshots.
