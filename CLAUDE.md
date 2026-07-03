# CLAUDE.md

## Project overview

This is the source for [awesa.me](https://awesa.me) — a personal music/artist site for Sam Lawrence, hosted on GitHub Pages. The custom domain is configured via `CNAME`.

## Deployment

- **Branch:** `main` is the default and production branch. All pushes trigger the Astro build-and-deploy workflow at [.github/workflows/astro-gh-pages.yml](.github/workflows/astro-gh-pages.yml).
- **Hosting:** GitHub Pages, serving the static output of an Astro build (`npm run build` → `dist/`). CI builds with Node 22 (see `.nvmrc` for the local pin).
- **Constraint:** No server-side code, no server-side rendering, no environment variables at runtime. Everything ships as plain static HTML/CSS/JS output by the Astro build.

## Local development

```
npm install
npm run dev       # local dev server
npm run build      # production build to dist/
npm run preview    # preview the production build
```

Requires Node >=22.12 (`.nvmrc` pins this — run `nvm use` if using nvm).

## Current structure

```
src/pages/          — one .astro file per route (index, my-story, press)
src/layouts/Default.astro — shared layout: head/meta/OG tags, header, nav, footer
public/              — static assets served as-is (style.css, favicon.svg, awesame-logo.png, images/icons/, robots.txt)
astro.config.mjs      — site URL + @astrojs/sitemap integration
CNAME                — custom domain: awesa.me
```

## Constraints to keep in mind

- GitHub Pages serves static files only. No server-side rendering, no environment variables at runtime.
- Sitemap is generated automatically by `@astrojs/sitemap` at build time.
- No UI framework (React/Vue/etc.) is installed — pages are plain `.astro` files with no client-side interactivity today. Add an integration only if a feature actually needs it.
