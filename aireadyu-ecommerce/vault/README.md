# Vault

This directory contains the **vault schema** — the blueprint for the 11-domain folder structure.

The full vault — with pre-built folders, synthetic data, and ready-to-use structure — is included in the **AI Ready U: E-Commerce pack**.

**[Get the full vault + skills → $29](https://fruverse.gumroad.com/l/aireadyu-ecommerce)**

After purchase, extract to `~/Documents/AIReadyU-Ecommerce/`. The agents already know to look there.

```
~/Documents/AIReadyU-Ecommerce/
├── skills/              <- 12 tool skills (gmail, calendar, drive, etc.)
└── vault/               <- 11 store domains with synthetic data
    ├── inventory/
    │   ├── 00_current/
    │   └── 01_prior/YYYY/
    ├── listings/
    ├── customers/
    └── ...
```

## 11 Store Domains

| Domain | Folder | What Goes Here |
|--------|--------|---------------|
| Inventory | `inventory/` | Stock records, SKU catalog, reorder logs, warehouse docs, inventory audits |
| Listings | `listings/` | Product listings, copy drafts, image assets, keyword research, listing audits |
| Customers | `customers/` | Customer records, support tickets, review responses, returns log, loyalty data |
| Orders | `orders/` | Order reports, fulfillment logs, SLA tracking, exception reports, 3PL docs |
| Marketing | `marketing/` | Ad campaigns, email sequences, social calendar, influencer contracts, promo plans |
| Finance | `finance/` | P&L statements, tax filings, chargeback records, revenue reports, vendor invoices |
| Vendors | `vendors/` | Supplier contracts, purchase orders, RFQ docs, vendor evaluations, payment schedules |
| Shipping | `shipping/` | Carrier contracts, shipping rate cards, delivery reports, claims records |
| Analytics | `analytics/` | Performance dashboards, conversion reports, LTV analysis, channel attribution data |
| Tech | `tech/` | Platform documentation, app inventory, automation specs, integration records |
| Admin | `admin/` | Business licenses, compliance filings, calendar records, administrative documents |
