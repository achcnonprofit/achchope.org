# ACHC — Website

Static website for ACHC (Alexander Chung Hope & Connection), an AI-powered suicide prevention organization for young adults.

## Structure

```
achc/
├── index.html          Main landing page
├── about.html          About / mission / origin
├── tools.html          Deep dive on each product
├── get-involved.html   Volunteer, chapter, share, donate
├── css/
│   └── styles.css      All styles
├── js/
│   └── main.js         Scroll reveals, count-up, particles, nav
└── assets/
    ├── alex-1.png
    └── alex-2.png
```

## Deploy

This is a pure static site — no build step, no backend.

**GitHub Pages**: push to a repo and enable Pages on the `main` branch root.
**Netlify**: drag and drop the `achc/` folder into a new site, or connect the repo.
**Vercel**: `vercel deploy` from the project root.

## Stack

- Vanilla HTML, CSS, JavaScript
- Google Fonts: Syne (display), DM Sans (body)
- Intersection Observer for scroll reveals and count-up
- Canvas API for hero particle background
- GoFundMe embed widget (loaded via official embed.js)

## Known placeholders

These need to be wired up before launch:

- **Letters of Hope form** (`#letters-form`): currently shows a confirmation on submit but does not send anywhere. Connect to Formspree, Netlify Forms, a Cloud Function, or your own backend. See comment in `index.html` and the submit handler in `js/main.js`.
- **Impact stats** (`data-countup` on `.impact-stat .num`): currently animate to 0. Update the `data-countup` attribute values once real numbers exist.
- **Volunteer/chapter buttons**: link to `mailto:` placeholders. Replace with real application forms or pages once available.
- **Social share URLs**: include `url=` query string but pass an empty value — replace with the live site URL after deploy.

## Accessibility & motion

- All scroll-triggered animations are disabled for users with `prefers-reduced-motion`.
- Hero particle canvas is also disabled for reduced motion.
- All interactive controls have visible focus states (browser defaults — extend if needed).
- Form fields have explicit labels.

## Tone reminder

- Never use clinical crisis language in user-facing copy outside the 988 reference.
- Always pair any mention of crisis with a resource.
- Use "died by suicide," never "committed suicide."
- No em dashes in copy.
