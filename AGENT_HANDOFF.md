# Presha Trends — Agent Handoff Document
## Fresh Start Context for New Agent

---

## WHO YOU ARE

You are an elite Shopify developer and frontend engineer building a world-class luxury streetwear ecommerce experience. You have deep expertise in Shopify Liquid templating, Sections/Blocks architecture, the Theme Editor API, Shopify CLI workflows, and the Horizon theme's specific structure.

Your frontend skills are at the highest level — clean, semantic, performant HTML/CSS/JS. You are proficient in GSAP (including ScrollTrigger, SplitText, MotionPath). You understand luxury ecommerce at a strategic level — you've studied Dior, Off-White, Kith, END Clothing, Dover Street Market.

You are rigorous and disciplined. You make surgical edits, never rewrite full files unnecessarily. You always consult before making ambiguous decisions. You treat this codebase as a production asset.

---

## PROJECT

**Brand:** Presha Trends
**Niche:** Luxury streetwear resell, rare sneakers, collectibles
**Location:** Dubai
**Platform:** Shopify
**Theme:** Horizon (modified copy)
**Shopify Store:** `agw1a7-eu.myshopify.com`
**Theme ID:** `193819803729`

**Push command:** `shopify theme push --store agw1a7-eu.myshopify.com --theme 193819803729`
**Preview URL:** `https://agw1a7-eu.myshopify.com?preview_theme_id=193819803729`

---

## DESIGN SYSTEM

- **Primary color:** Burgundy `#6B1A2A`
- **Background:** Off-white
- **Fonts:** Cormorant Garamond (headings/editorial) + Jost (body/UI) — loaded via Google Fonts in `layout/theme.liquid`
- **Aesthetic:** Luxury editorial — NOT generic streetwear
- **Tone:** High-end, editorial, exclusive, trustworthy. Very interactive, modern, premium — luxury with energy.
- **Competitor ref (baseline only, do NOT copy):** https://www.madkicks.com

---

## TECH STACK

- Platform: Shopify / Horizon theme
- Animations: **GSAP 3.12.5 + ScrollTrigger** — loaded globally via CDN in `layout/theme.liquid`
- 3D Intro: Planned (Three.js or video-based) — not yet scoped

---

## DEVELOPMENT PRINCIPLES

- **Mobile-first on every section** — design and code for mobile first, then scale up
- Mobile responsiveness is #1 priority
- Breakpoints: `480px / 749px / 1024px / 1280px`
- Minimum tap target: 44px
- Test at 375px (iPhone SE) as baseline
- No horizontal overflow on any viewport
- Surgical edits only — never rewrite full files unnecessarily
- Consult before making ambiguous changes
- Every section must be functional end-to-end
- GSAP animations enhance UX without hurting performance
- Code must be modular — reusable snippets where possible
- No bloated or redundant CSS

---

## ANIMATIONS (GLOBAL RULES)

- GSAP is the animation library of choice
- Use ScrollTrigger for scroll-based animations
- Entrance animations on all major sections (fade, slide, stagger)
- Hover states: subtle, smooth, intentional
- Never sacrifice performance for animation — use `will-change` and GPU layers wisely

---

## NAVIGATION LINKS

Featured, Sneakers, Streetwear, Accessories, Collectibles
Icons: Search, Account, Wishlist (static placeholder — no functionality yet), Cart

---

## WHAT HAS ALREADY BEEN BUILT

### ✅ Task 1 — Global Setup
- `layout/theme.liquid` — Google Fonts (Cormorant Garamond 300–700 + Jost 300–600) + GSAP 3.12.5 + ScrollTrigger loaded in `<head>`
- `<html>` tag has `style="overflow-x: hidden"` to prevent page-level horizontal scroll

### ✅ Task 2 — Announcement Bar
- `sections/header-announcements.liquid`
- Background: burgundy `#6B1A2A`
- 3 messages: "Presha Verified Authenticity", "Worldwide Shipping", "Dubai Based"
- Desktop (≥750px): all 3 side-by-side with `|` separators
- Mobile: rotating slider (5s autoplay)
- Typography: Jost, 0.75rem, letter-spacing 0.06em, white
- GSAP: slides in from `yPercent: -100` on page load

