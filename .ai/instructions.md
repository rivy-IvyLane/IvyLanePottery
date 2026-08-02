# Ivy Lane Pottery — AI Instructions

## Project

Static single-page portfolio website for **Donna Ivy**, ceramic artist and artist-in-residence at Glaze Ceramic Studio, McKinney, Texas.

- **Domain:** IvyLanePottery.com (GitHub Pages with custom domain)
- **Artist contact:** dkgivy@gmail.com
- **Reference site:** <https://hollygreyceramics.com>

## Repository Layout

```
index.html          Single-page site
style.css           All styles (no build step, no preprocessor)
CNAME               Custom domain declaration for GitHub Pages
.nojekyll           Disables Jekyll so GitHub serves raw HTML
DNS-SETUP.md        Step-by-step domain configuration guide
assets/
  logo/             Logo PNG + business card PDF
  people/           Artist headshots (JPG)
  pottery/          Gallery images (PNG)
.ai/
  instructions.md   This file
```

## Site Sections

| Section | Notes |
|---------|-------|
| Hero | Full-screen, `IMG_6504 - Edited.png` as background with dark overlay |
| Gallery | 29 pottery PNGs; 12 shown initially, "Show More" adds 12 at a time; click opens lightbox |
| About | Two-column: headshot (2026-05-29) left, three text blocks right |
| Contact | Centered email link (`dkgivy@gmail.com`) + studio credit |
| Footer | Auto-updating copyright year |

## Design System

| Token | Value |
|-------|-------|
| Background | `#f7f4ef` warm cream |
| Text | `#2d2926` deep charcoal |
| Accent | `#8a7560` warm brown |
| Border | `#dcd5c8` |
| Dark (footer) | `#1e1c1a` |
| Heading font | Cormorant Garamond (Google Fonts), weights 300/400/500 |
| Body font | Lato (Google Fonts), weights 300/400/700 |

Breakpoints: `max-width: 900px` (about layout collapses) and `max-width: 640px` (mobile nav, 2-col gallery).

## Assets

**Logo:** `assets/logo/Ivy Lane Pottery Logo - ChatGPT Image Nov 3, 2025, 10_48_08 PM.png`
— White background (not transparent). Used in nav (44px tall, beside site name) and hero (inside a cream card `hero-logo-wrap` to frame it against the dark background). Also set as favicon.

**Headshot:** `assets/people/Donna Ivy - headshot (2026-05-29) - PXL_20260529_194312892.RAW-01.jpg`
— The 2026 photo is used on the site; the 2017 photo is in the folder but not referenced.

**Pottery images:** 29 PNG files in `assets/pottery/`. Filenames contain spaces and some contain parentheses — URL-encode with `%20`, `%28`, `%29` when referencing in HTML/CSS. The JS gallery function `encodeImageName()` handles this at runtime.

## Conventions

- **No build tools.** Plain HTML + CSS + vanilla JS only.
- **No external JS libraries.** Lightbox, gallery, and all interactivity are hand-written.
- **No comments** in code unless the reason is non-obvious.
- Prefer editing existing files over creating new ones.
- Image paths in CSS use literal `%20` encoding (e.g., the hero background in `style.css`).
- Image paths in JS are encoded at runtime via `encodeImageName()`.

## Content

### About My Work
"My work celebrates beauty through ceramics, exploring form, texture, and surface design through hand-built and wheel-thrown pieces. I use carving, layering and expressive glazes to create depth and movement, allowing each vessel or sculptural form to carry its own character. My most recent work includes Nerikomi, combining multiple different clays to create pattern through changing color. Whether functional or purely sculptural, my ceramics are designed to invite touch, connection, and a sense of warmth and artistry into everyday spaces."

### Artist Statement
"As a lifelong Texan and passionate artist, I have explored a variety of creative pursuits throughout my life. Four years ago, I discovered ceramics and quickly found my home in the studio. My work emphasizes form and surface design with a particular focus on layered glazes and color change. My recent interest in Nerikomi, which uses colored clays combined to create patterns in the vessel rather than on the surface, continues this focus."

### Bio
"Donna Ivy holds a B.S. from the University of Texas Southwestern. She has studied with multiple professional ceramic artists in the DFW area and at the Anderson Ranch Arts Center in Snowmass, Colorado. She maintains her studio and is an artist-in-residence at Glaze Ceramic Studio in McKinney, Texas."
