# QA Report — Trail Monkeys Rosenheim Static Site

**Status:** Prototype complete — ready for local testing
**Date:** 2026-03-14

---

## Pages Implemented

| Page | File | Status |
|---|---|---|
| Homepage | `index.html` | Complete |
| Training | `pages/training.html` | Complete |
| Anmeldung | `pages/anmeldung.html` | Complete (form placeholder) |
| Galerie | `pages/galerie.html` | Complete (image placeholders) |
| Kontakt | `pages/kontakt.html` | Complete |

---

## CSS Files

| File | Purpose |
|---|---|
| `assets/css/design-tokens.css` | Color vars, font tokens, spacing scale |
| `assets/css/base.css` | Reset, typography, global elements |
| `assets/css/layout.css` | Header/nav, hero, page hero, footer, grids |
| `assets/css/components.css` | Buttons, cards, training blocks, lightbox, form |

---

## Assets Used

| Asset | Status | Notes |
|---|---|---|
| `assets/logo/trail-monkeys-embedded.svg` | Present | 810 KB, base64 PNG embed. Displays correctly. |
| `assets/img/hero-bg.webp` / `hero-bg.jpg` | **Missing** | Hero falls back to dark gradient. Add real trail photo. |
| `assets/img/foto-*.webp` / `foto-*.jpg` | **Missing** | Gallery shows placeholder tiles. Add real photos. |
| `assets/fonts/` | Empty | System font stack used. Add woff2 files if branded font available. |

---

## Known Placeholders (TODOs)

| Location | Item | Priority |
|---|---|---|
| `pages/training.html` | Exact training times for both groups | High |
| `pages/anmeldung.html` | Real Google Form URL | High |
| `index.html` | Hero background image | High |
| `pages/galerie.html` | All gallery photos | Medium |
| All pages | Datenschutz (Privacy Policy) link | High (legal requirement) |
| All pages | Impressum link | High (legal requirement) |
| `index.html` | Final domain in JSON-LD | Low (pre-launch) |
| `pages/training.html` | Gear list confirmation | Low |
| `assets/fonts/` | Branded woff2 font files | Low |

---

## Accessibility

- Skip-to-content link implemented on all pages
- `aria-current="page"` on active nav links
- All images have descriptive alt text (or `alt=""` for decorative)
- Focus outlines visible (`:focus-visible` global styles)
- Lightbox: keyboard accessible (ESC, arrow keys, Tab trap, focus restore)
- Gallery items: keyboard-openable via Enter/Space
- Mobile nav: CSS-only hamburger (no JS required)
- JSON-LD Organization structured data on homepage

---

## Content Sources

All content taken from the existing website at `trendsport-rosenheim.de`:

- Org name: Trendsport TSV 1860 Rosenheim e.V.
- Age groups: 4–6 and 7–12 years
- Location: Dirtpark Rosenheim, Lortzingstraße 15, 83024 Rosenheim
- Season: April to October, Wednesday & Friday
- Costs: €35/month (first child), €30/month (siblings), 2 free trials
- Trainers: Jonas Droste (jonas.droste@gmx.de), Andy Rieger (andyrieger@me.com)
- Verein address: Jahnstraße 25, 83022 Rosenheim, Tel. 08031 12639
- Instagram: @trailmonkeys.rosenheim

---

## Next Steps

### Before first real use
1. Add real hero background photo (`assets/img/hero-bg.webp` + `.jpg`)
2. Insert real Google Form URL in `pages/anmeldung.html`
3. Fill in exact training times in `pages/training.html`
4. Create `pages/datenschutz.html` (DSGVO — legally required in Germany)
5. Create `pages/impressum.html` (TMG §5 — legally required in Germany)
6. Update footer links to point to the new pages

### Nice to have
7. Add 6–12 real gallery photos
8. Add branded woff2 font files if available
9. Confirm gear list with trainers and update `pages/training.html`

### Hosting & deployment (post-prototype)
10. Register domain (e.g. trail-monkeys-rosenheim.de)
11. Deploy via Netlify drag-and-drop (free tier sufficient for static site)
    - Drag the `trail-monkeys-site/` folder into the Netlify UI
12. Or use Vercel: `npx vercel` in the project folder
13. Update JSON-LD `url` in `index.html` to final domain
14. Set up redirect rules if needed (e.g. www → non-www)
15. Optional: add GitHub repo + Netlify auto-deploy on push
