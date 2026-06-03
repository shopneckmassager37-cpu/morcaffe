# מורקפה — Morcafe

אתר תדמית של מורקפה (Morcafe), עגלת קפה בוטיק ומאפים ביתיים בחצר הראשונים, קיבוץ עלומים (עוטף עזה).

## Project overview

- **Single-file SPA**: the entire site lives in `index.html` — markup, styles and behavior in one file. There is **no build step** and no package manager.
- **Language & direction**: 100% Hebrew, `lang="he"` and `dir="rtl"`. All UI text, `aria-label`s and toasts must be in natural, high-end Hebrew with correct RTL behavior.
- **Tabs, not pages**: navigation swaps in-page views (`#tab-home`, `#tab-story`, `#tab-menu`, `#tab-guide`, `#tab-contact`) via the JS at the bottom of `index.html`; the active tab is reflected in the URL hash.
- **Deployment**: static hosting — open `index.html` directly. Keep it dependency-light (only the Tailwind Play CDN and Google Fonts are loaded).

## Design system (do not drift from this)

Light-mode only. Warm, airy, editorial, photography-first — "Apple meets Aesop meets a boutique bakery". Avoid generic SaaS/dashboard looks.

Color palette (also mirrored in the Tailwind config inside `index.html`):

| Token | Hex | Use |
| --- | --- | --- |
| `canvas` | `#FBF9F6` | global background |
| `sage` | `#5D6B59` | primary accent |
| `taupe` | `#8A7A6E` | secondary accent |
| `espresso` | `#2C2520` | primary text |
| `warmgray` | `#6E645E` | secondary text |

- Fonts: **Frank Ruhl Libre** (serif display) + **Heebo** (sans body).
- Components use `bg-white/70 backdrop-blur-md` with soft borders and large radii.
- Motion must respect `prefers-reduced-motion`. Story chapters reveal one-by-one via an `IntersectionObserver` (`.scroll-reveal`); other content uses the `.reveal` on-tab-activation animation.

## Source-of-truth copy

The Hebrew copy is exact and must not be shortened, genericized or invented. When editing, preserve existing wording; new elements should be complementary and factual.

## Conventions

- Keep everything in `index.html`. Match the surrounding markup style, RTL-aware utility classes, and comment density.
- Verify section/tag balance after edits and confirm all five tab views remain intact.

## Skills

This repo ships the **frontend-design** skill at `.claude/skills/frontend-design/SKILL.md`, installed from
[anthropics/claude-code](https://github.com/anthropics/claude-code.git) (`plugins/frontend-design`).

Use it for any UI/UX work on this site — building or refining components, pages, layouts, typography,
color and motion — to keep the design distinctive and production-grade and to avoid generic "AI slop"
aesthetics. Apply its guidance within the existing light, RTL, boutique design system described above.
