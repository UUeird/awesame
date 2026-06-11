# CLAUDE.md

## Project overview

This is the source for [awesa.me](https://awesa.me) — a personal music/artist site for Sam Lawrence, hosted on GitHub Pages. The custom domain is configured via `CNAME`.

## Deployment

- **Branch:** `gh-pages` is the production branch. All pushes trigger the Jekyll build-and-deploy workflow at [.github/workflows/jekyll-gh-pages.yml](.github/workflows/jekyll-gh-pages.yml).
- **Hosting:** GitHub Pages with Jekyll. No build step is required locally — GitHub Pages renders static HTML/CSS/JS directly.
- **Constraint:** No server-side code, no Node.js build pipeline, no npm packages. Everything must work as plain static files (HTML, CSS, vanilla JS, or CDN-loaded libraries).

## Current structure

```
index.html      — single-page site
style.css       — global styles
awesame.js      — empty jQuery ready handler (jQuery loaded from CDN)
awesame.png     — logo image
images/icons/   — social media icons (facebook, twitter, youtube, email)
awesame logos/  — brand assets (not served, design reference only)
CNAME           — custom domain: awesa.me
```

## Known issues / tech debt

- jQuery loaded over HTTP (not HTTPS) from code.jquery.com — will cause mixed-content warnings on HTTPS pages.
- `<LINK>` and `<script>` tags appear before `<html>` / `<head>` — malformed HTML structure.
- No `<meta charset>`, viewport tag, or Open Graph tags.
- Twitter link uses old `twitter.com` handle; X rebranded.
- `awesame.js` is essentially empty.

## Constraints to keep in mind

- GitHub Pages serves static files only. No server-side rendering, no environment variables at runtime.
- Jekyll is available but not currently used (no `_config.yml`, no Liquid templates). Adding Jekyll features is fine but not required.
- All external scripts/fonts must be loaded from CDN or bundled in the repo.
