# fastladacad.com

Public landing page for **Fast Lad Academy** — a coaching community for drivers serious about
getting faster. *Come home faster.*

Served via **GitHub Pages** from the `main` branch at the apex domain (`CNAME` → `fastladacad.com`).

## What's here

- `index.html` — the whole landing page. Self-contained: vanilla HTML/CSS/JS, no build step, no
  framework, no external dependency beyond Google Fonts (Cinzel + Inter). Single file so Pages
  can't break it.
- `favicon.svg` — helmet + mustache mark.
- `CNAME` — custom domain (`fastladacad.com`). Don't remove.
- `.nojekyll` — serve files as-is, skip Jekyll processing.
- `robots.txt` / `sitemap.xml` — search hygiene.

## Sections

Hero → mission band → how it works (learn → submit → coached in 48h) → membership tiers
($25 / $50 / $99, with the Founding 500 "25% off for life" scarcity callout) → founding-instructor
credibility strip → FAQ → waitlist capture → footer.

## Two things to wire up before launch

1. **Waitlist form** — currently a [Formspree](https://formspree.io) stub. Create a free form and
   replace `REPLACE_WITH_FORM_ID` in `index.html` (the `<form action>`). Until then the form falls
   back to a `mailto:` handoff so no signup is lost.
2. **Founding 500 counter** — `FOUNDING_CLAIMED` near the bottom of `index.html` defaults to `0`
   ("all spots open"). Bump it as founding members join, or wire it to a live count endpoint.

Optional: drop a `1200×630` `og-image.png` at the repo root and uncomment the `og:image` tag for
richer link previews.

## Brand

- Paddock Gold `#C9A227` — brand / achievement
- Workshop Orange `#FF6B00` — actions / CTAs
- Wax-seal crimson `#8B1A1A` — scarcity / urgency
- Workshop dark `#0E0E10` ground · Cinzel display · Inter body
- Voice: **come home faster.** No competitor names in public copy.

## Local preview

```sh
python3 -m http.server 8080   # then open http://localhost:8080
```
