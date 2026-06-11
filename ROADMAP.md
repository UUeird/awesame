# ROADMAP

A living list of improvements and new features for [awesa.me](https://awesa.me).
Items are grouped by theme. Move finished items to the **Done** section at the bottom.

---

## Improve: Design & layout

- [ ] Make footer icons larger / more touch-friendly on mobile.
- [ ] Consider a dark/light theme toggle or a more intentional color palette.

---

## Feature: Content

- [ ] **Bio section** — a short paragraph about awesame: who, what, genre, etc.
- [ ] **Links / releases section** — Spotify, Apple Music, Bandcamp, or other streaming links.
- [ ] **Shows / tour dates** — even a simple static list of upcoming gigs.
- [ ] **Press / EPK page** — populate with bio, downloadable one-sheet, high-res photos, quote cards.
- [ ] **Contact form** — static form via Formspree or similar (no server needed).

---

## Feature: Social & platform updates

- [ ] Add Spotify or Apple Music follow link.

---

## Done

- [x] Set up GitHub Pages with custom domain `awesa.me` (CNAME).
- [x] Jekyll build workflow deployed via GitHub Actions (Jekyll not yet used — just passes static files through).
- [x] Basic single-page layout with logo, SoundCloud embed, and social footer.
- [x] Fix HTTP jQuery — switched to `https://code.jquery.com/jquery-3.7.1.min.js`.
- [x] Fix HTML structure — moved `<link>` and `<script>` into `<head>`, fixed tag order.
- [x] Add `<meta charset="UTF-8">` and viewport tag.
- [x] Replace SoundCloud embed with footer profile link (soundcloud.com/awesame).
- [x] Update Twitter to X branding — new SVG icon, link updated to x.com/awesame.
- [x] Remove dead Facebook and YouTube footer links.
- [x] Add Instagram link/icon (instagram.com/awesa.me).
- [x] Replace email.png with consistent SVG icon.
- [x] Space footer icons with padding.
- [x] Add hover states to footer icons.
- [x] Adopt Jekyll — added `_config.yml`, `_layouts/default.html` with shared header/nav/footer; migrated index.html.
- [x] Create My Story page scaffold (timeline layout).
- [x] Create Press Kit page scaffold.
- [x] Add `<meta name="description">` tag (per-page via front matter, fallback to site description).
- [x] Add Open Graph tags (`og:title`, `og:description`, `og:image`, `og:url`).
- [x] Add sitemap via `jekyll-sitemap` plugin (auto-generates `/sitemap.xml`).
- [x] Add `robots.txt` pointing crawlers to sitemap.
- [x] Remove `awesame.js` (empty) and drop jQuery (nothing used it).
- [x] Add SVG favicon using brand color #f5a800.
- [x] Compress `awesame-logo.png` with optipng — 40KB → 28KB (29% smaller). Remove unused `awesame.png`.
