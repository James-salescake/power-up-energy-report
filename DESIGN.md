# DESIGN.md — Power Up Solutions Executive Design System

> **Design Vision:** An ultra-clean, Apple-grade executive presentation studio and homeowner energy proposal document. Zero generic AI clutter, calm split-workspace ergonomics, high intentional whitespace, and tabular numerical precision.

---

## 1. Design Philosophy & Foundations

1. **Executive Clarity Over Clutter:**  
   Replace complex multi-step wizards with a single continuous, beautifully structured executive comparison document. Homeowners at kitchen tables digest information through stark visual contrast, not cognitive overload.
2. **Side-by-Side Anchoring:**  
   Never show a solar payment or kWh rate in isolation. Every solar metric is immediately anchored by the utility equivalent and the corresponding annual escalation trajectory.
3. **Strict Sandboxed Isolation (`#power-up-app`):**  
   Every style token, component class, and keyframe is encapsulated within `#power-up-app`. External GoHighLevel (GHL) funnel CSS cannot bleed in, and internal styles cannot bleed out.
4. **Zero-Dependency Self-Containment:**  
   No external CDNs, fonts, or scripts. Everything runs natively in standard browser engines with complete offline resilience.

---

## 2. Color Palette & Semantic Tokens

| Token Name | Hex Code | Purpose & Semantic Usage |
|---|---|---|
| `--pu-black` | `#0a0a0c` | Primary executive header bar, branded document headers, high-contrast dark accents |
| `--pu-charcoal` | `#16181d` | Secondary dark backgrounds, dark button hover states |
| `--pu-ink` | `#111827` | Primary body typography (neutral-900), card headings |
| `--pu-slate` | `#374151` | Secondary body text, list items, descriptive labels |
| `--pu-muted` | `#6b7280` | Tertiary captions, year labels, helper notes |
| `--pu-border` | `#e5e7eb` | Crisp card borders, table dividers, tab separators |
| `--pu-bg` | `#f4f5f7` | Studio workspace canvas background (gentle, warm neutral) |
| `--pu-white` | `#ffffff` | Card surfaces, editor input backgrounds |
| `--pu-gold` | `#d99b16` | Warm solar gold accent border, brand lockups, primary CTA buttons |
| `--pu-gold-dark` | `#a16207` | High-contrast gold text on light backgrounds (WCAG AA compliant) |
| `--pu-gold-soft` | `#fdf8eb` | Live-edit toast background, active gold metric cards |
| `--pu-gold-border` | `#edd38a` | Subtle gold container borders |
| `--pu-solar-blue` | `#1d63dc` | Solar rate / monthly payment figures, solar kicker text |
| `--pu-solar-soft` | `#eff6ff` | Solar rate badge pill background |
| `--pu-solar-border`| `#bfdbfe` | Solar rate pill border |
| `--pu-green` | `#15803d` | Net savings metrics, cumulative milestones, success actions |
| `--pu-green-soft` | `#eefbf3` | Savings callout box background, verified badge pills |
| `--pu-green-border`| `#bbf7d0` | Savings container border |
| `--pu-utility` | `#c93b2b` | Utility rate alert red, utility escalation pill, danger buttons |
| `--pu-utility-soft`| `#fef2f2` | Utility comparison container background |
| `--pu-utility-border`| `#fecaca` | Utility container border |

---

## 3. Typography System

* **Font Stack:** `-apple-system, BlinkMacSystemFont, "SF Pro Display", "SF Pro Text", "Segoe UI", Roboto, Helvetica, Arial, sans-serif`
* **Numerical Tabular Alignment:** `font-variant-numeric: tabular-nums;` used for all dollar amounts, kWh totals, and annual schedule tables to guarantee columnar alignment.
* **Typographic Hierarchy:**
  * **Hero Figures (`32px – 36px`):** Weight `800`, tracking `-0.03em`, line-height `1.15`.
  * **Section Titles (`17.5px`):** Weight `700`, tracking `-0.015em`, line-height `1.3`.
  * **Body Primary (`14px – 15px`):** Weight `400` / `500`, line-height `1.5`.
  * **Category Kickers (`11.5px – 12px`):** Weight `700` / `800`, text-transform `uppercase`, tracking `0.06em`.
  * **Table Headers (`12px`):** Weight `700`, uppercase, tracking `0.04em`, color `--pu-muted`.

