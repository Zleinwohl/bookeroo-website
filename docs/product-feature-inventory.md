# Bookeroo Product Feature Inventory

> Verified against live demo at https://bookerooattempt1.netlify.app/
> Date: 2026-03-13
> This file documents actual, confirmed product functionality only.

---

## Platform Overview

Bookeroo is an operator SaaS platform for running water sports and outdoor activity businesses. The demo operator is **Jet Ski Punta Cana** (Dominican Republic), operating jet ski tours, buggies, and aqua kart experiences.

The platform covers: bookings, scheduling, staff management, customer CRM, financial reporting, waiver compliance, promotions, and equipment/resource tracking.

---

## Feature Modules

### 1. Dashboard

**What it shows:**
- Greeting with business name and current date
- 4 KPI cards: Revenue, Bookings count, Avg. Booking Value, Capacity Used — each with % change vs prior period
- **Next Stripe Payout** widget: shows payout amount, estimated arrival date, In Transit amount, Pending amount, and bank account identifier
- **Today's Manifest**: session-by-session breakdown with guest count, tickets, waiver status, balance-due indicators; color-coded status (All clear / Needs attention / Urgent)
- **Upcoming Sessions**: next 5 sessions with date, activity name, time, and capacity fill rate (e.g. "83% full")
- **Recent Bookings**: table of last 6 bookings with customer, activity, date/time, status badge, amount
- **Revenue by Activity**: bar list showing revenue breakdown per activity type

**Interactive: KPI Detail Modal**
- Clicking any KPI card opens a full overlay modal with:
  - Current metric value + % change vs prior period
  - Time range selector: Last 7 days / Last 14 days / Last 30 days / This month / Custom
  - Animated line chart showing trend over selected period
  - Peak, Low, and Average summary stats
  - "More info" button (navigates deeper)
  - ‹ / › arrows to navigate between all 4 KPI cards (1/4 → 2/4 → 3/4 → 4/4)
  - Close (×) button returns to dashboard

**Key terminology:**
- Manifest — daily operations sheet; per-session list of guests
- W / $ / ✓ — Waiver / Balance / Confirmed status indicators per guest
- KPI — Key Performance Indicators (Revenue, Bookings, Avg. Value, Capacity Used)

---

### 2. Bookings

**What it shows:**
- Total booking count (10 total in demo)
- Status filter tabs: All, Confirmed, Pending (with badge count), Cancelled
- Search field
- Table columns: ID, Customer, Activity, Date & Time, Tickets, Amount, Status
- Status badges: Confirmed (green), Pending (orange), Cancelled (red)
- Per-row action icons: View, Edit, More options
- Export button, Add Booking button

