# Signalflow Landing Page — Antigravity Submission

**Challenge:** Design Engineer 001  
**Candidate:** Antigravity  
**Time target:** 3–4 hours

---

## How to Run

No build step required. Serve the folder from any static HTTP server:

```bash
# Python
python -m http.server 9090 --directory .

# Node
npx serve .
```

Then open **http://localhost:9090** in your browser.

---

## What Was Built

A fully responsive, production-grade B2B SaaS landing page for **Signalflow** — built from scratch in a single `index.html` file with vanilla CSS and vanilla JS, augmented by the [Motion](https://motion.dev) library for animations.

### Sections

| # | Section | Notes |
|---|---------|-------|
| 1 | **Nav** | Sticky, glassmorphic, with a demo modal CTA |
| 2 | **Hero** | Split-screen: value prop left, animated SVG network graph right |
| 3 | **Feature Cards** | 3 flip cards overlapping the hero, orange back face on hover |
| 4 | **Logo Bar** | Tier-1 brand logos as styled SVG text |
| 5 | **Problem** | Narrative pain section before features |
| 6 | **The Solution** | 6-card 3×2 grid with flip animations and detail backs |
| 7 | **Social Proof** | Animated stat counters + testimonial |
| 8 | **Final CTA** | Single orange CTA button, dark navy section |
| 9 | **Footer** | Minimal, dark |

---

## Where It Outperforms the AI Baseline

| Dimension | AI Baseline | This Submission |
|-----------|-------------|-----------------|
| **Layout** | Full-width centered columns | Split hero, staggered depth |
| **Iconography** | Emoji (`📊 ⚡`) | Dual-color SVG line-art, 1.75px stroke |
| **Narrative** | Features → CTA | Problem → Solution → Proof → CTA |
| **Visual rhythm** | All white/light gray | Navy + light alternation for scroll pacing |
| **Interactivity** | None | 3D flip cards, animated counters, parallax, modal |
| **Animations** | None | 12 scroll-triggered sequences via Motion library |
| **Trust signals** | Text only | Stat counters, logo bar, attributed testimonial |
| **CTA strategy** | One generic button | Tiered: nav demo → hero demo → sales CTA |

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Vanilla HTML/CSS | Structure and all styling |
| [Motion](https://motion.dev) (`motion@latest` ESM CDN) | Spring-based scroll animations, hero entrance, parallax, modal |
| SVG | Hero network graph, all icons, logo bar |
| Python HTTP server | Local preview |

No build tools. No frameworks. No dependencies to install.

---

## Animation System

The page uses the **Motion** library (the web-native sibling of Framer Motion, same creator, same API) for:

- **Hero entrance** — staggered fade-up sequence on load: label → h1 → subtext → CTA → trust logos
- **Network graph** — spring scale-in per node with stagger offset
- **Flip cards** — spring stagger-in on scroll for both card rows
- **Section labels** — slide in from left
- **Stat counters** — count up with eased `requestAnimationFrame`
- **Modal** — spring pop-in, scale-out on close
- **Parallax** — hero visual drifts at 8% scroll rate

---

## File Structure

```
submissions/antigravity/
├── index.html      # Entire page — HTML, CSS, JS in one file
├── rationale.md    # Design decisions and critique of AI baseline
├── README.md       # This file
└── assets/
    └── .gitkeep
```

---

## Design Decisions

See [`rationale.md`](./rationale.md) for a full breakdown of every decision made and the specific weaknesses identified in the AI-generated baseline.

Key calls:

1. **Split hero** — puts the product visualization in front of buyers before they've read a word
2. **Problem section** — VP Sales buyers need to feel seen before they trust a solution
3. **Flip cards** — surface 3 points of evidence without adding page height
4. **Dark sections** — visual rhythm to control scroll pace and eye movement
5. **Single CTA in final section** — reduced from two buttons to one high-intent orange button ("Talk to Sales") to eliminate decision paralysis at conversion point
