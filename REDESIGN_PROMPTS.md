# Quantra Website — Full Redesign Prompts
## For use with Claude Code, step by step

**Design direction:** Dark premium agency aesthetic — deep dark backgrounds, floating animated pill shapes, gradient text, glassmorphism navbar, glowing card hovers. Inspired by high-end SaaS/agency sites. Pure HTML/CSS/JS, no framework.

**Status tracking:** Check off each step as you complete and verify it in the browser.

---

## Step 1 — CSS Foundation & Design System
**Status:** [x] Complete

Rewrite the :root CSS variables and base body styles in css/style.css for a full dark-theme redesign of the Quantra Ltd website.

New design direction: dark, premium, agency aesthetic — similar to high-end SaaS/agency sites.

New values:
```
--bg: #0a0a0f
--bg-alt: #0f0f1a
--bg-card: #13131f
--primary: #ffffff
--accent: #4f7eff
--accent-2: #a78bfa
--text: #e2e2e8
--text-muted: rgba(226, 226, 232, 0.5)
--border: rgba(255, 255, 255, 0.08)
--font-heading: 'Syne', sans-serif
--font-body: 'DM Sans', sans-serif
```

Also update body: background-color to var(--bg), color to var(--text), and keep scroll-behavior: smooth on html.

Do not touch any section HTML yet — only the CSS variables and body/html base styles.

---

## Step 2 — Hero Section (Animated Geometric Background)
**Status:** [x] Complete

Redesign the hero section in index.html and its styles in css/style.css. Keep the same HTML IDs and class structure where possible.

