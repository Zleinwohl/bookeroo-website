# Bookeroo Portal — Navigation & Architecture Reference

> Verified against live demo at https://bookerooattempt1.netlify.app/
> Date: 2026-03-13

---

## Top-Level Layout

The portal uses a fixed two-panel layout:

```
┌─────────────────┬──────────────────────────────────────────┐
│   Left Sidebar  │              Main Content Area            │
│   (nav + user)  │  (breadcrumb + topbar + page content)    │
└─────────────────┴──────────────────────────────────────────┘
```

**Sidebar** (~200px wide):
- Bookeroo logo at top
- Navigation groups (see below)
- User profile at bottom (name, role, business name)
- Collapse button (‹)

**Top Bar** (per-page header strip):
- Breadcrumb: `[Business Name] / [Page Name]`
- Global search field (placeholder: "Search bookings, customers, activities…", shortcut: ⌘K)
- Date period toggle: Today / Week / Month
- Notification bell icon
- `+ New Booking` button (always visible, top-right)

---

## Navigation Structure

### OPERATIONS
| Item | Badge | Notes |
|------|-------|-------|
| Dashboard | — | Default landing page |
| Bookings | Count (e.g. 2) | Badge shows pending/actionable bookings |
| Calendar | — | Monthly view, navigable |

### MANAGE
| Item | Badge | Notes |
|------|-------|-------|
| Activities | — | Activity catalog management |
| Resources | — | Equipment/asset management |
| Staff | — | Scheduling + staff roster |

### MARKETING
| Item | Badge | Notes |
|------|-------|-------|
| Customers | — | Customer CRM list |
| Promotions | — | Promo code management |

### (Ungrouped)
| Item | Badge | Notes |
|------|-------|-------|
| Waivers | Count (e.g. 1) | Badge shows unsigned/pending waivers |
| Settings | — | Business configuration |

### FINANCE
| Item | Expandable | Notes |
|------|-----------|-------|
| Financials ▾ | Yes | Expands to 3 sub-pages |
| → Overview | — | Revenue KPIs, payout, cash flow |
| → Statements | — | Monthly Stripe settlement records |
| → Tax Report | — | Per-booking tax breakdown |

---

## Page Hierarchy

```
/ (root)
├── Dashboard
├── Bookings
│   └── [Booking detail — drawer/modal]
├── Calendar
├── Activities
│   └── [Activity edit — panel/modal]
├── Resources
├── Staff
├── Customers
│   └── [Customer detail — drawer/modal]
├── Promotions
├── Waivers
├── Settings
│   ├── General (default)
│   ├── Branding
│   ├── Stripe
│   ├── Bank Accounts
│   ├── Email
│   ├── SMS
│   ├── Users
│   └── API Keys
└── Financials
    ├── Overview (default)
    ├── Statements
    └── Tax Report
```

---

## UI Component Patterns

### Status Badges
| Color | Meaning | Used In |
|-------|---------|---------|
| Green (sage) | Confirmed / Active / Covered / Signed | Bookings, Activities, Staff, Waivers |
| Orange (amber) | Pending / Needs attention / Needs Staff | Bookings, Dashboard, Staff |
| Red | Cancelled / Urgent | Bookings, Dashboard manifest |
| Grey | Inactive / Offline | Activities, Resources |
| Yellow/amber outline | Maintenance | Resources |

### Navigation Badges
- Circular badge on nav items indicates count of actionable items
- Bookings badge = pending booking count
- Waivers badge = unsigned waiver count

### Table Pattern (Bookings, Customers, Tax Report, Statements)
- Column headers with sort affordance
- Status badge column
- Action icon column (view eye, edit pencil, more options ⋯)
- Row click appears to open a detail drawer (automation limitation prevented capture)

### Card Grid Pattern (Activities, Promotions, Resources)
- 3-column grid
- Cards have: title, status badge, metrics row, action buttons
- Activities cards have colored accent border
- Promotions cards have dark promo code pill

### KPI Detail Modal Pattern (Dashboard + Financials)
- Clicking any KPI card opens a full-screen modal overlay (component: `Rf`)
- Modal shows: metric name, current value + % change, time range selector (Last 7/14/30 days, This month, Custom), line chart, Peak/Low/Avg stats, "More info" button
- Navigable 1/4 → 2/4 → 3/4 → 4/4 with ‹ › arrows
- Dashboard modals: Revenue, Bookings, Avg. Value, Capacity Used
- Financials modals: Collected, Outstanding, Projected Revenue, Avg. Booking Value
- Close via × button or onClose callback (dispatches null to parent state)

### Staff Day/Week View Toggle
- Week view: 7-column calendar with sessions per day
- Day view: single date panel showing all sessions for that day, with Covered/Needs Staff status cards
- Each session card shows: activity name, time, status badge, assigned staff, Assign button
- Toggle via Day/Week buttons in top-right of scheduling area
- ‹/› buttons navigate between days (day view) or weeks (week view)

### Decorative Buttons (Not Implemented in Demo)
These elements have `cursor: pointer` CSS but NO React onClick handlers — confirmed via source inspection:
- "New Booking" buttons (top nav + dashboard content)
- Booking table rows (no detail drawer)
- Activity card Edit/Schedules buttons
- Customer table rows (no detail drawer)
- Calendar day cells
- Resource, Promotion, Waiver table rows
- Settings sub-nav items (Branding, Stripe, Bank Accounts, Email, SMS, Users, API Keys)

---

## Global Interactions

| Action | Location | Notes |
|--------|----------|-------|
| Global search | Top bar | ⌘K shortcut; searches bookings, customers, activities |
| New Booking | Top bar (always) + Dashboard content | Quick access to booking creation |
| Period filter | Top bar | Today / Week / Month — affects time-scoped views |
| Export | Per-page | CSV/PDF where applicable (Bookings, Statements, Tax Report, Manifest) |
| Print | Dashboard Manifest | Prints today's session manifest |

---

## Business Context (Demo Operator)

| Field | Value |
|-------|-------|
| Business Name | Jet Ski Punta Cana |
| Short Name | Jet Ski PC |
| Location | Punta Cana, Dominican Republic |
| Timezone | UTC-4 (Atlantic Standard Time) |
| Currency | USD |
| Admin User | Pierre Roverd |
| Bank | Banco Popular Dominicano (account: BPDODOSX) |
| Stripe | Integrated (payout tracking active) |
| Activities | Jet ski, buggy, aqua kart combinations |

---

## React App Characteristics

- Single-page application (SPA) — no URL routing observed
- React synthetic events — modals/drawers require React event dispatch
- CSS variables — design tokens (`--sage`, `--amber`, `--ink-1` through `--ink-5`)
- Deployed on Netlify
- Responsive layout (sidebar collapses)
