# 🌾 Flour Finder — Edinburgh Baker's Guide

> A mobile-first artisan flour recommendation tool for home bakers in Edinburgh.  
> Built in a single HTML file. No dependencies, no build step, no framework.

![Screenshot](https://img.shields.io/badge/status-active-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Language](https://img.shields.io/badge/lang-EN%20%2F%20HU-orange)

---

## What it does

Flour Finder asks 5 questions about your bake, then recommends the best UK-available artisan flour for your specific situation — with a hydration calculator, baking schedule, and per-step countdown timers.

**Questions:**
1. What are you baking? (Sourdough / Yeasted / Baguette)
2. What matters most? (Rise / Flavour / Local Scottish / Organic)
3. How are you baking it? (Dutch oven / Baking stone / Bread tin)
4. Your experience level? (Beginner / Intermediate / Advanced)
5. Kitchen conditions (oven temp + kitchen temperature)

**Results include:**
- Best flour recommendation with protein %, W-Index, price/kg
- Calculated hydration % adjusted for your flour, oven, and kitchen temp
- Timed baking schedule (cold/warm kitchen aware, sourdough vs yeasted)
- ⏱ Per-step countdown timers with audio alert
- Where to buy in Edinburgh (clickable links)
- Runner-up flour suggestion
- Edinburgh climate note (cool damp kitchens)

---

## Features

- 🌍 **Bilingual** — English / Hungarian toggle, remembers nothing (stateless)
- ⏱ **Step timers** — compact bottom bar with pause/resume + audio beep on finish
- 💧 **Hydration calculator** — adjusts for flour type, kitchen temp, experience, oven power
- 🔡 **Font size toggle** — 100% / 120%, saved to localStorage
- 🛒 **Working links** — Ocado, Amazon, Shipton Mill, Wessex Mill, Real Foods, BakeryBits, Waitrose
- 📱 **Mobile-first** — max-width 430px, touch-optimised
- 🎨 **Artisan design** — Playfair Display + Lora serif, warm parchment palette

---

## Flour database

| Flour | Protein | W-Index | Price/kg | Best for |
|---|---|---|---|---|
| Marriage's Very Strong Canadian | 15.0g | — | £1.31 | Yeasted, high hydration |
| Shipton Mill Organic No. 4 | 13.0g | 275 | £1.75 | Sourdough, artisan |
| Mungoswells Extra Strong | 13.5g | — | £2.10 | Local Scottish, sourdough |
| Doves Farm Organic Strong White | 12.5g | — | £1.33 | Organic, beginners, tin |
| Wessex Mill Strong White | 12.6g | — | £2.00 | Yeasted, all-rounder |
| Wildfarmed T65 | 11.5g | — | £2.20 | Baguette, flavour, advanced |

---

## Usage

No install. No build. Just open the file.

```bash
git clone https://github.com/YOUR_USERNAME/flour-finder
cd flour-finder
open flour-finder.html
```

Or drag `flour-finder.html` into any browser.

Works offline after first load (Google Fonts require internet on first visit).

---

## File structure

```
flour-finder/
├── flour-finder.html   # Everything. Single file app.
└── README.md
```

---

## Tech stack

| Thing | How |
|---|---|
| Fonts | Google Fonts (Playfair Display + Lora) |
| Icons | Unicode emoji only |
| CSS | Custom properties (CSS variables), no framework |
| JS | Vanilla, no libraries |
| Audio | Web Audio API (timer beep) |
| Storage | localStorage (scale preference only) |

---

## Scoring logic

Each flour is scored against your answers:

- `+4` if flour tags match bread type (sourdough / yeasted / baguette)
- `+4` if flour matches priority (organic, local, strength ≥ 13.5g protein, flavour)
- `+2` if flour matches baking vessel (dutch oven / stone / tin)
- `+2` if flour matches experience level
- `+3` bonus for beginner-friendly flours when user selects Beginner
- `+1` bonus for high-protein flour when oven ≥ 250°C

Hydration base per flour is adjusted by:
- Kitchen temp (`cool` −2 to −3%, `hot` +2 to +3%)
- Oven temp (`<220°C` −2%, `≥250°C` +1%)
- Experience (`beginner` −3%, `advanced` +2%)

---

## Roadmap / ideas

- [ ] Add more Edinburgh-local flours (Scotland The Bread, Watermill, Golspie Mill)
- [ ] Offline PWA / installable app
- [ ] Flour comparison table (swipe between top 3)
- [ ] Recipe cards per flour recommendation
- [ ] Polish / French / German language support
- [ ] Dark mode

---

## Background

Built as a portfolio project alongside a micro-bakery business plan research for Edinburgh (Morningside / Oxgangs area). Covers the B2B wholesale café market, Natasha's Law allergen requirements, REHIS food hygiene certification, and Scottish Kitchen Hire options.

The Flour Finder was designed to help home bakers — particularly those using a **casserole pot or baking bricks** (Dutch oven method) — find the right flour without wading through conflicting advice online.

---

## License

MIT — use freely, attribution appreciated.

---

*Made in Edinburgh. Baked with Mungoswells flour.*
