# Presha Trends — Shopify Theme

## Project Overview
Presha Trends is a luxury streetwear and sneaker resell brand based in Dubai.
We are building their full Shopify storefront on the Horizon theme.
Everything built must be fully functional at the end.
Screenshots in /design-refs/ are base points and starting references — 
not fixed finals. Adjustments will be instructed during development.
Assume nothing has been built yet. Cross-reference existing theme files 
to check what's already in place before writing new code.

## Competitor Reference
- Reference site: https://www.madkicks.com
- We are NOT copying this site — it is a baseline reference only
- Presha Trends must be significantly superior in design, interaction,
  performance, and overall experience
- Use it to understand the category, not to derive design decisions

## Brand Identity
- Name: Presha Trends
- Niche: Luxury streetwear resell, rare sneakers, collectibles
- Location: Dubai
- Tone: High-end, editorial, exclusive, trustworthy
- Feel: Very interactive, modern, premium — luxury with energy

## Design System
- Primary color: Burgundy #6B1A2A
- Background: Off-white
- Fonts: Cormorant Garamond (headings/editorial), Jost (body/UI)
- Aesthetic: Luxury editorial — NOT generic streetwear
- Designer assets will be provided and integrated as they are confirmed

## Tech Stack
- Platform: Shopify
- Theme: Horizon (modified copy)
- Workflow: Shopify CLI + Git + Claude Code
- Animations: GSAP (required throughout — makes the site feel modern and alive)
- 3D Intro: Planned — details TBD, likely Three.js or a video-based intro sequence

## Development Principles
- Mobile responsiveness is the #1 priority on every section built
- Write clean, well-commented, maintainable code always
- Make surgical targeted edits — never rewrite full files unnecessarily
- Consult before making changes when intent is ambiguous
- Every section must be functional end-to-end, not just visual
- GSAP animations should enhance UX without hurting performance
- Code must be modular — reusable snippets and partials where possible
- No bloated or redundant CSS — keep styles scoped and organized

## Animations & Interactions (Global Rules)
- GSAP is the animation library of choice — load via CDN in theme.liquid
- Use ScrollTrigger for scroll-based animations
- Entrance animations on all major sections (fade, slide, stagger)
- Hover states should feel premium — subtle, smooth, intentional
- Page transitions should feel editorial and fluid
- Interactive elements must have clear tactile feedback
- Never sacrifice performance for animation — use will-change and GPU layers wisely

## 3D Intro
- Status: Planned, not yet scoped
- Likely approach: Three.js or a video-based intro sequence
- Will be briefed in detail when ready to build

## Mobile Responsiveness Rules
- Mobile-first CSS approach on all new sections
- Breakpoints: 480px / 749px / 1024px / 1280px
- Touch interactions must feel native and smooth
- No horizontal overflow on any viewport
- Tap targets minimum 44px
- Test every section at 375px (iPhone SE) as minimum baseline

## Navigation
- Links: Featured, Sneakers, Streetwear, Accessories, Collectibles
- Icons: Search, Account, Wishlist (static — no functionality yet), Cart
- Wishlist icon is a placeholder — functionality to be added later

## Pages & Sections Tracker
### Homepage
- [ ] Announcement Bar
- [ ] Navigation / Header
- [ ] Hero Section
- [ ] Category Pills
- [ ] (further sections TBD as designs come in)

### Other Pages
- [ ] Collection / Category Page
- [ ] Product Detail Page
- [ ] About Page
- [ ] Cart Page
- [ ] Account Page
- [ ] (more TBD)

## Product & Shopify Setup Notes
- Products are mostly one-of-one (resell) — inventory logic must reflect this
- Collections not fully set up yet — use placeholder handles where needed
- Metafields may be needed for custom product data — scope per section
- Wishlist: no app integrated yet — static icon only for now
- Product setup will be done in parallel as frontend is built

## Design References
All design screenshots live in /design-refs/
All designer assets live in /design-assets/
Both folders are gitignored — not tracked in version control
- hero.png — Homepage hero + announcement bar + nav + category pills
- More will be added as designs are confirmed

## Code Management
- Every completed section gets a git commit with a clear message
- Commit format: "feat: [section name] — [brief description]"
- Never push broken code to main
- Keep a clean commit history — one logical change per commit
- Any experimental work goes on a separate branch
```

---

Save that as `CLAUDE.md` in the root of your theme folder. Then make sure your `.gitignore` has:
```
CLAUDE.md
/designrefs/
/designassets/