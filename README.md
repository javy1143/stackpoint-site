# StackPoint IT — Website

Static marketing site for **StackPoint IT**, a managed IT and cybersecurity services provider targeting SMBs without an internal IT department.

---

## Tech Stack

- **Pure HTML/CSS** — zero framework dependencies, no build step required
- **Vanilla JavaScript** — mobile nav, scroll spy, intersection observer animations
- **Google Fonts** — Exo 2 (display) + IBM Plex Sans (body), loaded via `<link>` preconnect
- **Deployment** — Cloudflare Pages (static, zero-config)

---

## Project Structure

```
/
├── index.html          # Single-page site — all markup, styles, and scripts inline
└── assets/
    └── logo.png        # StackPoint IT logo (used in navbar, footer, og meta)
```

> All CSS is inlined in `<style>` using a utility-class system. There are no external stylesheets.

---

## Sections

| Anchor | Section |
|---|---|
| *(top)* | Hero — headline, CTA buttons, trust badges |
| `#services` | Services — patch management, vuln management, endpoint management |
| `#compliance` | Compliance carousel — PCI DSS, HIPAA, SOC 2, CIS CSC, GLBA/FFIEC |
| `#pricing` | Pricing — Essentials ($15/device/mo) and Professional ($95/user/mo) |
| `#resources` | Why StackPoint IT — six differentiator cards |
| `#contact` | CTA — free vulnerability assessment request |

---

## Design System

### Color Palette

| Variable | Hex | Usage |
|---|---|---|
| `--bg` | `#060D17` | Page background |
| `--surface` | `#0A1220` | Card surfaces |
| `--surface-light` | `#111D2E` | Elevated surfaces |
| `--surface-lighter` | `#1A2B42` | Borders, dividers |
| `--primary` | `#0E8AD4` | Primary blue |
| `--primary-light` | `#2EA3F0` | Hover state |
| `--accent` | `#00D4FF` | Accent cyan |
| `--text-primary` | `#E8EDF3` | Body text |
| `--text-secondary` | `#8899AB` | Muted text |

### Typography

- **Display / Headings** — Exo 2 (`--font-display`)
- **Body / UI** — IBM Plex Sans (`--font-body`)

---

## JavaScript Behaviors

- **Mobile nav** — slide-in drawer (288px) with overlay and body scroll lock
- **Navbar scroll** — background opacity and border-color transition after 80px scroll
- **Scroll animations** — `IntersectionObserver` on `.rv` elements, staggered with 80ms delay per element
- **Smooth scroll** — all `href="#..."` anchor links scroll with 80px navbar offset compensation
- **Compliance carousel** — pure CSS `scroll-x` keyframe animation, pauses on hover

---

## Deployment (Cloudflare Pages)

1. Push to your connected Git repository (GitHub/GitLab)
2. Cloudflare Pages auto-builds on push — no build command needed
3. Set **Build output directory** to `/` (root)

No environment variables, no build dependencies.

---

## Contact & CTA Routing

All CTAs route to `mailto:` links:

| Action | Address | Subject Line |
|---|---|---|
| Essentials inquiry | `support@stackpointit.com` | `Essentials Tier Inquiry` |
| Professional inquiry | `support@stackpointit.com` | `Professional Tier Inquiry` |
| Free assessment | `support@stackpointit.com` | `Free Vulnerability Assessment Request` |
| General contact | `support@stackpointit.com` | `General Inquiry` |

> To add a form backend (Cloudflare Turnstile + Workers, Formspree, etc.), replace `mailto:` hrefs with a `<form>` pointing to your preferred endpoint.

---

## License

&copy; 2025 StackPoint IT. All rights reserved. Not open source — proprietary business site.
