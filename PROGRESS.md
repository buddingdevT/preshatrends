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

## Upcoming Tasks

- [ ] Hero Section
- [ ] Category Pills
- [ ] Collection / Category Page
- [ ] Product Detail Page
- [ ] About Page
- [ ] Cart Page
- [ ] Account Page
- [ ] Footer