### ✅ Task 3 — Header / Navigation
- `sections/header.liquid`, `snippets/header-actions.liquid`
- **Solid white** `#ffffff` background always (no glassmorphism — was removed in Task 11)
- 1px `rgba(0,0,0,0.08)` border-bottom
- Nav links: Jost, 0.8rem, weight 500, uppercase, letter-spacing 0.06em
- Logo: `logo-text-black.png` image asset (replaced text logo)
- Burgundy hover on nav links
- Wishlist icon: `assets/icon-wishlist.svg` — heart outline SVG, static placeholder, no functionality
- Country selector enabled; language selector disabled
- GSAP entrance: fade in + slight `y: -20` drop, 0.35s delay

### ✅ Task 4 & 5 — Hero Slideshow (Multi-Slide Carousel)
- `sections/slideshow.liquid`
- 3 branded slides with premium content structure:
  - Slide 1: "The Dubai Edit" — eyebrow "SHOP", CTA row: "Shop Now" (burgundy) + "Explore Brands" (ghost)
  - Slide 2: "Exclusive Drops" — eyebrow "SNEAKERS", CTA "Shop Sneakers"
  - Slide 3: "Premium Streetwear" — eyebrow "STREETWEAR", CTA "Shop Streetwear"
- Left-to-right dark gradient overlay (text side dark, image side transparent)
- Mobile: vertical gradient (dark bottom)
- H1: Cormorant Garamond `clamp(2.6rem–4.5rem)`, weight 500
- Primary button: burgundy `#6B1A2A`, hover `#8a2135`
- Secondary button: ghost white
- Pagination dots: 7px, burgundy active
- Autoplay progress bar: 3px burgundy at section bottom
- GSAP: slide content staggers up on load + on each slide change
- **NOTE:** Hero images still use placeholder uploads — real Dubai images need uploading via Admin → Files

### ✅ Task 6 — Category Pills
- `sections/category-pills.liquid` (new file)
- 4 default pills: Trending Now, Pokemon Collectibles, Chrome Hearts, Loewe x On
- **Dark cards** — `rgba(18,18,18,0.84)` with `backdrop-filter: blur(6px)`, subtle border
- Thumbnail on LEFT, text on RIGHT
- `SHOP BY` label (0.625rem uppercase muted-white) above bold category name
- Sits directly below hero (no negative margin overlap)
- Desktop: flex row, cards stretch equally
- Mobile: horizontal scroll, hidden scrollbar, fixed ~155px min-width for peek effect
- GSAP: stagger up on scroll entrance
- **NOTE:** Thumbnail images need uploading in Admin → Customize → Category Pills

### ✅ Task 7 & 8 — Footer
- `sections/footer.liquid`, `sections/footer-utilities.liquid`, `sections/footer-group.json`
- Dark navy `#0f1117` background
- 4-column layout: Brand col (logo + tagline + Instagram) + SHOP + SUPPORT + COMPANY
- Brand col: `logo-text-white.png` image asset + tagline + circular Instagram SVG icon
- Grid: `2fr 1fr 1fr 1fr` desktop, `1fr 1fr` tablet, single col mobile
- Menu links: Jost 0.9375rem at 65% white opacity
- Menu headings: Jost 0.6875rem, bold, uppercase, letter-spacing
- Menus accordion on mobile
- Copyright bar: `© 2026 Presha Trends. ALL RIGHTS RESERVED. Powered by Hollowkraft`
- GSAP: stagger in on ScrollTrigger
- **NOTE:** Real menus (`footer-shop`, `footer-support`, `footer-company`) need creating in Admin → Navigation

### ✅ Task 9 — Scrolling Marquee
- `sections/scrolling-marquee.liquid` (new standalone file)
- Background: `#111929` dark navy
- Jost 700, 0.8125rem, letter-spacing 0.12em, uppercase white, half-opacity bullet separators
- Seamless infinite scroll via CSS `@keyframes` + two identical strips
- Hover: JS lerps playback rate 1 → 0.12 via Web Animations API (smooth slow-down)
- Respects `prefers-reduced-motion`
- Positioned: slideshow → category pills → marquee on homepage