**Key terminology:**
- Booking ID — prefixed with `#` (e.g. #1037)
- Tickets — number of participants on a booking
- Pending — payment not yet fully collected
- Confirmed — booking and payment confirmed

---

### 3. Calendar

**What it shows:**
- Monthly calendar view (March 2026 shown)
- Days with bookings show a count badge ("2 bookings", "6 bookings" etc.)
- Today highlighted with filled circle
- Navigation: ← Prev, Today, Next →
- Clickable day cells

**Key terminology:**
- Calendar serves as a visual scheduling overview by date

---

### 4. Activities

**What it shows:**
- Card grid layout — 3 columns
- Per-card: Activity name, Active/Inactive status badge, colored accent line, booking count, total revenue, schedule count
- Card actions: Schedules button, Edit button
- Count shown: 5 active, 1 inactive
- Activities in the demo: Aqua Splash Pack, Aqua Kart + Buggy, Buggy & Jet Ski, Jet Ski + Aqua Kart, Buggy + Jet Ski + Aqua Karts, Single Seater Tour (inactive)
- New Activity button

**Key terminology:**
- Activity — a bookable product/experience (e.g. "Jet Ski + Aqua Kart")
- Schedules — individual time slots for an activity
- Active/Inactive — whether an activity is available for booking

---

### 5. Resources

**What it shows:**
- Equipment asset cards (6 items): Double Seater Jetski, Single Seater Jetski, Banana Boat, Speed Boat, Rescue Jetski, Safety Boat
- Per-card: name, type (Watercraft), status (Active / Maintenance / Offline), capacity, minimum, availability count
- **Resource Management** panel: assignment rules linking activities to required equipment (e.g. "When activity = Guided Jetski Tour → 1× Double Seater Jetski + 1× Staff Instructor")
- New Resource button, Add Rule button

**Key terminology:**
- Resource — a physical asset (boat, jet ski, vehicle) required to run an activity
- Availability — how many units are currently available
- Resource Management rules — automation rules that auto-assign resources when a session is scheduled

---

### 6. Staff

**What it shows:**
- KPI row: Total Staff (10), Tours Covered (7 this week), Tours Needing Staff (7)
- **Weekly schedule view**: 7-day calendar (Mon–Sun), each column shows sessions for that day with:
  - Session name and time
  - "Covered" (green) or "⚠ Needs Staff" (amber) status
  - Assigned staff names and roles
  - Assign button for unfilled roles
- **Day view** (toggle from Week): single-day panel showing all sessions for the selected date, with full session detail cards side by side
- Activity type legend/filter (Guided Jetski Tour, Sunset Jetski Tour, Open Water Rental) — individually toggleable
- Day/Week toggle + ‹/› navigation (between days in day view, between weeks in week view)
- **Staff Overview** panel: all 10 staff members with availability toggle (green = available, toggleable per staff)
- **Staff Management** rules: requirement rules per activity (e.g. "1 × Instructor required for Guided Jetski Tour")
- Roster button, New Session button (decorative in demo)

**Staff in demo:** Marcus Alvarez (Instructor), Olivia Chen (Senior Guide), Daniel Brooks (Rental Operator), Hannah (Dock Manager), Jason Patel (Tour Guide), Sophie Carter (Instructor), Ethan Park (Equipment Specialist), Maya Thompson (Guide), Ryan Cole (Instructor), Isabella Torres (Tour Guide)

**Key terminology:**
- Covered / Needs Staff — per-session staffing status
- Role — job type assigned to a session slot
- Roster — full staff list view
- Staff Management rules — automation rules requiring specific roles per activity type

---

### 7. Customers

**What it shows:**
- 22 registered customers total
- Table columns: Customer (name + ID), Total Bookings, Total Spent, Last Activity (activity name + date), Status
- Per-row action icons: View, Edit
- Add Customer button

**Key terminology:**
- Customer ID — prefixed with "Customer #" (e.g. Customer #1000)
- Last Activity — most recent booking activity type and date

---

### 8. Promotions

**What it shows:**
- 6 active promo codes
- Card grid (3 columns): promo code badge (dark pill), discount % headline, title/label, expiry date, uses count
- Per-card: copy icon, edit icon
- New Promo button

**Promo codes in demo:** JETSKI2025 (10% off), ADVENTURE10 (5% off), JETSKI15 (15% off), JET10 (10% off), JETSKI20 (20% off), JETSKI2024 (14% off)

**Key terminology:**
- Promo code — a discount code customers apply at checkout
- Uses — number of times a code has been redeemed

---

### 9. Waivers

**What it shows:**
- Badge: "1 unsigned waiver pending"
- **Recent Signatures** panel: list of recently signed waivers (customer name, activity, Signed badge, date)
- **Templates** panel: waiver template documents linked to multiple activities
- New Waiver Template button

**Templates in demo:** "Jet Ski Punta Cana Terms & Conditions" (11 activities), "Standard Activity Waiver" (5 activities)

**Key terminology:**
- Waiver — digital liability/terms document guests must sign before participating
- Unsigned — a pending waiver that hasn't been completed by the guest
- Template — a reusable waiver document applied to multiple activities

---

### 10. Settings

**Sections visible in sidebar:**
- **Business**: General (name, website, timezone, currency, language), Branding
- **Payments**: Stripe, Bank Accounts
- **Notifications**: Email, SMS
- **Advanced**: Users, API Keys

**General settings fields:** Business Name, Website, Timezone, Currency, Default Language

---

### 11. Financials — Overview

**What it shows:**
- Period filter: This Month, Last Month, This Year
- 4 KPI cards: Collected, Outstanding (with "Needs attention" badge), Projected Revenue, Avg. Booking Value
- **Interactive: Same KPI detail modal as Dashboard** — clicking any KPI card opens the drill-down chart modal
- **Next Stripe Payout** widget (same as Dashboard)
- **Cash Flow Summary**: Gross Revenue, Discount Cost, Refunds Issued, Cancellation Loss, Net Revenue
- **Outstanding Balances**: customers with unpaid amounts, showing partial payment progress bars
- **Revenue by Activity**: list with booking count and avg price per ticket
- **Discount Impact table**: per-code breakdown of discount %, uses, and estimated revenue lost
- Export button

**Key terminology:**
- Collected — cash received this period
- Outstanding — bookings with balance still owed
- Projected Revenue — from confirmed future bookings
- Net Revenue — after discounts and cancellation losses
- Discount Impact — financial cost of promo code usage

---

### 12. Financials — Statements

**What it shows:**
- 3 summary cards: YTD Revenue, Last Payout (amount + reference + date), Bank Account (name + currency)
- Statement table: State (Paid), ID, Reference number, Period, Amount, Updated date
- Per-row: View, Download (PDF) icons
- Export PDF and Export CSV buttons

**Key terminology:**
- Statement — monthly settlement record from Stripe
- Reference — unique statement ID (e.g. R2026033975)
- YTD — Year to Date

---

### 13. Financials — Tax Report

**What it shows:**
- 4 summary cards: Total Tax Collected, Total Discounts, Total Paid Incl. Tax, Tax Mode
- **Period tabs (interactive)**: Mar 2026, Feb 2026, Jan 2026, All Time — clicking changes displayed transactions and totals
- All Time view: shows all 6 historical transactions with full totals ($1,641.05 collected, -$86.95 discounts)
- Transaction count
- Per-booking tax table: ID, Status, Created, Activity Date, Item, Price, Discount, Tax Rate, Tax Amt, Tax Mode, Pay Ratio, Paid
- Totals row: Total Discounts, Total Tax, Total Collected
- Export PDF and Export CSV buttons

**Key terminology:**
- Tax Mode — how tax is applied (demo shows "Included" — tax built into prices)
- Pay Ratio — percentage of booking amount collected
- Tax Amt — calculated tax per transaction (0% in demo, tax-inclusive pricing)

---

## Cross-Module Patterns

| Pattern | Description |
|---------|-------------|
| Status badges | Consistent color system: green = Confirmed/Active/Covered, orange = Pending/Needs attention, red = Cancelled/Urgent, grey = Inactive/Offline |
| Export | CSV and/or PDF export available on Bookings, Statements, Tax Report |
| Search | Global search bar (⌘K shortcut) in top nav — searches bookings, customers, activities |
| New Booking button | Always accessible in top nav header from any screen |
| Stripe integration | Payout tracking visible on Dashboard and Financials Overview |
| Today's date | Dashboard Manifest auto-populates with current day's sessions |

---

## Data Verified in Demo

- **10 bookings** across various statuses (Confirmed, Pending, Cancelled)
- **6 activities** (5 active, 1 inactive)
- **6 equipment resources**
- **10 staff members** with roles
- **22 customers**
- **6 promo codes**
- **8 financial statements** (monthly, going back to Jul 2025)
- Stripe payouts integrated with In Transit + Pending breakdown
- Revenue by Activity tracked (total $14,799 across 5 activity types)
