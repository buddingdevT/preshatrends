# Presha Trends — Build Progress Log

---

> ## 🔴 MANDATORY INSTRUCTION FOR CLAUDE
> **After EVERY completed task, you MUST append a new section to the bottom of this file.**
> Do this BEFORE committing. Include:
> - What was built / changed
> - Which files were modified
> - Any important notes for future reference
>
> **No task is considered done until PROGRESS.md has been updated and committed.**

---

---

## Project Overview
- **Brand:** Presha Trends — luxury streetwear & sneaker resell, Dubai
- **Platform:** Shopify (Horizon theme, modified)
- **Fonts:** Cormorant Garamond (headings) + Jost (body/UI) — loaded via Google Fonts in `layout/theme.liquid`
- **Animations:** GSAP 3.12.5 + ScrollTrigger — loaded globally in `layout/theme.liquid`
- **Design reference:** `/designrefs/hero.png` (announcement bar + header + hero + category pills)

---

## Completed Tasks

---

### ✅ Task 1 — Global Setup (Fonts + GSAP)
**Commit:** `worked on announcement bar`
**Files changed:**
- `layout/theme.liquid`

**What was done:**
- Added Google Fonts preconnect + stylesheet for **Cormorant Garamond** (300–700, italic variants) and **Jost** (300–600)
- Added **GSAP 3.12.5** and **ScrollTrigger** via cdnjs CDN, loaded synchronously in `<head>` so they are available globally for all section animation scripts

---

### ✅ Task 2 — Announcement Bar
**Commit:** `worked on announcement bar`
**Files changed:**
- `sections/header-announcements.liquid`
- `sections/header-group.json`

**What was done:**
- Set background to brand burgundy `#6B1A2A` (already partially done, refined)
- Updated announcement content to 3 brand messages: **Presha Verified Authenticity**, **Worldwide Shipping**, **Dubai Based**
- Old placeholder messages (WhatsApp, arrivals, etc.) preserved in JSON blocks object but removed from `block_order` (effectively commented out)
- **Desktop (≥750px):** All 3 messages display simultaneously in one row with `|` pipe separators via CSS `::before` pseudo-element
- **Mobile:** Messages rotate via Horizon's built-in slider (autoplay every 5s)
- Typography: Jost, `0.75rem`, `letter-spacing: 0.06em`, white
- Bar is full-width (edge-to-edge) with compact `8px` top/bottom padding
- **GSAP entrance:** Bar slides in from `yPercent: -100` on page load (`power3.out`, 0.7s)

---

### ✅ Task 3 — Header / Navigation
**Commit:** `worked on header and nav`
**Files changed:**
- `sections/header.liquid`
- `snippets/header-actions.liquid`
- `sections/header-group.json`
- `assets/icon-wishlist.svg` *(new file)*

