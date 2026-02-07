# ivikramsahu.github.io

Personal blog built with **Astro** + **Tailwind CSS**, deployed to **GitHub Pages** via **GitHub Actions**.

## Why this blog exists
This site is designed to be fast, readable, and fun:

- **Writing-first**
  Posts are authored as content entries and rendered as static pages for great performance.
- **A little delight**
  The sidebar includes a **Quotes** widget and a small **Snakes & Ladders** game to keep the experience light and interactive while still staying out of the way of reading.

## Features
- **Astro static rendering** for speed and SEO.
- **Tailwind CSS** for consistent styling.
- **Sticky header** with a **theme toggle** (light/dark).
- **Blog listing + pagination** (`/page/[page]/`).
- **Post pages** (`/blog/[...slug]/`) with clean typography.
- **Quotes widget**
  Rotates quotes and refreshes periodically.
- **Snakes & Ladders**
  A small two-player (You vs Computer) mini-game with state persistence, move logs, and win/lose effects.

## Why the Quotes widget?
The quotes panel is meant to add a small “focus boost” while browsing posts:

- A quick line of motivation or perspective
- Refreshes automatically (and also changes on reload)
- Lives in the sidebar so it doesn’t distract from reading

Implementation lives in `src/components/QuotesWidget.astro`.

## Why the Snakes & Ladders game?
The game is intentionally simple and optional:

- Adds a playful element to the homepage/listing pages
- Encourages exploration (without affecting core reading UX)
- Runs fully client-side and doesn’t require any backend

Implementation lives in `src/components/SnakesAndLadders.astro`.

## Tech stack
- **Astro** (site framework)
- **Tailwind CSS** (styling)
- **GitHub Pages** + **GitHub Actions** (deployment)

## Project structure (high level)
- `src/layouts/BaseLayout.astro`
  Shared layout, header/nav, theme toggle.
- `src/pages/index.astro`
  Homepage blog list + sidebar.
- `src/pages/page/[page].astro`
  Paginated blog list pages.
- `src/pages/blog/[...slug].astro`
  Individual blog post pages.
- `src/pages/about.astro`
  About page.
- `src/components/QuotesWidget.astro`
  Quotes sidebar widget.
- `src/components/SnakesAndLadders.astro`
  Snakes & Ladders game.
- `src/styles/global.css`
  Global styles + typography tweaks.
- `.github/workflows/deploy.yml`
  GitHub Actions workflow that builds and deploys the static output.

## Running locally
Prerequisites:
- Node.js (LTS recommended)
- npm

Commands:

```bash
npm install
npm run dev
```

Astro will print the local dev URL (typically `http://localhost:4321`).

## Build
```bash
npm run build
npm run preview
```

## Deployment (GitHub Pages)
This repo is intended to be deployed as a **user site**:

- Repo name: `ivikramsahu.github.io`
- URL: `https://ivikramsahu.github.io/`

Notes:
- Deployment is done via **GitHub Actions** (see `.github/workflows/deploy.yml`).
- In GitHub settings, ensure:
  - **Settings → Pages → Source = GitHub Actions**
  - Not “Deploy from a branch” (that can trigger Jekyll on source files).

## Content notes
If you imported content from another platform, helper scripts may live under `scripts/` (for example `scripts/import-hashnode.mjs`). These scripts are optional and not required to run the site.