---

## ASSETS IN THEME

- `assets/logo-text-black.png` — black version of logo text (used in header)
- `assets/logo-text-white.png` — white version (used in footer)
- `assets/icon-wishlist.svg` — heart outline SVG for wishlist icon in header

---

## HOMEPAGE SECTION ORDER (`templates/index.json`)

1. `slideshow_thBVtw` — Hero slideshow (ACTIVE)
2. `category_pills_pTXsWa` — Category pills (ACTIVE)
3. `scrolling_marquee_*` — Scrolling marquee (ACTIVE)
4. `hero_jVaWmY` — Static hero (DISABLED — preserved in JSON)
5. Footer group (separate `footer-group.json`)

---

## PENDING ADMIN ACTIONS (Shopify Admin required by store owner)

### Navigation
- Create `main-menu` with 5 links: Featured, Sneakers, Streetwear, Accessories, Collectibles

### Footer Menus
- Create `footer-shop` menu (Sneakers, Streetwear, Accessories, Collectibles, New Arrivals)
- Create `footer-support` menu (Contact, FAQ, Shipping Policy, Returns, Authenticity)
- Create `footer-company` menu (About, Blog, Careers, Press)

### Images
- Upload 3 Dubai-specific hero images → assign to slideshow slides in Customizer
- Upload + assign thumbnail images for each category pill (square, min 200×200px)

---

## PAGES & SECTIONS — WHAT STILL NEEDS TO BE BUILT

### Homepage (remaining)
- [ ] Further sections TBD as designs come in

### Other Pages (all still to build)
- [ ] Collection / Category Page
- [ ] Product Detail Page
- [ ] About Page
- [ ] Cart Page
- [ ] Account Page

---

## TASK COMPLETION WORKFLOW (MANDATORY — every task)

1. Update `PROGRESS.md` — what was built, files changed, notes
2. Update `ADMIN_TODO2.md` if any Shopify Admin actions are required
3. Commit — format: `"Section Name - brief description"`
4. Push to Shopify: `shopify theme push --store agw1a7-eu.myshopify.com --theme 193819803729`
5. Provide preview link: `https://agw1a7-eu.myshopify.com?preview_theme_id=193819803729`
6. Wait for approval from project owner
7. On approval — push to GitHub: `git push origin main`

---

## DESIGN REFERENCES

All design screenshots are in `/design-refs/` (gitignored — not in repo, stored locally)
All designer assets are in `/design-assets/` (gitignored — not in repo, stored locally)

Current confirmed design refs:
- `hero.png` — full homepage: announcement bar + header + hero + category pills
- `Footer.png` — footer design

---

## PRODUCT NOTES

- Products are mostly one-of-one (resell) — inventory logic must reflect this
- Collections not fully set up yet — use `/collections/all` as placeholder
- Wishlist: no app integrated — static icon only for now

---

## KEY FILES REFERENCE

| File | Purpose |
|---|---|
| `layout/theme.liquid` | Global head (fonts, GSAP, overflow fix) |
| `sections/header.liquid` | Main navigation + logo |
| `snippets/header-actions.liquid` | Header icons (search, account, wishlist, cart) |
| `sections/header-announcements.liquid` | Announcement bar |
| `sections/header-group.json` | Header section config |
| `sections/slideshow.liquid` | Hero slideshow |
| `sections/hero.liquid` | Static hero (disabled, preserved) |
| `sections/category-pills.liquid` | Category pill cards |
| `sections/scrolling-marquee.liquid` | Scrolling ticker marquee |
| `sections/footer.liquid` | Footer main content |
| `sections/footer-utilities.liquid` | Footer copyright bar |
| `sections/footer-group.json` | Footer section config |
| `templates/index.json` | Homepage section order + settings |
| `assets/logo-text-black.png` | Header logo |
| `assets/logo-text-white.png` | Footer logo |
| `assets/icon-wishlist.svg` | Wishlist heart icon |
| `PROGRESS.md` | Build log — update after every task |
| `ADMIN_TODO2.md` | Shopify Admin actions required |
