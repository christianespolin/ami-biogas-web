# AMI Biogas International AS — website

The public marketing site for AMI Biogas International AS. One page, no build step.

## Running it locally

It is a static site — any web server will do:

```bash
python3 -m http.server 4317
```

Then open <http://localhost:4317>. Opening `index.html` directly from the filesystem mostly works, but some browsers block web fonts over `file://`, so the server is preferable.

## Deploying

Upload `index.html` and the `assets/` folder as they are. No build, no server-side code, no dependencies. Any static host works (Netlify, Vercel, Cloudflare Pages, or ordinary web hosting).

The production domain is **amibiogas.com**. The absolute URLs in the `<head>` of `index.html` — `canonical`, `og:url`, `og:image` and `twitter:image` — are already set to it, so link previews in email, LinkedIn and Slack resolve correctly. If the site ever moves, update those four and regenerate nothing else.

## Editing

Everything is hardcoded and meant to be edited by hand.

| What | Where |
|---|---|
| All copy and every figure | `index.html` |
| Colours, type, spacing, layout | `assets/ami.css` (tokens are at the top, under `:root`) |
| Logo | `assets/ami-logo.svg`, also inlined once in `index.html` as `<symbol id="wm">` |
| Diagrams | `assets/model.svg`, `assets/digester.svg`, `assets/methane-chart.svg` |
| Photography | `assets/hero-plant.webp`, `assets/ref/`, `assets/team/` |
| Social share card | `assets/og.jpg` (1200 × 630) |

Figures live in plain text in `index.html` — search for the number and change it. The section labels, headings and footnote lines follow the same pattern throughout, so a new section can be copied from an existing one.

## A note on what goes in here

This repository is public, and the site is written for an audience that includes investors, lenders and counterparties.

The content was selected deliberately: commercially sensitive material from the investor and board papers — financial projections, plant economics, facility terms, counterparty names, group structure and diligence-stage risk detail — is **excluded by design**, not by accident. Named counterparties appear in descriptive form only.

Please check before adding figures or naming parties.

## Fonts

IBM Plex Sans and IBM Plex Mono, self-hosted in `assets/fonts/` (SIL Open Font License).
