# Bookeroo Portal — Screen Inventory

> Captured: 2026-03-13
> Demo URL: https://bookerooattempt1.netlify.app/
> Operator account: Pierre Roverd / Jet Ski Punta Cana

---

## Screenshot File Index

### Raw Screenshots (`website/public/images/product/raw/`)

| File | Section | Description |
|------|---------|-------------|
| `dashboard-overview-browser.png` | Dashboard | Full page — KPI cards, payout widget, manifest, upcoming sessions, recent bookings, revenue by activity |
| `dashboard-kpi-modal-revenue-browser.png` | Dashboard | KPI detail modal — Revenue ($18,420, +14.2%) with 30-day line chart, Peak/Low/Avg stats |
| `dashboard-kpi-modal-bookings-browser.png` | Dashboard | KPI detail modal — Bookings (47, +8.5%) with 30-day chart |
| `dashboard-kpi-modal-avg-value-browser.png` | Dashboard | KPI detail modal — Avg. Value ($391.9, +11.3%) with 30-day chart |
| `dashboard-kpi-modal-capacity-browser.png` | Dashboard | KPI detail modal — Capacity Used (78%, +4.3%) with 30-day chart |
| `bookings-list-browser.png` | Bookings | Full page — table with 10 bookings, status tabs (All/Confirmed/Pending/Cancelled), search |
| `calendar-view-browser.png` | Calendar | Full page — monthly view March 2026, days with booking counts highlighted |
| `calendar-day-detail-browser.png` | Calendar | Viewport — March 13 selected (6 bookings) |
| `activities-list-browser.png` | Activities | Full page — 6 activity cards (5 active, 1 inactive) with bookings/revenue/schedules |
| `resources-list-browser.png` | Resources | Full page — 6 equipment cards + Resource Management rules panel |
| `staff-scheduling-browser.png` | Staff | Full page — week view calendar with sessions, staff overview panel, management rules |
| `staff-day-view-browser.png` | Staff | Full page — day view (March 9) showing 2 sessions: Covered + Needs Staff, staff availability toggles |
| `customers-list-browser.png` | Customers | Full page — 8 visible customers with bookings/spend/last activity |
| `promotions-list-browser.png` | Promotions | Full page — 6 promo code cards |
| `waivers-list-browser.png` | Waivers | Full page — Recent Signatures + Templates panel |
| `settings-browser.png` | Settings | Full page — General settings with sidebar (Business, Payments, Notifications, Advanced) |
| `financials-overview-browser.png` | Financials | Full page — KPI cards, Stripe payout widget, cash flow summary, outstanding balances, revenue by activity, discount impact table |
| `financials-kpi-modal-browser.png` | Financials | KPI detail modal — Collected ($18,420, +14.2%) with line chart over Financials page |
| `financials-statements-browser.png` | Financials | Full page — YTD stats + monthly statement history table |
| `financials-tax-report-browser.png` | Financials | Full page — tax summary cards + per-booking tax breakdown (Mar 2026 default) |
| `financials-tax-all-time-browser.png` | Financials | Full page — Tax Report "All Time" period, 6 total transactions, totals row |

### Marketing Screenshots (`website/public/images/product/marketing/`)

| File | Best Use |
|------|---------|
| `dashboard-overview-marketing.png` | Hero product shot — shows full operator dashboard at a glance |
| `dashboard-kpi-modal-marketing.png` | Analytics depth — Revenue KPI drill-down modal with trend chart |
| `bookings-list-marketing.png` | Booking management — filterable table with status badges |
| `calendar-view-marketing.png` | Scheduling capability — monthly calendar with booking density |
| `activities-list-marketing.png` | Activity management — card grid with revenue and scheduling |
| `staff-scheduling-marketing.png` | Team operations — weekly scheduling grid with coverage indicators |
| `staff-day-view-marketing.png` | Daily operations — day view showing session coverage status per session |
| `customers-list-marketing.png` | CRM capability — customer list with spend and activity tracking |
| `financials-overview-marketing.png` | Revenue clarity — KPIs, payout status, cash flow breakdown |

---

## Screen Classification

### Tier 1 — Hero / Feature Flagship (highest marketing value)
- `dashboard-overview` — single best product shot; shows breadth of platform
- `dashboard-kpi-modal-revenue` — shows analytics depth; strong proof of business intelligence
- `financials-overview` — shows revenue intelligence; strong proof of business value
- `staff-scheduling` — visually rich; shows operational depth

### Tier 2 — Feature Proof Screenshots
- `bookings-list` — core workflow; all operators use this daily
- `calendar-view` — scheduling capability
- `activities-list` — product catalog management
- `customers-list` — CRM / repeat business
- `staff-day-view` — daily operational view with coverage status

### Tier 3 — Supporting Detail
- `resources-list` — equipment management
- `waivers-list` — compliance workflow
- `promotions-list` — marketing tools
- `settings` — onboarding/configuration
- `financials-statements` — financial accountability
- `financials-tax-report` / `financials-tax-all-time` — accountant-ready exports
- `financials-kpi-modal` — analytics drill-down on financial metrics

---

## Demo Implementation Notes (Verified via React Source Inspection)

The following UI elements appear interactive (cursor: pointer) but are **not implemented** in the demo — they render as decorative-only placeholders with no React onClick handlers:

- **New Booking modal** — "New Booking" button (top nav and dashboard) has no onClick; decorative button
- **Booking detail drawer** — booking table rows have no onClick in the Bookings component
- **Activity edit panel** — Activities component has no onClick handlers at all
- **Customer detail panel** — Customers component has no onClick handlers
- **Calendar day click** — Calendar component has no onClick handlers
- **Resources** — no interactivity beyond display
- **Promotions** — no interactivity
- **Waivers** — no interactivity
- **Settings sub-pages** — Branding, Stripe, Bank Accounts, Email, SMS, Users, API Keys sidebar buttons are hardcoded inactive; only General settings panel is rendered

These are confirmed non-functional via React fiber/source inspection, not automation limitations.

## Actually Interactive UI States (Verified)

| Interaction | Component | Mechanism |
|-------------|-----------|-----------|
| KPI card click → detail modal | Dashboard (`wf`) | `useState(null)` → index 0–3 opens `Rf` modal |
| KPI card click → detail modal | Financials Overview (`Rv`) | Same pattern, 4 financial KPI cards |
| Staff Day/Week toggle | Staff (`Mv`) | `useState("week")` → "day" renders single-day view |
| Tax Report period filter | Tax Report (`wv`) | `useState("Mar 2026")` → period tabs change displayed data |
| Bookings status filter tabs | Bookings (`jv`) | `useState("all")` → filters table rows |
| Staff availability toggles | Staff (`Mv`) | Per-staff boolean state array |
| Staff activity type filters | Staff (`Mv`) | Object of booleans per activity type |
