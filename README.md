# Victoria Badminton Centre — Website

Single-file HTML site. Just open `index.html` in a browser, or upload the whole folder to any static host (Netlify, Vercel, GitHub Pages, Cloudflare Pages, or a cPanel host).

## File structure
```
victoria-badminton/
├── index.html        ← the whole site
└── assets/
    └── logo.jpg      ← your logo
```

## Quick customization guide

### 1. Going live — turn off the "Coming Soon" overlay
Open `index.html`, find this line near the top of the `<style>` block:
```css
--coming-soon: 1;
```
Change `1` to `0` to hide the overlay. That's it — the full site underneath was already built and running.

Alternatively, visitors can already click **"Preview the site →"** at the bottom of the overlay to peek through, which is useful during the marketing phase.

### 2. Update the launch countdown
In the `<script>` block at the bottom of `index.html`:
```js
launch.setDate(launch.getDate() + 90); // currently 90 days from load
```
Replace with a fixed date, e.g.:
```js
const launch = new Date('2026-07-15T10:00:00+10:00');
```

### 3. Replace the Google Map
Go to [maps.google.com](https://maps.google.com), search your real address, click **Share → Embed a map**, copy the `src` URL from the iframe, and paste it over the existing one in the `<iframe>` inside the `.map-frame` div. Also update the address text just above it (there are two spots — the Visit section and the footer).

### 4. Update opening hours, phone, email
Find the `.hours-list` section for hours, and the footer `Contact` column for phone/email. Plain text edits.

### 5. Hook up social media
Every `<a href="#" aria-label="...">` in the socials blocks (there are two sets — one in Coming Soon, one in the footer). Replace `#` with the real Instagram/Facebook/TikTok/WhatsApp/YouTube URLs.

### 6. Book a Court button
Currently all "Book a Court" buttons point to `#book` (the CTA section) and the big button shows an alert. When your booking system is live, change the `href` on these to your booking URL:
- Nav button (top right)
- Hero primary button
- Footer CTA → remove the `onclick` and set `href` to the real URL

### 7. Partners
The Yonex and Victor "logos" are styled text placeholders — a common approach until you receive official logo files from the brands (required for proper usage). Once you have approved logo files, replace the `<div class="logo-box yonex">YONEX</div>` blocks with `<img>` tags.

### 8. Photos
All gallery and hero images are pulled from Unsplash (free to use). When you have real photos of the centre, replace the image URLs — that's the single biggest upgrade you can make to the site.

## Colors (all in CSS variables at the top)
- `--olive-800` #3d4a1f — logo background
- `--coral` #e8936b — logo figure
- `--gold` #d4b85a — logo accent stars
- `--cream` #f4efe3 — page background

## Typography
- **Bebas Neue** — display (headings, buttons)
- **Fraunces** — editorial serif (italic accents, quotes)
- **Inter** — body

All loaded from Google Fonts; no install required.
