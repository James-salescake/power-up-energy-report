# Power Up Solutions — Personalized Energy Report Studio

A high-performance, executive-grade proposal and presentation studio for residential solar, battery storage, and energy agreements. Built with a bespoke design system, deterministic calculation engine, and standalone locked customer export capabilities.

---

## 🚀 Sales Cake (GoHighLevel) Funnel Builder Integration

This application is tailored for seamless integration inside **Sales Cake** (or any white-label GoHighLevel instance):

### 1. Using Sales Cake Media Storage for Logos
Instead of uploading a local file each time, host your branding directly in Sales Cake:
1. In Sales Cake, go to **Sites** (or **Marketing**) → **Media Storage**.
2. Upload your company logo (`.png` with transparency or `.svg` recommended).
3. Click the uploaded file → **Copy Link**.
4. In the studio under **1. Client → Brand Logo**, paste the link into the **Logo Image URL** field.
5. The logo will immediately appear in the Studio topbar, the live canvas, and any exported customer reports.

### 2. Embedding in Sales Cake Funnel Builder
You can embed this tool into a Sales Cake Funnel page using either of these two methods:

#### Method A: Direct Custom HTML/JS Element (Recommended for internal reps)
1. In Sales Cake Funnel Builder, create a new step/page (e.g., `/energy-report-studio`).
2. Add a **Full Width Section** and set section padding (Top/Bottom/Left/Right) to `0px`.
3. Add a **1 Column Row**, then add a **Custom HTML/JS** element.
4. Open the Custom Code editor and paste the full contents of `index.html`.
5. Save and Publish the page.

#### Method B: Embedded via iFrame
If hosting the repository via GitHub Pages, Vercel, or custom subdomain:
1. In Sales Cake Funnel Builder, add a **Custom HTML/JS** element:
   ```html
   <iframe src="https://your-domain.com/index.html" 
           style="width:100%; height:100vh; border:none; display:block;" 
           allow="clipboard-write"></iframe>
   ```

---

## ⚡ Auto-Prefill with Sales Cake / GHL Merge Tags (URL Query Parameters)

You can automatically prefill customer and rep information by passing query parameters in the funnel URL or automated booking links.

### Example URL:
```text
https://app.salescake.com/energy-report?name={{contact.name}}&email={{contact.email}}&address={{contact.address1}}&bill={{contact.electric_bill}}&rep={{user.name}}&rep_email={{user.email}}&phone={{user.phone}}&logo={{custom_values.company_logo}}
```

### Supported Parameters:
| URL Parameter | Field Populated | Example GHL Merge Tag |
|---|---|---|
| `name` or `customer_name` | Customer Full Name | `{{contact.name}}` |
| `email` or `customer_email` | Customer Email | `{{contact.email}}` |
| `address` or `customer_address` | Service Address / City | `{{contact.address1}}` |
| `bill` or `monthly_bill` | Current Average Electric Bill ($/mo) | `{{contact.electric_bill}}` |
| `kwh` or `usage` | Annual Consumption (kWh) | `{{contact.annual_kwh}}` |
| `system_size` or `kw` | Solar System Size (kW DC) | `{{contact.system_size}}` |
| `rep` or `rep_name` | Representative Name | `{{user.name}}` |
| `rep_email` | Representative Email | `{{user.email}}` |
| `phone` or `rep_phone` | Representative Phone | `{{user.phone}}` |
| `logo` or `logo_url` | Brand Logo Image URL | `{{custom_values.company_logo}}` |
| `utility` or `provider` | Utility Preset (`PGE`, `SCE`, `IID`) | `{{contact.utility_provider}}` |
| `offer` | Offer Type (`propel` or `cea`) | `propel` |

---

## 🌟 Key Application Features

1. **Deterministic Financial & Energy Calculation Engine**
   - True side-by-side comparison between Solar and Utility rates across 25 or 30-year terms.
   - Modeled utility rate escalations (0% flat, 3.4%, 6.0%, 9.4%, and custom schedules).
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

4. **Print & PDF Optimized**
   - Clean `@media print` styling with page-break-inside protection to prevent awkward page splits on quotes and tables.

---

## 📁 Repository Structure

```
power-up-energy-report/
├── index.html        # Complete application (Studio, Engine, & Customer Canvas)
├── README.md         # Documentation & Sales Cake / GHL integration guide
└── .gitignore        # Git ignore rules
```
