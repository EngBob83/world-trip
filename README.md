# World Trip — Leg 1: Reconnection

Static site for Robert's spring/summer 2026 reconnection tour.

## Why plain HTML (not Astro)

Plan said Astro, but the site is one page with a Leaflet map and a list.
A static HTML + CDN Leaflet build has zero install, zero build step, and
deploys to Cloudflare Pages by uploading this directory as-is.

If the site grows (multiple pages, a blog, a CMS), migrate to Astro then.

## Files

- `index.html` — the page
- `nodes.json` — the 10 stops (edit this to update status/dates/windows)
- `emails/` — per-host email drafts (gitignored for drafts)
- `contacts.md` — local host contact info (gitignored)

## Local preview

Any static server. Examples:

```
cd "C:/Users/Robert Rippee/clawd/world-trip"
python -m http.server 8000
# or
npx serve .
```

## Deploy (Cloudflare Pages)

```
npx wrangler pages deploy . --project-name=world-trip --branch=main
```

Custom domain suggestion: `trip.alignedengineeringllc.com` (CNAME to the
`*.pages.dev` hostname after first deploy).
