# product-income-calculator-web

Live: [https://kareembullard.github.io/product-income-calculator-web/](https://kareembullard.github.io/product-income-calculator-web/)

My real product & income catalog, plus a live "what if" calculator for the EUPM / unit-cost / income formula stack.

## What it is

A static, single-file web app version of [product-income-calculator](https://github.com/kareembullard/product-income-calculator) (the original tkinter + SQLite desktop app). This public version:

- Shows my **actual product catalog** — 120 products exported from my Airtable workspace, with real unit prices and income projections, published deliberately
- Sortable/filterable table (by Area, Type, Income Type) plus a top-10-by-yearly-income bar chart (plain canvas, no chart library)
- **The whole catalog is a live calculator**: click directly on any Unit Price, EUPM, or Cost % cell to edit it in place (Enter or click away to save, Escape to cancel) — the row, the stats at the top, and the chart all recalculate immediately using the same formula stack. "Reset" reverts a single row; "Reset all edits" in the toolbar reverts everything
- **Bulk edit via CSV**: export the table, edit Unit Price/EUPM/Cost % in a spreadsheet, then import it back — rows are matched by the ID column (or by product name as a fallback) and only the columns you filled in get applied, so partial edits work too
- What-if calculator uses the **exact same formulas** as the desktop app, and can load any real (or edited) product from the catalog as a starting point
- **Export your reports**: download the current filtered/sorted catalog table as CSV, download all saved what-if scenarios as CSV, or export a full JSON backup (catalog edits + scenarios) that can be re-imported later
- Saved scenarios and catalog edits stay in your browser's `localStorage` — nothing is sent anywhere
- Makes no network calls

```
unit_cost        = unit_price * unit_cost_pct   (25% is my standard low-end estimate across the catalog)
est_mnt_income   = unit_price * eupm
est_yr_income    = est_mnt_income * 12
unit_cost_mnt    = unit_cost * eupm
est_mnt_profit   = est_mnt_income - unit_cost_mnt
est_yr_profit    = est_mnt_profit * 12
```

## Where the data comes from

`data/products.json` is the export from the "Inventory 081026" Airtable base, Products and Services table — product name, type, area, unit price, EUPM/AUPM, estimated monthly/yearly income, unit cost range, and income type (Passive/Active). The `PRODUCTS` array in `index.html` is generated directly from this file.

## Run locally

Just open `index.html` in a browser — no build step, no server required.

## Screenshot

_(placeholder)_
