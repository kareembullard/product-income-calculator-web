# product-income-calculator-web

Live demo: [https://kareembullard.github.io/product-income-calculator-web/](https://kareembullard.github.io/product-income-calculator-web/)

Live "what if" calculator for the EUPM / unit-cost / income formula stack.

## What it is

A static, single-file web app version of [product-income-calculator](https://github.com/kareembullard/product-income-calculator) (the original tkinter + SQLite desktop app). This public version:

- Uses the **exact same formulas**, verified identical to the desktop app (see the assertions in that repo's `main.py` and the tests run while building this one)
- Ships with a **generic sample catalog** (Online Course, Ebook, Consulting Service, etc.) with illustrative figures instead of real financial data
- Stores saved scenarios in your browser's `localStorage` instead of a shared database
- Makes no network calls

```
unit_cost        = unit_price * unit_cost_pct   (25% ≈ "Unit Cost Low", 50% ≈ "Unit Cost High")
est_mnt_income   = unit_price * eupm
est_yr_income    = est_mnt_income * 12
unit_cost_mnt    = unit_cost * eupm
est_mnt_profit   = est_mnt_income - unit_cost_mnt
est_yr_profit    = est_mnt_profit * 12
```

## Run locally

Just open `index.html` in a browser — no build step, no server required.

## Screenshot

_(placeholder)_
