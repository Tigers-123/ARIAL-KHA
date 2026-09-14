# ARIALKHA AGRO — Frontend Design Direction
**Concept: "Paddy Row Editorial"** · v0.1 · Design-lead summary

## What's in this package
- `index.html` — full homepage prototype (static, self-contained): hero, trust/why section, featured products, sourcing story, reviews, FAQ, newsletter, footer. Includes working **EN ⇄ বাংলা toggle** (localStorage-persisted), cart-count micro-interaction, FAQ accordion, toast notifications, responsive layouts from 320px to 1920px+, `prefers-reduced-motion` support.
- `styleguide.html` — tokens, type specimens (EN + BN), buttons, badges, motif usage, accessibility/contrast notes, paste-ready CSS variables.
- `DESIGN.md` — this document.

## The distinctive point of view
The brand is **heritage rice from specific Bengal farmland** — so the interface borrows from a *printed harvest journal*, not an app UI kit:
- **Editorial serif display (Fraunces)** with **Noto Serif Bengali** for Bangla display and **Hind Siliguri** for Bangla body — bilingual-first, not translated-after.
- **Signature motif:** fine horizontal "paddy-row" line stacks (pure CSS `repeating-linear-gradient`, edge-masked) used as section dividers — a fingerprint of terraced fields. Zero images, zero JS, instant paint.
- **Hand-drawn inline-SVG illustration** (terraces at sunset, farmer silhouette, rice-sack product marks) instead of stock photos — swap for duotone-treated R2 photography in production.

## The one aesthetic risk (justified)
1. **The CTA is mustard, not green.** Every natural brand makes green the action color. Here green = trust/identity (header, footer, "why" section); `--sun #E2A52B` = action. Mustard is the literal color of harvested paddy, and it passes WCAG AA comfortably (dark text #3A2A05 on #E2A52B ≈ 8.5:1; on deep-green sections with a 3px mustard focus ring it's fully keyboard-accessible).
2. **Husk-brown ink (#2B2618), never pure black** — keeps long Bangla reading warm and reinforces "paper & grain."
3. **Oversized Bengali glyphs ("ধান", "মাটি, পানি, রোদ") as background art** inside an English-first hero — the client's bilingual mandate made visible rather than hidden in a settings menu.

## Rules that keep it from drifting into template territory
- One accent color per screen region. Blue (`--water`) is information/status only — never a CTA.
- Crossed-out prices exist only for real, dated campaigns.
- Motion: ≤300ms, translate/scale only, killed under `prefers-reduced-motion`.
- Primary button = "seed pressed into soil" 3D shadow that compresses on click.

## Notes for build phases
- Logo mark in the prototype is a **placeholder drawn from the brief** (hills / river / sun / sprout in a roundel). Replace with the supplied ARIALKHA AGRO logo asset 1:1 — proportions locked, `favicon` from the same SVG.
- Fonts are Google Fonts CDN here; self-host subsets (Bengali unicode-range) in production for Core Web Vitals.
- This prototype is the **Phase 1 visual foundation**; the `styleguide.html` token block is the source of truth for the Tailwind/Next.js theme in later phases.
