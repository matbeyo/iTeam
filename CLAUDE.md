# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for iTeam-sh, an IT services company based in Raanana, Israel. Built with vanilla HTML, CSS, and JavaScript — no frameworks, no build tools, no package manager.

## Running Locally

Serve files with any static HTTP server:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000`. No build step required.

## Architecture

- **`index.html`** — Main landing page with hero, services overview, about, partners, customers, and contact form
- **`services/`** — 6 standalone service detail pages (cloud-services, cyber-security, infrastructure-projects, it-consulting, it-management-support, it-optimization), each with its own inline styles and breadcrumb navigation
- **`styles.css`** — Shared stylesheet used by all pages (linked as `../styles.css` from service pages)
- **`script.js`** — Shared client-side logic: mobile menu, scroll effects, contact form validation/submission, intersection observer animations, stats counter animation, and canvas particle network effect
- **`images/`** — Logo, customer logos (`customers/`), and partner logos (`partners/`)
- **`sitemap.xml`** / **`robots.txt`** — SEO files targeting `https://www.iteam-sh.co.il/`

## Key Conventions

- **Hebrew RTL**: The entire site is right-to-left (`dir="rtl"`, `lang="he"`). Uses the Heebo font from Google Fonts.
- **CSS custom properties**: Theming uses variables like `--primary-color` (#001F3F navy), `--accent-color` (#0D9488 teal), defined in `:root`.
- **Contact form**: Submits via fetch to Formspree (`https://formspree.io/f/mgolndpk`). Validates Israeli phone format and email client-side before submission.
- **SEO structured data**: JSON-LD blocks for LocalBusiness, Service, BreadcrumbList, and AggregateRating schemas are embedded in each page.
- **Animations**: Intersection Observer triggers fade-in effects on cards. The hero section has a Canvas 2D particle network with mouse interaction.
- **No dependencies**: Everything is vanilla — no npm packages, no bundler, no transpiler. External resources are Google Fonts only.
