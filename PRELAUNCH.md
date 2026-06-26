# Landing Page — Pre-Launch Checklist

Source: multi-agent pre-launch audit, 2026-06-25. Pricing corrected locally same day (commit pending).
The page is **not deployed** — live `fastladacad.com` still serves the old placeholder until pushed.

## ✅ Brand rebuild applied 2026-06-26 (DECISIONS #42 — product-led, professional)
Full clean rebuild of `index.html`: retired the Cinzel/medieval/heraldic system (crests, crown, shields);
moved to **Archivo + Inter** type, **near-black base + single orange accent** (gold/crimson gone);
product-led hero with a coached-review preview mock + "Drive. Upload. Improve."; credibility reframed to
"coaches who've raced where you're headed" with one quiet national-level line (no champion banners).
This **resolves** the earlier should-fix items: palette confirm, the hero "cheaper-than" framing, and the
loud champion/credential claims. `twitter:card` downgraded to `summary` (no broken large card).

## ✅ Done this session — pricing/content now matches DECISIONS #38–40
- Paddock $25→**$29** (founding $18.75→**$21.75**)
- **Hot Lap tier deleted** (retired); Grid promoted to the featured "Most popular" card
- Grid: "Everything in Hot Lap"→"Everything in Paddock"; "2 reviews"→**1 included review/mo (a $119 value)**
- Grid perks → **Driver's Meetings** + **Live In-Car** (canonical #40 exclusives)
- À-la-carte → **$119 non-member/Paddock, $99 Grid** (Paddock bullet + tiers-note)
- "Pit Wall" → **Open Pit / Driver's Meetings / Live In-Car** (Paddock bullet + FAQ)
- Founding-lock now carries the **continuity caveat** ("…as long as your membership stays active")
- CSS tier grid 3→2 columns, centered; no-JS `.reveal` fallback added

## 🔴 Go-live blockers (need Dylan)
1. **Formspree form id** — replace `REPLACE_WITH_FORM_ID` in the form `action`, submit a test email, confirm it lands. Until then every signup falls back to mailto (leads silently lost on no-mail devices).
2. **`git push origin main`** — the new page exists only as a local unpushed commit; pushing is what makes it live.
3. **HTTPS cert** — repo Settings → Pages → re-save the custom domain to retrigger Let's Encrypt, then tick **Enforce HTTPS**. (Currently GitHub serves its default `*.github.io` cert, so `https://fastladacad.com` fails. Grey-cloud Cloudflare DNS — done — is what lets this provision.)

## 🟡 Should-fix before broad promotion (judgment calls)
- **Privacy + Terms** — page collects email PII with no Privacy/Terms link (GDPR/CCPA exposure; Terms should carry the motorsport assumption-of-risk). Drafts exist in `~/projects/fla/legal/` but aren't web-published. Add footer links + a one-line consent note by the email field; ship at least a `/privacy` stub. **Highest-priority should.**
- **Champion/"credentialed" claims** — stated as present fact for a cohort not yet signed (NDA pending). Confirm + document the titled instructors before launch, or soften to defensible language ("experienced club racers", "raced at a national level") until contracts are in.
- **Hero frame line** — "One track weekend costs $500 … one month costs less" trips the *"Plus, not vs."* rule (and contradicts the FAQ). Suggested reframe: *"You already spend $500+ on a track weekend. Membership — for less than that, every month — is what turns those laps into time you keep."*
- **"48 hours"** — stated as a hard guarantee before any review delivered (hero pill, step 3, the "48h" stat tile, FAQ, meta). Soften to "typically ~48h" to avoid refund pressure on the first slip.
- **OG share image** — still no `og-image.png`. `twitter:card` now set to `summary` (safe, no broken card). To upgrade: produce a 1200×630 PNG in the **new brand (near-black + orange, Archivo)**, drop it at repo root, uncomment the `og:image` block, and restore `twitter:card` to `summary_large_image`.
- **Palette confirm (brand owner)** — gold token is `#C9A227`; spec says Limestone Gold `#C4A35A`. Orange is the dominant CTA color on a Paddock/marketing surface (spec reserves orange for the in-app Workshop). Wax-seal crimson is a 3rd, unsanctioned accent. Bless or adjust.

## ⚪ Nice-to-have
- Meta description ~197 chars → tighten to ~155 so the tagline isn't truncated in search.
- JSON-LD Organization: add `logo` + `sameAs` (no Offer/price fields — avoids a price-sync liability).
- `FOUNDING_CLAIMED` counter hard-coded to 0 ("Now open") — fine for launch; bump as members join or wire to the FLA count endpoint.
