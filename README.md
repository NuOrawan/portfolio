# Orawan Anuntakul — UX/UI Designer portfolio

Static site for GitHub Pages. No build step: every page is plain HTML.

## Pages
- `index.html` — Home
- `work/`, `about/`, `contact/`
- `projects/faac/`, `prepmate/`, `template/`, `no-fuss-meal-plan/`, `ivy-growth-group/`

Each page folder keeps its own `images/`.

## Contact form
The forms on Home and Contact send messages through [Web3Forms](https://web3forms.com) to orawannwcoders@gmail.com.
The access key is set in each of those two pages (`var WEB3FORMS_KEY = ...`). It is meant to be public.
If the key line is ever reset to the placeholder, the forms fall back to opening an email draft.

## Publishing
Repo **Settings › Pages** → Source: *Deploy from a branch*, Branch: `main`, folder `/ (root)`.
## Adding a new project from the template

### 1. Copy the template
- Copy `projects/template/` and rename the copy, e.g. `projects/new-project-name/`.
  Use lowercase letters and hyphens only: the folder name becomes part of the web address.
- Leave `projects/template/` unchanged so it can be reused.

### 2. Edit the new project page (`projects/new-project-name/index.html`)
- **Delete** `<meta name="robots" content="noindex">` near the top, so search engines can find the real project.
- Replace `Project Name` in two places: the `<title>` (line 6) and the `<h1>`.
- Replace the placeholder text: year and project type, description, Role, Duration, Tools,
  and each process step (Discovery, Define, Ideate, UI, Validate).
- Update the **View Final Prototype** button: replace `href="#"` with the real link,
  or delete the button if there is no link.
- Put the project's images in `projects/new-project-name/images/` and reference them as `images/your-image.webp`.

### 3. Make a card image
Create one preview image (`.webp`), e.g. `newproject-card.webp`, and copy it to:
- `images/project-cards/` (Home page)
- `work/images/project-cards/` (Work page)
- `images/project-cards/` inside every other project folder ("There's more to explore")

### 4. Add the project to the Home and Work pages
In `index.html` and `work/index.html`, copy an existing `<a class="work-item" ...>` block and change:
- `href`: `projects/new-project-name/index.html` on Home, `../projects/new-project-name/index.html` on Work
- `img src`: `images/project-cards/newproject-card.webp`
- `work-number`, `work-title`, `work-role` and `work-description`
- Cards alternate sides: add `work-item--reverse` to every other card so the layout keeps zig-zagging.

### 5. Add it to "There's more to explore"
In each other project page, add a card inside `<div class="card-grid">`:

```html
<a class="project-card" href="../new-project-name/index.html">
  <div class="card-mockup-area card-mockup-area--image">
    <img src="images/project-cards/newproject-card.webp" alt="New Project case-study preview">
  </div>
  <p class="card-title">New Project</p>
  <p class="card-role">UX/UI Case Study</p>
</a>
```

In the new project's own page, the grid should list the other projects but not itself.

### 6. Update this README
Add the new folder to the `projects/` list under **Pages**.

### 7. Check and publish
- Open `index.html` in a browser and click through every project card and "more to explore" link.
- Check the new page at a narrow (phone) width too.
- In GitHub Desktop: write a summary such as "Add New Project case study", **Commit to main**, then **Push origin**.

Source of truth for design rules: `~/nudev/UX-Portfolio` (`design-tokens.css`, `portfolio-brand-guidelines.md`).