---

## 4. Layout Architecture & Workspace Ergonomics

### Split-Screen Studio Workspace
* **Left Inspector (`440px` sticky pane):**
  * Top 5-segment tab control (`1. Client`, `2. Utility`, `3. System`, `4. Offer`, `5. Protect`).
  * Structured form sections with subtle section dividers.
  * Form inputs with clean `#d1d5db` borders, 8px corner radius, and solar-gold focus glow (`0 0 0 3px rgba(217, 155, 22, 0.18)`).
* **Right Canvas (Fluid flex/grid):**
  * Maximum document width: `820px` centered with generous page breathing room.
  * Sticky top preview bar featuring **Live Customer Preview** badge and real-time **Updated Toast**.
  * Instant visual feedback (`puGoldFlash` animation) that pulses a gentle warm gold border whenever an inspector input triggers a recalculation.

### Client Presentation Mode (`.client-fullscreen`)
* Triggered by primary CTA: **`▶ Finalize & Present`**.
* Smoothly hides the 440px editor inspector, centering the customer document into an ultra-clean presentation layout.
* Rep actions:
  * Top bar: **`✎ Back to Editor`** (or `Esc` key) and **`✉ Email Proposal to Customer`**.
  * Footer: **`✎ Revise Proposal`** and **`✉ Email Proposal to Customer`**.

---

## 5. Core Component Specs

### 1. Branded Document Header
* Dark obsidian header (`#0a0a0c`) with 3px gold bottom border (`#d99b16`).
* Integrated Power Up Solutions logo (Sales Cake leadconnector CDN or vector mark).
* Customer name, service address, report version, date, and representative contact information cleanly aligned.

### 2. Executive Hero Comparison Card
* Side-by-side 2-column split:
  * Left: `☀️ SOLAR — FIXED` with `Goes up 0% annually` badge.
  * Right: `⚡ YOUR UTILITY — TODAY` with dynamic escalation badge (e.g., `Goes up 9.4% annually`).
* High-contrast numerical figures: `25¢ / $175` vs. `42¢ / $287`.
* 4-Column schedule table: `Year` | `☀️ Solar Rate / Mo` | `⚡ Utility Rate / Mo` | `Annual Savings`.
* Embedded **Total Cumulative Savings Over Time** milestone panel (Years 5, 10, 15, 20, 25, 30).

### 3. Side-by-Side Value Boxes
* Solar Plan vs. Doing Nothing comparison cards placed directly adjacent.
* Highlighting locked payments vs. endless escalating utility bills with zero equity and zero outage protection.
* Dedicated Early-Payoff side-by-side comparison for Propel ownership path.

### 4. 3-Step Outage Protection Cycle
* Visual 3-card progression:
  1. `☀️ Daytime Solar` (powers home directly and charges battery).
  2. `🔋 Nighttime Battery` (stored power powers essentials through the evening).
  3. `🔄 Next-Day Recharge` (morning sun replenishes storage for extended resilience).

### 5. Solar Insure SI-30 Protection Grid
* Gated exclusively upon Daybreak confirmation.
* 5 clean benefit tiles:
  * 🛡️ `$0 Deductible`
  * 🔧 `30-Year Parts & Labor`
  * 🏠 `3-Inch Roof Seal`
  * 🔋 `30-Year Battery Coverage` (SI-30 Total)
  * 🤝 `$0 Home Sale Transfer`

---

## 6. Micro-Interactions & Animation Tokens

```css
@keyframes puGoldFlash {
  0% { box-shadow: 0 0 0 4px rgba(217, 155, 22, 0.45); }
  100% { box-shadow: var(--pu-shadow); }
}

.pu-flash-updated {
  animation: puGoldFlash 0.85s ease-out;
}
```

* **Transitions:** `all 0.16s ease` on buttons, tabs, and input states.
* **Toasts:** Smooth pill status showing `Updated: [Field Name]` with background `#fdf8eb` and border `#edd38a`.
* **Print Styling:** Strict `break-inside: avoid;` on all cards and tables to ensure executive multi-page PDF output.
