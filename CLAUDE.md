# Claude Code Instructions

## Overview

Marketing website for Chitti (chitti.me) — an AI beauty companion app.
Astro static site with Tailwind CSS v4, deployed to Cloudflare Pages.

## Stack

- **Framework:** Astro 5.x (static output)
- **Styling:** Tailwind CSS v4
- **Fonts:** Bricolage Grotesque (display), DM Sans (body) via Google Fonts
- **Deployment:** Cloudflare Pages (auto-deploy on push to `main`)

## Structure

```
src/
  components/    # Header, Footer, Hero, Features, HowItWorks, Testimonials, DownloadCTA, BlogCard
  content/       # Blog posts (markdown with frontmatter)
  layouts/       # BaseLayout, PageLayout, BlogPost
  pages/         # index, about, blog, privacy, support, terms, 404
  styles/        # global.css (theme, animations)
public/          # favicon.png, images/, robots.txt
```

## Build & Dev

| Command | Description |
|---------|-------------|
| `npm run dev` | Local dev server |
| `npm run build` | Production build → `dist/` |
| `npm run preview` | Preview built site |

## Design

- Dark theme hero/CTA sections, light theme content sections
- Primary color: `#4AB89A` (mint/teal)
- Accent palette: iris, rose, gold, sky (prismatic gradients)
- Animations: fade-up, float, shimmer, pulse-glow

## Pages

| Path | Purpose |
|------|---------|
| `/` | Landing page |
| `/about` | Mission, values, cultural context |
| `/blog` | Blog listing + individual posts |
| `/privacy` | Privacy policy |
| `/support` | FAQ + contact info (App Store support URL) |
| `/terms` | Terms & conditions |

## Verification Workflow

After every meaningful UI change, visually verify using `agent-browser`:
1. Start dev server (`npm run dev`) if not running
2. Open page with `agent-browser open http://localhost:4321`
3. Screenshot and inspect the changed section
4. Scroll/navigate to confirm surrounding sections are unaffected
5. Only then report the change as complete

## Key Notes

- Site URL configured as `https://chitti.me` in `astro.config.mjs`
- Download buttons currently point to `#` (placeholder until app store listings are live)
- Blog uses Astro content collections (`src/content/blog/`)
- App icon source lives in the main app repo (`saheli-ai/saheli`); copy manually when updated
