# Portfolio Brand & Design System Guidelines

> **Purpose of this document:** This file is written to be read directly by Claude (Desktop) as a design-system spec. It defines every visual rule needed to design and build a UX/product-designer portfolio site — colors, type, spacing, components, and usage logic — derived from a design teardown of reference screenshots. Claude should treat every token and rule below as binding unless the user explicitly overrides it in a conversation.

---

## 0. How This Document Was Built (read this first)

The source material was a set of camera photos of a reference portfolio site (case studies: *LikeHer*, *Isle*, *Mirror*). Photos of a screen introduce a blue color-cast, glare, and moiré — so **exact hex values could not be extracted pixel-for-pixel with confidence.** What follows is a *calibrated* palette and system: the color relationships, typographic pairing, hierarchy, and component patterns are analyzed with high confidence; the specific hex values are expert-judgment approximations of what those swatches represent once you correct for camera distortion.

**Action item for the user:** if you get access to the live site, a Figma file, or brand assets later, drop them in and I'll swap the approximate hex values below for exact ones in five minutes. Everything else in this system (type pairing, spacing, component rules) will not need to change.

---

## 1. Brand Positioning & Personality

The reference aesthetic reads as: **editorial, calm, confident, human-centered.** It borrows conventions from print editorial design (large serif display type, generous whitespace, italic pull-quotes) and applies them to a UX portfolio — signaling "thoughtful designer" rather than "flashy developer."

**Personality traits to design toward:**
- Warm minimalism — not stark/clinical, not maximalist
- Editorial confidence — big type, short copy, lots of breathing room
- Soft, human accent colors rather than saturated "tech" colors
- Quiet structure — numbered systems (01, 02, 03) that suggest process and rigor without feeling corporate

**One-line brief:** *"A design magazine profile, not a SaaS landing page."*

---

## 2. Logo / Brand Mark

**Pattern observed:** a minimal monogram badge — lowercase initials stacked/interlocking inside a solid dark circle, rendered in a thin sans-serif, placed top-left of the nav bar at small scale (roughly 32–40px diameter).

**Rules to apply to your own mark:**
- Use your own initials (1–3 lowercase letters), stacked or interlocked, centered inside a solid-fill circle.
- Circle fill: Ink/near-black (see §3). Letterforms: background color (near-white), thin sans-serif weight.
- Keep it small and quiet — it's a wayfinding mark, not a hero element. Never scale it above ~48px in the nav.
- Do not add gradients, drop shadows, or outlines to the badge.
- Clear space: minimum 12px on all sides from other nav elements.

---

## 3. Color System

### Design logic
The palette is built on a **60/30/10 rule**: a soft neutral base (60%), ink for text and structure (30%), and a two-tone accent pair borrowed from the case-study work itself (10%, used sparingly as highlight/CTA moments only).

### Core tokens

| Token | Approx. Hex | Usage |
|---|---|---|
| `color-bg-base` | `#F7F8F6` (off-white, warm neutral) | Page background, default surface |
| `color-bg-muted` | `#EDEFEB` | Section alternation, card backgrounds |
| `color-ink-900` | `#12181F` (near-black navy-charcoal) | Primary headlines, high-emphasis text |
| `color-ink-700` | `#2B333C` | Body copy |
| `color-ink-500` | `#6B7480` | Secondary text, eyebrows, metadata labels |
| `color-ink-300` | `#B7BEC6` | Dividers, disabled states, hairline borders |
| `color-accent-terracotta` | `#D99A7C` (warm terracotta) | Primary accent — links, active states, highlights |
| `color-accent-seafoam` | `#A8CFC3` (dusty seafoam) | Secondary accent — highlight underlines, tags, decorative moments |
| `color-white` | `#FFFFFF` | Cards, reversed text on dark |

> **Update (superseded from the original sage/blush pair):** the accent pair was changed to terracotta/seafoam after a contrast review — sage/blush is kept only as a historical reference in `design-tokens.backup-sage-blush.css`. Note terracotta/seafoam still fail WCAG AA (4.5:1) against the light-mode backgrounds above, same as the original pair did — reserve them for small accent moments on dark surfaces or non-text decoration, not for text needing AA contrast on a light background.

