# Wyman Reporting

Static hosting for the Kristin Wyman Agency campaign reports, deployed on Vercel.

## What's here

| Path | Description |
| --- | --- |
| `index.html` | Kristin Wyman Agency — Campaign Configuration (2026-09-11). Served at the site root. |
| `vercel.json` | Vercel config: static site, no build step, caching and security headers. |
| `.vercelignore` | Keeps repo metadata out of the deployment bundle. |

The report is fully self-contained: all images are inline base64 and the only
external request is the Inter webfont from Google Fonts. There is no build
step, no framework, and no dependencies.

## Deploying

Import the repo at [vercel.com/new](https://vercel.com/new):

- **Framework Preset:** Other
- **Root Directory:** `./`
- **Build Command:** leave empty (overridden to none by `vercel.json`)
- **Output Directory:** leave empty — files are served straight from the repo root
- **Install Command:** leave empty

Every push to the default branch triggers a production deploy; pushes to other
branches get preview URLs.

## Adding another report

1. Drop the new HTML file in the repo root, e.g. `2026-10-15-campaign-review.html`.
2. Thanks to `cleanUrls`, it will be reachable at `/2026-10-15-campaign-review`.
3. Commit and push — Vercel redeploys automatically.

To make a newer report the landing page, replace `index.html` with it and keep
the previous one under its dated filename.

## Access

`X-Robots-Tag: noindex, nofollow` keeps these reports out of search engines,
but the URL is public to anyone who has it. For client-only access, turn on
Vercel Deployment Protection (password or SSO) in the project settings.