Design requirements:
- Full viewport dark background (#0a0a0f)
- 5 floating pill/capsule shapes in the background (absolutely positioned divs with border-radius: 9999px). Each pill should have a subtle gradient using one of these colors at low opacity: indigo (#6366f1), violet (#8b5cf6), rose (#f43f5e), amber (#f59e0b), cyan (#06b6d4). Each pill has a glowing border: border: 1px solid rgba(255,255,255,0.12) and a blur backdrop.
- Pills animate: float up and down infinitely using @keyframes float with different durations (10s, 14s, 18s, 12s, 16s) and delays so they move independently
- Pills also entrance-animate: start at opacity 0, translateY(-80px), rotate slightly, then ease into position on page load with staggered CSS animation-delay values
- Hero content centered, max-width 800px, text-align center
- Badge pill at top: small rounded pill with border: 1px solid rgba(255,255,255,0.1), background rgba(255,255,255,0.04), text "Digital Agency" in var(--accent) color
- H1: "We handle your online presence so you don't have to." — font Syne bold, clamp(2.6rem, 5.5vw, 4.2rem), white gradient text using: background: linear-gradient(to bottom, #ffffff, rgba(255,255,255,0.75)), -webkit-background-clip: text, -webkit-text-fill-color: transparent
- Subtext paragraph below in var(--text-muted)
- Two buttons: primary filled accent (#4f7eff), secondary ghost with white border
- Bottom fade overlay: gradient from transparent to var(--bg) at the very bottom of the section

All animations CSS only. No JS needed for this section.

---

## Step 3 — Navbar (Glassmorphism Dark Style)
**Status:** [x] Complete

Redesign the navbar in index.html and css/style.css.

Requirements:
- Keep position: fixed, top 0, z-index 1000, height 68px
- Default state: background: rgba(10, 10, 15, 0.6), backdrop-filter: blur(16px), border-bottom: 1px solid rgba(255,255,255,0.06)
- .scrolled state: background: rgba(10, 10, 15, 0.92), border-bottom: 1px solid rgba(255,255,255,0.1), box-shadow: 0 4px 24px rgba(0,0,0,0.4)
- Logo text "Quantra" in Syne bold white, "Ltd" in var(--accent)
- Nav links: white at 70% opacity, hover to full white, keep the underline hover animation but use var(--accent) color
- Keep the existing JS scroll listener (just toggle .scrolled class at 50px)
- Add a CTA button "Get Started" on the right side — small, filled with var(--accent), border-radius 6px, links to #contact

---

## Step 4 — Services Section (Dark Cards with Glow)
**Status:** [x] Complete

Redesign the services section in index.html and css/style.css.

Requirements:
- Background: var(--bg-alt) (#0f0f1a)
- Section label, h2, and subtext updated for dark theme (white/muted text)
- 4 service cards in 2x2 grid:
  - background: var(--bg-card) (#13131f)
  - border: 1px solid var(--border)
  - border-radius: 14px, padding: 2rem
  - On hover: border-color changes to rgba(79, 126, 255, 0.4), box-shadow: 0 0 30px rgba(79, 126, 255, 0.08), transform: translateY(-4px)
  - Icon area: replace emoji with a square icon container (48x48px, background: rgba(79,126,255,0.1), border-radius: 10px, centered). Use a simple CSS shape or keep emoji for now but wrap it in this container.
  - Card title in white Syne bold
  - Card description in var(--text-muted)
  - A subtle right-arrow "→" at bottom right of card in var(--accent) that appears on hover
- Keep existing IntersectionObserver scroll animation, update to work with new card styles
- border-bottom between sections: 1px solid var(--border)

---

## Step 5 — About Section (Dark Layout with Trust Card)
**Status:** [x] Complete

Redesign the about section in index.html and css/style.css.

Requirements:
- Background: var(--bg)
- Left column text updated for dark theme — body text in var(--text), section label in var(--accent)
- Stats row: stat values in white Syne bold, stat labels in var(--text-muted). Add a subtle top border using var(--border)
- Trust card (right column):
  - Background: linear-gradient(145deg, rgba(79,126,255,0.12) 0%, rgba(167,139,250,0.08) 100%)
  - Border: 1px solid rgba(79, 126, 255, 0.2)
  - border-radius: 16px
  - Heading label in var(--text-muted)
  - List items in white with the existing accent dot (keep the square 8px dot in var(--accent))
- Keep the existing fade-up scroll animations

---

## Step 6 — Contact Section (Dark Form & WhatsApp Card)
**Status:** [ ] Complete

Redesign the contact section in index.html and css/style.css.

Requirements:
- Background: var(--bg-alt)
- Section header text in white/muted
- Form inputs:
  - background: rgba(255,255,255,0.04)
  - border: 1px solid var(--border)
  - color: var(--text)
  - border-radius: 8px
  - On focus: border-color: var(--accent), box-shadow: 0 0 0 3px rgba(79,126,255,0.15)
  - Placeholder: var(--text-muted)
- Submit button: full width, var(--accent) background, white text
- WhatsApp card (right column):
  - background: linear-gradient(145deg, #0d1f0d, #0a1a0a)
  - border: 1px solid rgba(37, 211, 102, 0.2)
  - border-radius: 16px
  - Keep the green WhatsApp button (#25D366)
  - Heading and subtext in white/muted
- Floating WhatsApp button: keep as is but ensure it works with dark theme
- Labels above inputs: var(--text-muted), font-size 0.85rem

---

## Step 7 — Footer (Consistency Update)
**Status:** [ ] Complete

Update the footer in index.html and css/style.css to match the new dark theme.

Requirements:
- Background: #070710 (slightly deeper than --bg to create separation)
- Border-top: 1px solid var(--border)
- Logo: "Quantra" white bold, "Ltd" in var(--accent)
- Tagline: var(--text-muted)
- Quick links label and contact label: var(--text-muted) uppercase small
- Links: rgba(255,255,255,0.6) default, hover white
- Social buttons: keep the existing var(--accent) background, update hover to rgba(79,126,255,0.8)
- Email link: var(--accent) color
- Copyright bar border: var(--border)
- Copyright text: rgba(255,255,255,0.25)

Do not change the HTML structure — CSS updates only.

---

## Step 8 — Final Polish & Consistency Pass
**Status:** [ ] Complete

Do a full consistency and polish pass on the Quantra website (index.html + css/style.css):

1. Ensure all section-label spans use var(--accent) color and uppercase letter-spacing consistently
2. Ensure all h2 section headings are white and use Syne font
3. Ensure all section-sub paragraphs use var(--text-muted)
4. Add a subtle noise/grain texture overlay to the body using a CSS pseudo-element with a data URI SVG noise pattern at very low opacity (0.03) — this adds depth to the dark backgrounds
5. Ensure scroll-margin-top values are correct for all sections (navbar is 68px now)
6. On mobile (max-width: 768px): ensure hero pills are smaller and don't overflow, text sizes are correct, buttons stack vertically
7. Check all border colors use var(--border) consistently
8. Ensure .btn--primary has a subtle glow on hover: box-shadow: 0 0 20px rgba(79,126,255,0.35)
9. Save the full updated file — do not truncate any section

---

## Notes
- Site stack: plain HTML/CSS/JS — no React, no Tailwind, no build step
- Hosted on Vercel, auto-deploy on push to main
- Repo: https://github.com/Aman112233/quantra-website
- After each step: preview in browser before committing
- Commit message format suggestion: `redesign: step N — [section name]`

---

## Pending Sections (after redesign)
- [ ] Testimonials section
- [ ] Portfolio section  
- [ ] Process section