### Usage rules
- **Never** use pure black (`#000000`) or pure white text-on-white. Always use the ink scale above — it's warmer and softer than true black/white.
- Terracotta and seafoam are **accent-only** colors. They should never be used as large background fills or body text color — reserve them for: active-state dots, underline highlights behind a word/title, small tags/badges, and illustration/UI-mockup color inside project imagery.
- Backgrounds stay overwhelmingly neutral (off-white). Color enters through imagery (app screenshots, photography) and small accent moments — not through painted background blocks.
- Maintain WCAG AA contrast: `color-ink-700` or darker for any body text on `color-bg-base`.

### Dark mode (optional, if the portfolio supports it)
Invert the neutral scale (`#12181F` background, `#F7F8F6` text) and keep terracotta/seafoam accents unchanged — they read fine on dark.

---

## 4. Typography System

### Font pairing
Two-typeface system, editorial-style: a **high-contrast serif for display/headlines** paired with a **clean humanist sans-serif for UI and body copy.**

| Role | Reference feel | Recommended free/Google Fonts equivalent |
|---|---|---|
| Display serif | Elegant, high stroke-contrast serif (Didone/transitional character) | **Fraunces** (or Playfair Display, GT Sectra Display as paid alt) |
| UI / body sans | Clean, geometric-humanist sans | **Inter** (or Work Sans, General Sans as alt) |

Load both via Google Fonts / self-hosted `.woff2` for performance. Do not substitute a third typeface anywhere in the system.

### Type scale & usage

| Style | Font | Weight | Size (desktop) | Size (mobile) | Letter-spacing | Usage |
|---|---|---|---|---|---|---|
| Display / H1 | Fraunces | 400–500 | 64–80px | 36–44px | -0.5px | Hero headline, "About [Name]", project title on case study hero |
| H2 | Fraunces | 400 | 40–48px | 28–32px | -0.25px | Section titles within a case study |
| H3 / Subhead (sans) | Inter | 600 | 20–22px | 18px | 0 | "User Interviews", sub-section labels |
| Eyebrow / Label | Inter | 600 | 12–13px | 12px | +1.5px, UPPERCASE | "01. DISCOVERY", "UX/UI DESIGNER, BRANDING", "ROLE", nav-adjacent metadata |
| Body | Inter | 400 | 16–17px | 15–16px | 0 | Paragraph copy |
| Pull-quote | Fraunces | 400 italic | 22–26px | 18–20px | 0 | Interview quotes, testimonials — always italic serif, never sans |
| Nav link | Inter | 500 | 15px | — | 0 | "Work / About / Contact" |
| Button label | Inter | 600 | 14px | — | +0.5px, UPPERCASE optional | CTA text |

### Hierarchy rules
- **Only serif italic is used for direct quotes.** This is a signature move in the reference — it visually separates "user's voice" from "designer's voice" (sans-serif). Preserve this distinction; don't italicize anything else.
- Eyebrows are always Inter, uppercase, small, and in `color-ink-500` — they never compete with the headline below them.
- Never mix serif into UI chrome (nav, buttons, form labels) — serif is reserved for editorial/content moments only.
- Line-height: 1.1–1.2 for display serif, 1.5–1.6 for body sans.

---

## 5. Layout & Spacing

- **Grid:** 12-column grid, max content width ~1200–1280px, generous outer margins (80–120px desktop, 24px mobile).
- **Spacing scale (8px base unit):** 8 / 16 / 24 / 32 / 48 / 64 / 96 / 128px. Section vertical padding should sit at 96–128px desktop, 48–64px mobile — the reference relies heavily on whitespace to feel editorial rather than dense.
- **Whitespace principle:** when in doubt, add more space. Dense layouts contradict the brand personality.
- Text blocks (body copy) should be width-constrained to ~60–70 characters per line even on wide screens — don't let paragraphs stretch full-width.

---

## 6. Components

### Navigation
- Fixed/sticky top bar, transparent or matching page background (no hard-edged nav bar with its own contrasting fill).
- Logo badge left, 3–4 text links right (`Work`, `About`, `Contact`), Inter Medium, generous horizontal spacing (32–40px between links).
- Active/current page link gets a thin underline in `color-ink-900`.

