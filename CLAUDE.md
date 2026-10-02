# Sudoku Odyssey – Website Project

## Overview
Promo website for the iOS app **Sudoku Odyssey** (no ads, 40+ board styles, daily challenge).
Hosted on **GitHub Pages** at **sudokuodyssey.com**.
Repo: `ezralatina/sudoku-odyssey-website` (GitHub Pages, branch: main).

## App Details
- App Store URL: https://apps.apple.com/us/app/sudoku-odyssey-no-ads/id6791718361
- App icon CDN: https://is1-ssl.mzstatic.com/image/thumb/Purple221/v4/2c/31/d9/2c31d98f-3fe1-a840-18ef-c5694d6a9811/AppIcon-0-0-1x_U007epad-0-1-0-GLES2_U002c0-85-220.png/540x540bb.jpg
- Apple badge URL: https://toolbox.marketingtools.apple.com/api/v2/badges/download-on-the-app-store/black/en-us?releaseDate=1789344000
- Developer: Ezra Latina — sudokuodyssey@gmail.com
- Tech: SwiftUI, Firebase Analytics, StoreKit 2 IAP ($4.99 "Unlock All Boards")

## Site Pages
- `index.html` — main landing page
- `support.html` — FAQ / support page
- `privacy.html` — privacy policy
- `logo.png` — Sudoku Odyssey wordmark (SUDOKU in blue, ODYSSEY in black tiles)
- `screenshot-*.png` — app screenshots used in the styles section (8 total, more to come)

## Design System
- Primary blue: `#007AFF`
- Dark blue: `#0055B3`
- Background: `#F2F2F7`
- Card: `#FFFFFF`
- Border radius: `16px`
- Font: `'SF Pro Rounded', ui-rounded, 'Nunito', -apple-system, BlinkMacSystemFont, system-ui, sans-serif`
- Nunito loaded from Google Fonts (rounded fallback for non-Apple devices)

## index.html Section Order
1. Nav (links: Styles → Features → Daily)
2. Hero (app icon embed + logo + tagline + App Store badge)
3. Board Styles (`#styles`) — 2 rows of screenshots: Classic and Emoji
4. Features (`#features`) — 6 feature cards
5. Daily Challenge (`#daily`) — playable in-browser sudoku
6. CTA — App Store download
7. Footer

## Screenshot Files
Classic row: `screenshot-space.png`, `screenshot-chalkboard.png`, `screenshot-notebook.png`, `screenshot-retro.png`
Emoji row: `screenshot-jungle.png`, `screenshot-ocean.png`, `screenshot-fantasy.png`, `screenshot-cinema.png`
Plan: expand to 6 per row when Ezra adds more screenshots.

## Daily Challenge JS
Uses a seeded LCG matching the iOS app: `seed = YYYYMMDD as BigInt`, `state = state * 6364136223846793005n + 1442695040888963407n`

## Push Workflow
**Claude cannot push to GitHub directly.** Ezra handles all git pushes manually.
After making changes to `index.html`, send the file to the user and give them this Terminal command:
```
cp ~/Downloads/index.html ~/Documents/GitHub/sudoku-odyssey-website/index.html && cd ~/Documents/GitHub/sudoku-odyssey-website && git add index.html && git commit -m "<message>" && git push
```
For new image files, also copy them: `cp ~/Downloads/screenshot-*.png ~/Documents/GitHub/sudoku-odyssey-website/`

GitHub credentials: Ezra uses a Personal Access Token (classic, repo scope) pasted as password when Terminal prompts.

## Apple CDN Note
`toolbox.marketingtools.apple.com` badge URLs have referrer restrictions — they show as placeholders in local preview but work correctly on the live sudokuodyssey.com domain. Do not replace with hand-crafted SVGs.
