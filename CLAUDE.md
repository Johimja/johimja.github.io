# CLAUDE.md

Guide for AI assistants working on this codebase.

## Project Overview

Static single-page website for **Johimja**, a Norwegian Alternative Metal / Progressive Rock project by Atle Stray. Hosted on GitHub Pages at [johimja.com](https://johimja.com).

## Architecture

Pure vanilla HTML/CSS/JS with **no build system, no package manager, no frameworks**. Files are served directly by GitHub Pages.

### File Structure

```
index.html   - Single-page HTML (all sections: home, about, music, store, contact)
styles.css   - All styles (responsive, mobile-first, animations)
script.js    - Vanilla JS (nav toggle, smooth scroll, Intersection Observer, store buttons)
CNAME        - Custom domain config (johimja.com)
README.md    - Brief project description
```

### Sections (anchor IDs)

`#home` (hero) | `#about` | `#music` | `#store` | `#contact` | footer

## Key Conventions

### CSS
- **Naming**: kebab-case class names (`.nav-links`, `.store-grid`, `.cta-button`, `.hero-content`)
- **Layout**: CSS Grid for content grids (`auto-fit, minmax`), Flexbox for nav/links
- **Fonts**: `Orbitron` (headings/logo), `Crimson Text` (body) via Google Fonts CDN
- **Colors**: Dark theme — background `#0a0a0a`, text `#e0e0e0`, accent `#ff0040`
- **Responsive**: Single breakpoint at `768px` for mobile; hamburger menu replaces nav-links
- **Animations**: `fadeInUp` keyframe with Intersection Observer triggers

### JavaScript
- Vanilla ES6+ (no transpilation needed)
- `querySelector`/`querySelectorAll` for DOM access
- Intersection Observer API for scroll-triggered animations
- Store buttons are placeholder (`alert('Coming soon!')`)

### HTML
- Semantic sections with ID anchors for single-page navigation
- External embeds: Spotify player iframe, YouTube playlist iframe
- Streaming links: Apple Music, YouTube, Spotify, Amazon Music

## Development Workflow

1. **No build step** — edit files directly and push
2. **Deployment** — automatic via GitHub Pages on push to `main`
3. **Local preview** — open `index.html` in a browser, or use any static file server (`python3 -m http.server`, etc.)
4. **No tests** — no test framework or test files exist
5. **No CI/CD** — no GitHub Actions workflows

## External Dependencies (CDN only)

- Google Fonts: `Crimson Text`, `Orbitron`
- Spotify embed (iframe)
- YouTube embed (iframe)
- Unsplash background image URL in CSS hero section

## Things to Watch Out For

- The `.youtube-container` responsive styles and `.music-embeds iframe` styles are inside the `@media (max-width: 768px)` block in `styles.css` — they only apply on mobile
- Store buttons have no real purchase flow yet (placeholder alerts)
- Some social links in the contact section use `href="#"` (placeholders)
- The Amazon Music link contains a placeholder artist ID (`B0YourAmazonID`)
- Footer copyright year is hardcoded to 2025
