# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto-based portfolio website that showcases product management projects. It automatically deploys to GitHub Pages via GitHub Actions when changes are pushed to main.

## Commands

### Local Development
```bash
quarto preview              # Start dev server with hot-reload
quarto render               # Build site to _site/ directory
```

### Deployment
Push to `main` branch triggers automatic deployment via `.github/workflows/publish.yml`. No manual deployment commands needed.

## Architecture

**Static Site Generator:** Quarto renders `.qmd` (Quarto Markdown) files to HTML.

**Key Configuration:**
- `_quarto.yml` - Site config, navbar, theme settings
- `styles.css` - Custom CSS overrides
- `_site/` - Build output (gitignored, regenerated on build)

**Content Structure:**
- `index.qmd` - Homepage with profile and featured projects
- `about.qmd` - Bio and background page
- `projects/*.qmd` - Individual project showcase pages

**Assets:**
- `images/` - Profile photos, project screenshots, favicon
- Font Awesome loaded via CDN for icons

## Adding Projects

1. Create `projects/project-N.qmd` with YAML front matter (title, date, categories)
2. Uncomment/add entry in `_quarto.yml` navbar menu under Projects
3. Use `<iframe>` embeds for live app demos, Markdown tables for specs

## Theme

Uses Cosmo theme. Change in `_quarto.yml` under `format.html.theme`. Available: cosmo, flatly, litera, minty, pulse, sandstone, simplex, sketchy, slate, solar, spacelab, superhero, united, yeti.
