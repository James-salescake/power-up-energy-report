# Power Up Solutions — Personalized Energy Report Studio

A high-performance, executive-grade proposal and presentation studio for residential solar, battery storage, and energy agreements. Built with a bespoke design system, deterministic calculation engine, and standalone locked customer export capabilities.

---

## 🌟 Key Features

1. **Deterministic Financial & Energy Calculation Engine**
   - True side-by-side comparison between Solar and Utility rates across 25 or 30-year terms.
   - Modeled utility rate escalations (0% flat, 3.4%, 6.0%, 9.4%, and custom year-by-year schedules).
   - Accurate true-up settlement buffers, minimum grid connection charges, and excess export valuation.
   - Propel (Fixed Payment / Path to Ownership / Early Payoff) and Clean Energy Agreement (PPA-style) financing models.

2. **Split Studio Workspace & Customer Presentation Mode**
   - **Studio Editor (Left)**: Real-time tabbed editor for Client, Utility Baseline, System Sizing, Financing Offer, and Solar Insure Warranty enrollment.
   - **Live Customer Canvas (Right)**: Synchronized live document with instant visual update flash feedback.
   - **Presentation Mode**: Fullscreen, distraction-free view tailored for rep-led presentations with customers in person or over Zoom.
   - Keyboard navigation including `Esc` key to exit presentation mode.

3. **Standalone Locked Customer HTML & Backup Export**
   - One-click export bundles all precomputed scenarios into a self-contained, offline-compatible HTML proposal.
   - Built-in `mailto:` actions for customer acceptance ("Ready to Move Forward") and revision requests with pre-filled details.
   - JSON export and restore capabilities for effortless state recovery and proposal revision tracking.

4. **Image & Logo Transparency Support**
   - In-browser image compression preserving PNG and SVG transparency for clean brand integration.
   - Multi-photo attachment support mapped to specific sections (Solar Design, Battery Setup, Financing, Supporting Documentation).

5. **Print & PDF Optimized**
   - Clean `@media print` styling with page-break-inside protection to prevent awkward page splits on quotes and tables.

---

## 🚀 Quick Start

This application is completely self-contained with **zero external dependencies** and no build step required.

1. Clone or open the repository:
   ```bash
   cd power-up-energy-report
   ```
2. Open `index.html` in any modern web browser:
   - On macOS: `open index.html`
   - Or serve with any static server:
     ```bash
     npx serve .
     # or
     python3 -m http.server 8000
     ```

---

## 📁 Repository Structure

```
power-up-energy-report/
├── index.html        # Complete application (Studio, Engine, & Customer Canvas)
├── README.md         # Documentation & guide
└── .gitignore        # Git ignore rules
```

---

## 🛠️ Code Inspection & Improvements Applied

- **Fixed Missing CSS Variable**: Defined `--pu-gold-dark` (`#a16207`), restoring proper contrast for status toasts and battery rule labels.
- **Fixed `0%` Degradation Parsing**: Replaced falsy `|| 0.5` fallback with `isNaN(degParsed) ? 0.5 : degParsed`, allowing true 0% degradation testing.
- **Fixed Alpha/Transparency Image Handling**: Resolved issue where canvas JPEG conversion rendered transparent PNG/SVG logos with black backgrounds.
- **Modern Clipboard API**: Upgraded summary copy feature to `navigator.clipboard.writeText` with graceful `execCommand` fallback.
- **Enhanced Accessibility**: Added ARIA tabs, roles, labels, and keyboard listeners (`Enter`/`Space` on file input labels, `Esc` to exit presentation mode).
- **Dual Milestone Savings Metric**: Added both direct solar savings and net out-of-pocket savings metrics to calculation rows.
- **CEA Auto-Calculator**: Added quick action to calculate monthly payments directly from production and per-kWh rates.
