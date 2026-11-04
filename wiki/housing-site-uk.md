---
title: housing-site-uk
type: project
status: active
created: 2026-10-27
updated: 2026-10-29
sources: []
scope: housing-observatory
tags: [project, frontend]
verified_commit: 67286f743523434cd77fb1a46032ba05a92b3815
files: [index.html, Makefile, deploy.sh, data/fetch_into.R, assets/js/stat.js]
---
# housing-site-uk

Static site of the UK Housing Observatory: house price charts, headline statistics and the embedded UK dashboard.

Part of [[concepts/housing-observatory]]. GitHub: `lancs-macro/uk`.

## Stack
Plain HTML/CSS/JS. Charts load JSON from the data API ([[projects/housing-api/housing-api]]): `api.housing-observatory.com/visualizations/uk/rhpi` and `rhpi_yoy`. The dashboard is embedded from Posit Connect Cloud ([[projects/ukdash/ukdash]]); a recent commit migrated it from shinyapps.io.

## Run and test
Serve the folder statically. `make download_json` and `make download_png` refresh `assets/js/stat.js` and the comparison image from `lancs-macro/ukho-dashboard`.

## Deploy
Hosted on Cloudflare Workers static assets (`wrangler.jsonc`), built from GitHub by Workers Builds on push to `main`.

## Layout
- Pages: `index.html`, `about.html`, `dashboard.html`, `resources.html`, `disclaimer.html`, `404.html`, `sitemap.xml`; partials `nav.html` and `footer.html`
- `data/fetch_into.R` data helper (purpose not documented)
- `assets/` css, img, js

## Unknowns
- Overlap with [[projects/housing-site-main/housing-site-main]], which carries the same title and almost the same files.

Related: [[concepts/housing-observatory]], [[conventions]], [[inbox/housing-site-uk]].
