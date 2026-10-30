# Orawan Anuntakul — UX/UI Designer portfolio

Static site for GitHub Pages. No build step: every page is plain HTML.

## Pages
- `index.html` — Home
- `work/`, `about/`, `contact/`
- `case-studies/faac/`, `prepmate/`, `likeher/`, `no-fuss-meal-plan/`, `ivy-growth-group/`

Each page folder keeps its own `images/`.

## Contact form
The forms on Home and Contact send messages through [Web3Forms](https://web3forms.com) to orawannwcoders@gmail.com.
The access key is set in each of those two pages (`var WEB3FORMS_KEY = ...`). It is meant to be public.
If the key line is ever reset to the placeholder, the forms fall back to opening an email draft.

## Publishing
Repo **Settings › Pages** → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)`.

Source of truth for design rules: `~/nudev/UX-Portfolio` (`design-tokens.css`, `portfolio-brand-guidelines.md`).
