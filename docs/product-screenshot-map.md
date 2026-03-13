# Bookeroo Product Screenshot Map

> Stable lookup table for marketing website image references.
> Base path: `/images/product/`

---

## Usage Guide

Reference images in Astro components as:
```
/images/product/raw/[filename]
/images/product/marketing/[filename]
```

---

## Marketing Screenshots (Preferred for Website)

| Key | File Path | Dimensions | Best For |
|-----|-----------|------------|---------|
| `dashboard-hero` | `/images/product/marketing/dashboard-overview-marketing.png` | 1249×1277 | Homepage hero, feature intro section |
| `dashboard-kpi-modal` | `/images/product/marketing/dashboard-kpi-modal-marketing.png` | 1249×554 | Analytics depth — KPI drill-down with trend chart |
| `bookings-list` | `/images/product/marketing/bookings-list-marketing.png` | 1249×1277 | Bookings feature section |
| `calendar` | `/images/product/marketing/calendar-view-marketing.png` | 1249×1277 | Scheduling feature section |
| `activities` | `/images/product/marketing/activities-list-marketing.png` | 1249×1277 | Activity management feature |
| `staff` | `/images/product/marketing/staff-scheduling-marketing.png` | 1249×1277 | Team management — weekly view |
| `staff-day-view` | `/images/product/marketing/staff-day-view-marketing.png` | 1249×1054 | Daily operations — session coverage status |
| `customers` | `/images/product/marketing/customers-list-marketing.png` | 1249×1277 | CRM / customer feature |
| `financials` | `/images/product/marketing/financials-overview-marketing.png` | 1249×1277 | Financials / revenue feature |

---

## Raw Screenshots (Full-Page Reference)

| Key | File Path | Notes |
|-----|-----------|-------|
| `dashboard-full` | `/images/product/raw/dashboard-overview-browser.png` | Full scrollable page |
| `dashboard-kpi-revenue` | `/images/product/raw/dashboard-kpi-modal-revenue-browser.png` | Revenue KPI detail modal with chart |
| `dashboard-kpi-bookings` | `/images/product/raw/dashboard-kpi-modal-bookings-browser.png` | Bookings KPI detail modal with chart |
| `dashboard-kpi-avg-value` | `/images/product/raw/dashboard-kpi-modal-avg-value-browser.png` | Avg. Value KPI detail modal with chart |
| `dashboard-kpi-capacity` | `/images/product/raw/dashboard-kpi-modal-capacity-browser.png` | Capacity Used KPI detail modal with chart |
| `bookings-full` | `/images/product/raw/bookings-list-browser.png` | Complete bookings table |
| `calendar-full` | `/images/product/raw/calendar-view-browser.png` | Monthly calendar |
| `activities-full` | `/images/product/raw/activities-list-browser.png` | Full activity grid |
| `resources-full` | `/images/product/raw/resources-list-browser.png` | Equipment + rules panel |
| `staff-full` | `/images/product/raw/staff-scheduling-browser.png` | Full staff scheduling page — week view |
| `staff-day-view-full` | `/images/product/raw/staff-day-view-browser.png` | Staff day view — single day sessions with coverage |
| `customers-full` | `/images/product/raw/customers-list-browser.png` | Customer table |
| `promotions-full` | `/images/product/raw/promotions-list-browser.png` | Promo code grid |
| `waivers-full` | `/images/product/raw/waivers-list-browser.png` | Waivers + templates |
| `settings-full` | `/images/product/raw/settings-browser.png` | Settings panel |
| `financials-overview-full` | `/images/product/raw/financials-overview-browser.png` | Full financials overview |
| `financials-kpi-modal` | `/images/product/raw/financials-kpi-modal-browser.png` | Financials KPI modal — Collected metric with trend chart |
| `financials-statements-full` | `/images/product/raw/financials-statements-browser.png` | Statement history |
| `financials-tax-full` | `/images/product/raw/financials-tax-report-browser.png` | Tax report — Mar 2026 default |
| `financials-tax-all-time` | `/images/product/raw/financials-tax-all-time-browser.png` | Tax report — All Time, 6 transactions, full history |

---

## Recommended Pairings for Feature Sections

| Feature Section | Primary Image | Secondary Image |
|----------------|---------------|----------------|
| Dashboard / Operations | `dashboard-hero` | `dashboard-full` |
| Booking Management | `bookings-list` | `bookings-full` |
| Scheduling | `calendar` | `staff` |
| Activity Setup | `activities` | `activities-full` |
| Financial Reporting | `financials` | `financials-statements-full` |
| Customer Management | `customers` | — |
| Team Management | `staff` | `staff-full` |
| Waiver Compliance | — | `waivers-full` |
| Promotions | — | `promotions-full` |
