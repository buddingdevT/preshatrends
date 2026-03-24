# Presha Trends — Shopify Admin Todos

> These are tasks that must be completed inside **Shopify Admin** (not in code).
> This file is updated by the developer after every build task that requires Admin action.

---

## 🧭 Navigation

- [ ] **Create "Main Menu"** in Shopify Admin → Navigation (handle: `main-menu`)
  - Add links: Featured, Sneakers, Streetwear, Accessories, Collectibles

---

## 🦶 Footer Menus

- [ ] **Create "footer-shop" menu** → Admin → Navigation (handle: `footer-shop`)
  - New Arrivals, Sneakers, Apparel, Accessories, Collectibles

- [ ] **Create "footer-support" menu** → Admin → Navigation (handle: `footer-support`)
  - Authentication, Shipping Policy, Returns & Refunds, Track Order, Contact Us

- [ ] **Create "footer-company" menu** → Admin → Navigation (handle: `footer-company`)
  - Our Story, Journal, Careers, Privacy Policy, Terms of Service

---

## 🖼️ Media / Images

- [ ] **Upload hero images** (one per slideshow slide) → Admin → Content → Files
  - Slide 1: The Dubai Edit (Goyard)
  - Slide 2: Exclusive Drops (Sneakers)
  - Slide 3: Premium Streetwear
  - Then assign via: Online Store → Customize → Slideshow → each slide → Media

- [ ] **Upload category pill thumbnails** → Admin → Content → Files
  - Trending Now, Pokemon Collectibles, Chrome Hearts, Loewe x On
  - Then assign via: Online Store → Customize → Category Pills → each pill → Image

---

## 🏪 Collections

- [ ] Create collection handles referenced in code (use these exact handles):
  - `new-arrivals`
  - `sneakers`
  - `apparel` (or `streetwear`)
  - `accessories`
  - `collectibles`
  - `goyard`, `rimowa`, `audemars-piguet`, `patek-philippe`, `jacquemus` (brand collections)

---

## 📄 Pages

- [ ] Create page: `pages/authentication` — Authentication & verification info
- [ ] Create page: `pages/track-order` — Order tracking info
- [ ] Create page: `pages/contact` — Contact form
- [ ] Create page: `pages/our-story` — Brand story
- [ ] Create page: `pages/careers` — Careers (placeholder OK for now)

---

## ⚙️ Theme Settings

- [ ] **Set favicon** → Admin → Online Store → Themes → Customize → Theme settings → Favicon
- [ ] **Set store logo** → Admin → Online Store → Themes → Customize → Header → Logo image
  - Use `logo-full.png` or the appropriate logo asset

---

## 🛍️ Products

- [ ] Begin adding products — inventory logic: each product is **one-of-one** (quantity = 1, track inventory enabled, do not allow oversell)
- [ ] Set up metafields if needed for custom product data (scope TBD per section)

---

> ✏️ *Developer note: Update this file with a new item every time a build task requires an Admin action. Mark items `[x]` when confirmed done by the store owner.*
