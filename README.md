# SPATCO Energy Solutions × Salesforce — Executive Microsite

A self-contained, interactive executive microsite built for the SPATCO Energy Solutions pursuit. It is a **pre-close pitch site** aimed at getting final sign-off on Phase 1 — not a post-sale onboarding hub.

**Live site:** https://edalton122.github.io/spatco-salesforce-deck/

---

## What's in here

| File | Purpose |
|---|---|
| `index.html` | The microsite. Ten full-viewport slides, all CSS and JS inline. |
| `exec-summary.html` | Print-ready one-page executive summary. |
| `bva.html` | Business Value Assessment — donut + stacked bar, per-category breakdowns, assumptions table. Print to PDF. |
| `team.html` | Account team page. |
| `photo-ae.png` | Samuel Schmal headshot. **Drop this file in the repo root.** |
| `photo-se.jpg` | Eric Dalton headshot. **Drop this file in the repo root.** |

No build step, no framework, no CDN dependencies beyond the Google Fonts `<link>`. Open `index.html` in any modern browser and it works — including offline, apart from the font falling back to a system sans.

---

## The ten slides

1. **Hero** — "Built for the Road to $800M," growth stats, the three pain points, Phase 1 product row.
2. **The Challenge** — three flip cards: fragmented quoting, reactive-only sales, no campaign attribution.
3. **Platform Overview** — Sales Cloud / Marketing Cloud / Data Cloud Foundations, each opening a detail drawer.
4. **Product Demo** — trade-show lead → CRM record → follow-up, with a phone frame awaiting demo footage.
5. **A Technician's Day** — the flagship interactive: an 8-screen field-service walkthrough. Explicitly labeled as Phase 2 / forward-looking.
6. **Connected Ops** — before/after toggle. Three tools get absorbed; SAP stays put.
7. **Architecture** — five layers, with the Einstein Trust Layer featured.
8. **Executive Dashboard** — simulated Lightning UI with four tabbed KPI views.
9. **Business Value Calculator** — the real $115K investment snapshot plus four interactive tabs and a PDF export.
10. **Path Forward** — outcome cards, the real SOW Gantt, org chart, and contact CTAs.

---

## Messaging guardrails

These are baked into the copy. Keep them if you edit:

- **Only Sales Cloud, Marketing Cloud, and Data Cloud Foundations are in scope today.** Field Service, Revenue Cloud, and Agentforce appear only as clearly labeled roadmap direction.
- **SAP is never displaced or disparaged.** It is the system of record. Salesforce is the front-end CRM and engagement layer that syncs with it.
- **No real SPATCO names, accounts, or dollar figures inside demo screens.** The technician is "Marcus Webb," the site is "Ridgeline Manufacturing," and the equipment IDs are invented.
- **LogicRain Technologies Inc.** is named as the implementation partner, but the spotlight stays on Salesforce as the platform.
- Tone is confident, not hyped. Every claim should trace back to something SPATCO or the deal team actually said.

---

## Real deal data used

- Phase 1 implementation: **$115,000 fixed**, 14–16 weeks, **Aug 10 → Nov 27, 2026**
- Breakdown: Sales Cloud configuration $50,000 · SPIFF commission implementation $50,000 · Data migration (up to 50K records) $15,000
- Payment milestones: $57,500 → $19,250 → $19,250 → $19,000
- Comparative context: SPATCO's ~$411K/year SAP Field Service & Asset Management spend — a separate system, not being replaced
- Audience: Kevin Bretcher (CRO, champion), John Force (CEO), Scott Wattenberg (CFO)

---

## Common edits

**Adding the headshots.** Drop `photo-ae.png` and `photo-se.jpg` into the repo root. The `<img>` tags already reference those exact filenames and fall back to initials avatars until the files exist.

**Adding Grant Stephens' photo.** Search for `TODO: replace with photo-rvp.png` (three places: `index.html`, `exec-summary.html`, `team.html`) and swap the initials `<div>` for an `<img src="photo-rvp.png">`.

**Adding demo footage to Slide 4.** Search `TODO: drop in demo-loop.mp4` in `index.html` and replace the placeholder `.pfv-screen` contents with a `<video>` element.

**Changing calculator assumptions.** The four tabs are driven by `calcBvc()` near the bottom of `index.html`. Slider defaults live in the `value=` attributes of each `<input type="range">`. Every input is tagged in the UI as either *SPATCO actual* or *industry benchmark* — keep that labeling honest when you change a default.

**Editing the Gantt.** Bar positions are inline `left`/`width` percentages over a 16-week grid (each week = 6.25%). Row detail copy is in the `GANTT_DETAIL` array.

**Editing the interactive demo.** Screen copy for the left-hand panel lives in `DEMO_CONTEXT`. Screen markup is `ds-screen-1` through `ds-screen-8`. Three rules worth respecting: never put an inline `position:` on a `.demo-screen` div, never put two `display:` values in one `style` attribute, and clear `target.style.transform` before adding `ds-active`.

---

## Presenting it

Scroll, use the dot nav on the right edge, or use the arrow keys. Slide 5 is the one to spend time on — tap through all eight screens. Slide 9's sliders are meant to be moved live in front of the CFO.

---

*Prepared by the Salesforce account team for SPATCO Energy Solutions · September 2026 · Confidential*
