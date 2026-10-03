# Satti Studio — Portfolio

Single-page freelance web developer portfolio: services, approach, a filterable grid of practice builds, and a working quote builder.

**Live:** https://satti-web-studio.vercel.app

Source code is in this repo — hand-written, no build step. Open `index.html` in a browser or serve the folder locally (see below).

## About

This is my personal portfolio site — the one that represents the freelance web development work. It is a single self-contained `index.html` (HTML, CSS and JavaScript all inline) with no dependencies, no bundler and no build step, so it can be dropped onto any static host. Sections cover what I do, how I work, selected work, the stack I build with, and a quote builder that prices a project live and sends the request over WhatsApp.

## Tech stack

| | |
|---|---|
| Markup | HTML5, semantic sections, `lang="en"` |
| Styling | Hand-written CSS in an inline `<style>` block, CSS custom properties for the palette |
| Script | Vanilla ES6+ in one inline `<script>` — no libraries, no bundler |
| Fonts | Google Fonts: Space Grotesk, Inter Tight, Playfair Display, Space Mono |
| Build | None. No `package.json`, no dependencies |
| Hosting | Vercel, static hosting |

## Features

Everything below is implemented in `index.html`.

- **Typewriter hero line** — types `> PAKISTAN-BASED FREELANCE WEB DEVELOPER` character by character; renders instantly when `prefers-reduced-motion` is set.
- **Filterable work grid** — 10 project cards with filter chips (`All`, `Business`, `E-commerce`, `Landing`) driven by `data-cat`, state exposed via `aria-pressed`.
- **Quote builder modal** — pick a project type (landing page / business website / e-commerce store), add extra pages at Rs. 3,500 each and priced add-ons (WhatsApp booking, SEO + analytics, bilingual content, priority delivery); the total recalculates on every change and is formatted as `Rs. 12,000`.
- **Quote → WhatsApp** — the modal builds a line-item summary and opens a pre-filled WhatsApp message.
- **Scroll progress bar** and **reveal-on-scroll** animations via `IntersectionObserver` (one-shot, elements unobserve after firing).
- **Mobile navigation** — closes on link click, on `Escape`, and when the viewport widens past 880px.
- **Accessibility basics** — skip-to-content link, `aria-modal` / `aria-labelledby` on the dialog, focus moved to the close button on open, `Escape` and backdrop click both close, body scroll locked while open, `aria-live="polite"` on the extra-page counter, `aria-pressed` on the filter chips.
- **Responsive** — breakpoints at 1024px, 880px and 560px.
- **Motion safety** — all animation is disabled under `prefers-reduced-motion: reduce`.

## Project structure

```
.
├── index.html          # the entire site — markup, styles and script
├── me.jpg              # portrait
├── project-*.jpg       # one card image per project (10)
├── screenshot-hero.png
├── screenshot-full.png
├── .gitignore          # ignores .vercel
└── .vercel/            # Vercel project link (projectName: satti-web-studio)
```

## Local preview

No install step. Any static server works:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Opening `index.html` directly from the filesystem also works.

## Selected work

Each build below is a practice/demo build, not a delivered client project.

| Project | What it is | Live |
|---|---|---|
| Multi-Site Demo | Showcase page for sample businesses | https://client-showcase-psi.vercel.app |
| Ember & Oak | Wood-fire restaurant, 3 pages with a live menu | https://ember-oak-gold-gamma.vercel.app |
| Velour Beauty | Salon + academy, booking | https://velour-salon-kohl.vercel.app |
| TimeCart | Watch e-commerce store (React) | https://timecart-hh5m.vercel.app |
| Corals by Tabassum | Jewellery e-commerce store | https://corals-by-tabassum.vercel.app |
| Skyline Realty | Real estate, buy / sell / rent | https://skyline-realty-nu.vercel.app |
| CareWell Clinic | Clinic site with booking | https://carewell-clinic-one.vercel.app |
| BrightMinds Academy | Education site with online admission | https://brightminds-academy-green.vercel.app |
| IronForge Fitness | 4-page gym business site | https://gym-ironforge-lyart.vercel.app |
| IronForge Landing | Single-page campaign site with lead capture | https://gym-landing-ironforge.vercel.app |

## Notes

- Prices in the quote builder are my own rates, kept in one `P` / `EXTRA` object at the top of the script so they are easy to change.
- All card images use `loading="lazy"`.
- Contact details on the page are real; the businesses in the work grid are demo content.