**What was done:**
- **Logo:** Styled with Cormorant Garamond 500, `1.35rem`, `letter-spacing: 0.05em` — overrides Horizon's body font fallback via `!important`
- **Nav links:** Jost 400, `0.8125rem` (13px), `letter-spacing: 0.04em`
- **Nav hover:** Burgundy `#6B1A2A` with `opacity: 1` override (replaces Horizon's default opacity-dimming behavior)
- **Active link:** Burgundy color
- **Wishlist icon:** Created `assets/icon-wishlist.svg` (heart outline, `stroke="currentColor"`); added as static `<a>` placeholder in `snippets/header-actions.liquid` between account and cart icons — no functionality yet
- **Country selector:** Re-enabled (`show_country: true`) — renders before wishlist in the right column
- **Language selector:** Disabled (`show_language: false`) — not needed for Dubai market
- **Removed:** Broken red hover custom CSS (`.header__menu-item:hover {color: #ff0000}` — was targeting a non-existent class)
- **GSAP entrance:** Header fades in with slight `y: -20` drop, `delay: 0.35s` (staggered after announcement bar), `power2.out`, 0.8s
- Nav links configured to use `main-menu` handle — **navigation links (Featured, Sneakers, Streetwear, Accessories, Collectibles) must be added in Shopify Admin → Navigation → Main menu**

---

---

### ✅ Task 4 — Hero Section
**Commit:** `worked on hero section`
**Files changed:**
- `templates/index.json`
- `sections/hero.liquid`

**What was done:**
- **Disabled** the old slideshow section (`slideshow_thBVtw`) — preserved in JSON but hidden from storefront
- **Enabled** the hero section (`hero_jVaWmY`) and moved it to first position on the homepage
- **Hero content** (all configured via `index.json` blocks):
  - Eyebrow: "SHOP" — Jost, 11px, uppercase, wide letter-spacing, white
  - Headline: "The Dubai Edit" — `<h1>`, styled via CSS to Cormorant Garamond `clamp(2.75rem–4.5rem)`, white, weight 500
  - Subtitle: "Curated luxury streetwear and rare sneakers from the world's most sought-after brands." — Jost, 15px, `#e8e8e8`
  - CTAs in a `group` block (row layout): "Shop Now" (primary/burgundy) + "Explore Brands" (ghost/outline white)
- **Hero settings:**
  - `section_height: "large"` — tall viewport-filling hero
  - `section_width: "page-width"` — content constrained, image full-bleed
  - `color_scheme: "scheme-6"` — dark/white text
  - `toggle_overlay: true`, `overlay_style: "gradient"`, `gradient_direction: "to right"` — dark on left (text side), transparent on right (model side), `#0a0a0ab3` (70% dark)
  - Content: left-aligned column, `gap: 16`, `padding-block-end: 80`
- **CSS additions to `sections/hero.liquid`:**
  - `h1` → Cormorant Garamond, `clamp()` responsive size, weight 500
  - `p` → Jost font, `line-height: 1.55`
  - Primary `.button` → burgundy `#6B1A2A` fill, lightens to `#8a2135` on hover
  - `.button-secondary` → ghost white, subtle hover background
  - Mobile overrides: headline scales down, button padding adjusted
- **GSAP animations:**
  - Hero content blocks stagger up (`y: 40 → 0`, `opacity 0 → 1`) with `0.14s` stagger, `delay: 0.9s`
  - Hero image (`hero__media-wrapper`) scales in from `1.06 → 1` over 1.6s (`power2.out`)
- **Note:** Hero image still uses the old Goyard placeholder — upload the correct Dubai hero image via Shopify Admin → Online Store → Customize → Hero section → Media 1

---

### ✅ Task 5 — Hero Slideshow (Multi-Slide Carousel)
**Commit:** `worked on hero slideshow`
**Files changed:**
- `sections/slideshow.liquid`
- `templates/index.json`

**What was done:**
- **Disabled** the single static hero section (`hero_jVaWmY`) — preserved in JSON but hidden
- **Re-enabled** and **rebuilt** the slideshow section (`slideshow_thBVtw`) as the new homepage hero
- **Moved slideshow to first position** in `index.json` order array
- **3 branded slides** with premium content structure:
  - Slide 1: "The Dubai Edit" (Goyard image) — eyebrow "SHOP", CTA group row: "Shop Now" (burgundy) + "Explore Brands" (ghost)
  - Slide 2: "Exclusive Drops" (Nike Mind image) — eyebrow "SNEAKERS", CTA "Shop Sneakers"
  - Slide 3: "Premium Streetwear" (streetwear image) — eyebrow "STREETWEAR", CTA "Shop Streetwear"
- **Slideshow settings:** `slide_height: "large"`, `autoplay: true`, `autoplay_speed: 6s`, `full_frame_on_mobile: true`, full-width
- **CSS additions to `sections/slideshow.liquid`:**
  - Custom left-to-right gradient overlay via `::after` (dark editorial left panel, fades to transparent right)
  - Mobile override: vertical gradient (dark bottom) for readability on portrait images
  - All slide text → Jost base font, H1 override → Cormorant Garamond `clamp(2.6rem–4.5rem)`, weight 500
  - Primary button → burgundy `#6B1A2A`, hover `#8a2135`
  - Secondary button → ghost white with hover fill
  - Pagination dots → 7px circles, burgundy active state with scale(1.6)
  - Navigation arrows → white, 0.65 opacity, full on hover
  - Desktop padding boost → 72px inline-start at ≥1024px
  - Autoplay progress bar → 3px burgundy line at section bottom, CSS positioned absolutely
- **GSAP animations:**
  - On initial load (0.7s delay): first slide content stagers up (`y: 32 → 0`, `opacity 0 → 1`, `stagger: 0.12s`)
  - On slide change (detected via scroll event + 240ms debounce on `slideshow-slides`): same stagger animation fires for incoming slide
  - Autoplay progress bar: `scaleX: 0 → 1` over the autoplay duration, resets on each slide change
- **Note:** Slide images use existing uploaded files. Upload new Dubai-specific hero images via Shopify Admin → Files to replace the current placeholder images per slide.

---

## Upcoming Tasks

- [ ] Upload proper hero images for each slide (currently using existing uploaded files)
- [ ] Category Pills
- [ ] Collection / Category Page
- [ ] Product Detail Page
- [ ] About Page
- [ ] Cart Page
- [ ] Account Page
- [ ] Footer
