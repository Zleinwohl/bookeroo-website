# Bookeroo Marketing Website — Product Alignment Phase

## Status: IN PROGRESS
Started: 2026-03-13

---

## Audit Findings

### Current Website Weaknesses
- No real screenshots used anywhere — all ProductPanel mock components with invented data
- ProductPanel data is inaccurate (fake names, wrong revenue figures, invented "Platform Fee")
- `features.astro` is a thin grid with no visuals
- Inaccurate features listed: "Customer Booking Widget" and "Automatic confirmations" not verified
- "Drag and reassign staff" not confirmed — portal shows Assign button, not drag-and-drop
- No `/product-tour` page
- Missing industry pages: adventure-tours, jet-ski-rentals, guided-tours
- Footer links to 2 industry pages that don't exist
- Navbar has "Features" which duplicates Product content

### Screenshot Library Available
9 marketing screenshots + 21 raw screenshots in `website/public/images/product/`
All screenshots represent the **operator dashboard** (not customer-facing)

---

## Phase 1: Shared Components (must complete first)

- [x] `ScreenshotPanel.astro` — browser chrome wrapper for real product screenshots
- [x] `DashboardWidget.astro` — interactive mini dashboard (real KPI data, tab switching)
- [x] `BookingsWidget.astro` — interactive bookings list with filter tabs
- [x] `FinancialsWidget.astro` — financial summary widget

---

## Phase 2: Rewrite Core Pages

- [x] `index.astro` — Real hero screenshot, accurate copy, workflow sections with real screenshots
- [x] `product/index.astro` — Real screenshots replacing all ProductPanel mocks
- [x] `product/bookings.astro` — Real screenshot, BookingsWidget, accurate features
- [x] `product/financials.astro` — Real screenshot, FinancialsWidget, accurate features
- [x] `product/staff-scheduling.astro` — Real screenshot, accurate features
- [x] `product/operations-dashboard.astro` — Real screenshot (dashboard), accurate features
- [x] `features.astro` — Accurate feature list (remove unverified features)

---

## Phase 3: New Pages

- [x] `product-tour.astro` — Visual step-by-step product walkthrough
- [x] `industries/jet-ski-rentals.astro`
- [x] `industries/guided-tours.astro`
- [x] `industries/adventure-tours.astro`

---

## Phase 4: Navigation & Layout

- [x] `Navbar.astro` — Replace "Features" with "Product Tour", keep clean
- [x] `Footer.astro` — Fix broken industry links, add jet-ski-rentals + guided-tours

---

## Screenshot Selection

| Feature Section | Screenshot Used |
|----------------|----------------|
| Homepage hero | `dashboard-overview-marketing.png` |
| Bookings | `bookings-list-marketing.png` |
| Calendar/Scheduling | `calendar-view-marketing.png` |
| Staff management | `staff-scheduling-marketing.png` |
| Financials | `financials-overview-marketing.png` |
| Operations dashboard | `dashboard-overview-marketing.png` |
| Analytics depth (product tour) | `dashboard-kpi-modal-marketing.png` |
| Daily operations (product tour) | `staff-day-view-marketing.png` |
| Customers | `customers-list-marketing.png` |

---

## Accuracy Rules Applied

### Features REMOVED from copy (not verified in product):
- "Customer Booking Widget" (embed on website) — not in feature inventory
- "Automatic confirmation emails" — not verified
- "Drag and reassign staff" — drag-and-drop not confirmed (Assign button exists, not drag)
- "Platform Fee" line in financials mock — product shows Discount Cost / Refunds / Net Revenue

### Features CONFIRMED and used:
All from `docs/product-feature-inventory.md`

---

## Review

*To be filled after completion*