### Buttons
- Two styles only:
  1. **Ghost/outline button** (primary CTA seen in reference — e.g. "View Final Prototype"): 1px `color-ink-300` border, transparent fill, `color-ink-900` text, fully rounded or 6–8px radius corners, generous horizontal padding (24–32px), on hover fill with `color-ink-900` and invert text to white.
  2. **Text link with arrow**: for lower-emphasis actions ("View work"), Inter Medium, underline on hover.
- Never use a solid saturated-color filled button — it breaks the neutral-first palette rule.

### Case-study hero
- Two-column layout: left = eyebrow (year/date) + serif title + short description + metadata list (Role / Duration / Read time, each as Eyebrow-label-over-value pairs) + CTA button. Right = device mockup or app-screen collage, angled/tilted for visual energy.

### Section eyebrow + divider
- Pattern: a short 24–32px horizontal rule immediately followed by uppercase Eyebrow text (e.g. `— THE PROCESS`). Use this whenever introducing a new content section within a case study.

### Process stepper / Table of contents
- Horizontal step list at top of section (`01. DISCOVERY  02. DEFINE  03. IDEATE  04. UI  05. VALIDATE`), Inter Semibold, uppercase, current step in `color-ink-900`, future steps in `color-ink-300`.
- Mirrored as a **sticky vertical sidebar** during scroll: same labels, sentence case, with a small dot indicator — filled `color-accent-terracotta` for the current/active section, hollow gray for others.
- Include simple prev/next/play navigation controls (circular icon buttons, muted fill) if the case study is presented as a slide-like sequence.

### Project cards (index / "other projects")
- Bordered container (thin 1px `color-ink-300` hairline, generous internal padding), device mockup image centered/top, serif project title centered below image, Eyebrow-style role label beneath the title in `color-ink-500`.
- On hover: subtle lift (translateY -4px) + soft shadow, border color deepens to `color-ink-900`.

### Highlight underline
- Signature micro-detail: a project title (e.g. "LikeHer") gets a horizontal band of `color-accent-seafoam` sitting behind/under the baseline of the text, like a highlighter stroke. Use this exactly once per project title as a branding flourish — don't overuse it elsewhere.

### Media frames
- All device mockups (laptop/phone) use realistic hardware frames, slightly rotated/layered when shown as a collage, flat/front-facing when shown as a single hero shot.

---

## 7. Imagery & Iconography

- Personal/portrait photography: desaturated or black-and-white treatment (see "About" page portrait) — keeps focus on typography and case-study color rather than competing with photo color.
- Case-study UI screenshots retain their **full native color** (this is where terracotta/seafoam and other app-specific colors are allowed to appear richly) — they're the one place saturated color lives on the page.
- Icons: simple line-style, circular muted-gray containers for playback/navigation controls (prev/play/next), consistent stroke weight, no fill unless indicating an active state.

---

## 8. Voice & Tone (writing style)

- First-person, warm, concise: *"I'm [Name], a UX Designer creating empathetic, human-centered solutions."*
- Case-study copy is structured and numbered (process-driven), but individual sentences stay plain and human — avoid jargon-heavy corporate language.
- Metadata is presented as quick-scan labeled facts (Role / Duration / Read time) rather than buried in paragraphs.

---

## 9. Do / Don't Summary

**Do**
- Keep backgrounds neutral; let accent color come from case-study imagery and small highlight moments.
- Use serif only for display headlines and italic quotes.
- Use generous whitespace and a consistent 8px spacing scale.
- Keep buttons outlined/ghost-style, not solid-filled.

**Don't**
- Don't introduce a third typeface.
- Don't use saturated accent colors as large background fills.
- Don't italicize anything except direct quotes.
- Don't crowd sections — when unsure, add more vertical space, not less.

---

## 10. Implementation Notes for Claude (Desktop)

When building the actual site from this spec:
- Treat §3 and §4 tables as CSS custom properties / design tokens (e.g. `--color-ink-900`, `--font-display`, `--space-4`) at the top of the stylesheet.
- Build components (nav, button, project card, case-study hero, TOC stepper) as reusable pieces per §6 before assembling pages — the reference site reuses these same 5–6 components across every page.
- Default to the neutral/light theme; only build dark mode if the user asks.
- If the user provides real project names/colors/copy, slot them into this same structure rather than redesigning the system.
