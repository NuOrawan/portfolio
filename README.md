# Nu — UX Portfolio

A calm, editorial UX/UI portfolio site: three static pages built from an approved §6 component system.

## Pages

- `index.html` — homepage (nav, hero intro, selected-work project cards, contact)
- `about.html` — about page (nav, bio hero, "How I Work" process stepper)
- `case-study.html` — case-study page template, using the LikeHer project as the live example ("Discovery → Define → Ideate → UI → Validate" sidebar stepper, plus a "more to explore" project-card section at the end)

Each page is self-contained (CSS inlined) and links to the others by relative path, so this works as-is on GitHub Pages or any static host — just set the Pages source to the repo root (or `main` branch) and `index.html` is the entry point.

## Design system

- `design-tokens.css` — the CSS custom properties (color, type, spacing) used across all three pages. Current accent pair: **terracotta** (`--color-accent-terracotta`, `#D99A7C`) and **seafoam** (`--color-accent-seafoam`, `#A8CFC3`), replacing an earlier sage/blush pair.
- `portfolio-brand-guidelines.md` — the full design-system spec (brand positioning, color/type/spacing rules, and the five approved §6 components: nav, buttons, project card, case-study hero, process stepper) that the three pages were assembled from. Updated in this repo to reflect the terracotta/seafoam swap.

### A known caveat, left as-is rather than silently fixed
Terracotta/seafoam fail WCAG AA text-contrast (4.5:1) against the light-mode background tokens — same limitation the original sage/blush pair had. They're safe as decorative/accent moments (dots, underlines, borders) and read fine on the dark-mode backgrounds, but shouldn't be used as text color on a light surface.

### Process changes going forward
Any future change to a color, spacing value, or component rule should be proposed first, confirmed, applied to `design-tokens.css` / `portfolio-brand-guidelines.md` first, and then propagated through the three pages — see the project's `portfolio-design-change-workflow` skill for the full process.

## Theme

All three pages support light/dark mode: automatically via the OS/browser (`prefers-color-scheme`), or manually via the toggle button in the nav bar (labeled "Dark" / "Light" for whichever mode you'd switch *to*).

## Notes

- The homepage's "Contact" button uses a placeholder email (`hello@example.com`) — update it to your real address.
- The About page's bio, meta row (role/city/focus), and "How I Work" process copy are placeholder text — no About-page copy had been approved yet when these pages were assembled, so the layout/components are the approved ones but the words are drafts to replace.
- The case-study page's process-stepper copy (family-health-history interview content) doesn't actually match the LikeHer dating-app narrative in its own hero — that mismatch predates this repo and wasn't invented here; it's flagged rather than silently rewritten. Worth reconciling before publishing live.
