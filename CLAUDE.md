# LSS 2026 — SJRM Praise Ministry Website

## Project Overview
Static website for the St. James Renewal Movement (SJRM) Praise Ministry, hosted on GitHub Pages.
Repository: https://github.com/Arsiesh/lss_2026
Live: https://arsiesh.github.io/lss_2026/

## Site Structure
- `index.html` — LSS No. 38 hour-by-hour schedule (Day 1 & Day 2 with tab switching)
- `secret/index.html` — Praise Ministry website (Google Sheets-driven CMS)
- `LSS38_Day1_Schedule.html` — Original Day 1 schedule (legacy, not used)
- `LSS38_Day2_Schedule.html` — Original Day 2 schedule (legacy, not used)
- `sheet_data/` — CSV templates for Google Sheet tabs

## Tech Stack
- Pure vanilla HTML/CSS/JS — no build step, no framework
- Google Fonts: Playfair Display, DM Sans (schedule), Lora, Source Sans 3 (praise site)
- Google Sheets as CMS for the Praise Website (secret/index.html)

## Google Sheets Integration (secret/index.html)
- Published Sheet ID: `1ultfMCtYeMZzZzZv6LDrEnjJdJ4lFa3bfF96GRotvYI`
- Published CSV base URL in CONFIG at top of secret/index.html
- Tabs & GIDs:
  - Resources (gid=0) — music links (Spotify, YouTube, Google Drive)
  - Lyrics (gid=1185586539) — chord/lyrics book links
  - Calendar (gid=1348165568) — practice dates & events
  - MainEvent (gid=TBD) — banner title, date, hidden schedule link
- Falls back to hardcoded data if sheet fetch fails
- URLs in the sheet need `https://` prefix or the fixUrl() function adds it

## Schedule Page (index.html)
- CSS custom properties for day theming: Day 1 = blue, Day 2 = gold
- Body class toggles between default (Day 1) and `day2` (Day 2)
- Sticky frosted glass tab bar, day banner, staggered card animations
- Card types: default, highlight, praise, food, mass, baptism, commission, closing

## Design Conventions
- Schedule: dark "Sacred Editorial" aesthetic — Playfair Display headings, DM Sans body
- Praise site: warm church community aesthetic — cream/ivory bg, burgundy + gold accents, Lora headings, Source Sans 3 body
- Mobile-first, max-width containers
- SVG cross separators and dove decorations on praise site

## Deployment
- Push to `main` branch → GitHub Pages auto-deploys
- Custom domain not configured (using arsiesh.github.io/lss_2026)
- Future: consider Netlify for private repo + password protection