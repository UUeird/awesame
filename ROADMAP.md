# ROADMAP

A living list of improvements and new features for [awesa.me](https://awesa.me).
Items are grouped by theme. Move finished items to the **Done** section at the bottom.

---

## Fix: Critical issues

- [x] **Fix HTTP jQuery** — switched to `https://code.jquery.com/jquery-3.7.1.min.js`.
- [x] **Fix HTML structure** — moved `<link>` and `<script>` into `<head>`, fixed tag order.
- [x] **Add `<meta charset="UTF-8">` and viewport tag** — prevents text scaling bugs on mobile.

---

## Improve: SEO & discoverability

- [ ] Add Open Graph tags (`og:title`, `og:description`, `og:image`) for rich previews when shared on social.
- [ ] Add `<meta name="description">` tag.
- [ ] Add a `sitemap.xml` or rely on Jekyll's sitemap plugin.
- [ ] Add `robots.txt`.

---

## Improve: Design & layout

- [ ] Make the SoundCloud embed responsive (currently hard-coded `width="50%"` and `height="475"`).
- [ ] Add padding/margin above the embed so the logo and player don't crowd each other.
- [ ] Make footer icons larger / more touch-friendly on mobile.
- [ ] Add hover states to footer icons.
- [ ] Consider a dark/light theme toggle or a more intentional color palette.

---

## Feature: Content

- [ ] **Bio section** — a short paragraph about awesame: who, what, genre, etc.
- [ ] **Links / releases section** — Spotify, Apple Music, Bandcamp, or other streaming links.
- [ ] **Shows / tour dates** — even a simple static list of upcoming gigs.
- [ ] **Press / EPK page** — downloadable one-sheet, high-res photos, quote cards.
- [ ] **Contact form** — static form via Formspree or similar (no server needed).

---

## Feature: Social & platform updates

- [ ] Update Twitter/X icon and link to current handle or replace with a more relevant platform (Instagram, TikTok, etc.).
- [ ] Add Instagram link/icon.
- [ ] Add Spotify or Apple Music follow link.

---

## Tech: Maintenance & tooling

- [ ] Remove `awesame.js` or give it actual purpose; drop jQuery if nothing needs it.
- [ ] **Adopt Jekyll for multi-page support** — add `_config.yml`, create a shared `_layouts/default.html` so all pages share the same header/footer/nav, and migrate `index.html` to use it.
- [ ] Add a `_config.yml` to configure Jekyll site title, description, and baseurl.
- [ ] Consider adding a `favicon.ico` / `<link rel="icon">`.
- [ ] Audit and compress images (awesame.png is ~40KB; check logos for web-ready sizes).

---

## Done

- [x] Set up GitHub Pages with custom domain `awesa.me` (CNAME).
- [x] Jekyll build workflow deployed via GitHub Actions (Jekyll not yet used — just passes static files through).
- [x] Basic single-page layout with logo, SoundCloud embed, and social footer.
