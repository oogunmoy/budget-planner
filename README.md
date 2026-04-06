# 💰 Budget Builder Pro

A comprehensive semi-monthly paycheck planner with tax estimation, 401(k) front-loading, and debt payoff analysis. Runs entirely in the browser — no server, no login, no dependencies.

**[Launch Budget Builder Pro →](https://oogunmoy.github.io/budget-planner/)**

## Features

### 💵 Income & Tax Estimation
- Annual salary input with semi-monthly paycheck breakdown (24 paychecks/year)
- 2026 federal tax brackets for all filing statuses (Single, MFJ, MFS, HoH)
- State income tax for all 50 states + DC
- FICA (Social Security + Medicare) with proper HSA exemptions
- WA Cares Fund (LTC) for Washington state
- W-4 extra withholding for RSUs/bonuses/other income

### 🏦 Payroll Deductions
Clearly separated **pre-tax** and **post-tax** deductions:

| Pre-Tax (reduces taxable income) | Post-Tax |
|---|---|
| 401(k) Employee % | After-Tax 401(k) % (Mega Backdoor Roth) |
| HSA (employee + employer) | ESPP % |
| AD&D Insurance | Legal Plan |
| Other Pre-Tax | LTD Offset |

### 🚀 401(k) Front-Load Tracker
- Paycheck-by-paycheck simulation respecting IRS limits
- **Employee Pre-Tax** — progress bar + max-out paycheck date
- **Employer Match** — 50% of your contribution, stops when you stop
- **After-Tax (Mega Backdoor Roth)** — fills remaining 415(c) space
- **Combined 415(c) stacked bar** with color-coded legend
- **Phase comparison** — take-home during front-loading vs after max-out

### 💊 HSA Max Tracker
- Your contributions + employer lump sum deposits (Jan + Jul)
- Progress bar toward annual limit
- FICA savings calculation

### 🎯 401(k) Max-Out Projection
- Table showing salary needed to max out at your current contribution % in 4, 6, 8, 10, or 12 paychecks

### 📊 Annual Cash Flow Analysis
- **Blended annual take-home** across both front-loading phases
- **Monthly budget allowance** (annual ÷ 12)
- **Phase 1 vs Phase 2** income comparison
- **Savings buffer needed** to survive lean front-loading months
- **12-month cash flow grid** — color-coded surplus/deficit per month

### 💳 Debt Payoff Planner
- Multiple debt types: Credit Card, Student Loan, Car Loan, Personal Loan, Legal Fees, Medical, Other
- **Target payoff date** per debt with required monthly payment calculation
- **Avalanche vs Snowball** strategy comparison
- Uses your annual surplus from the cash flow analysis
- Feasibility check — can your surplus cover the plan?

### 📤 Excel Export
- Styled spreadsheet with ExcelJS (colors, borders, formatting)
- **Left side:** Paycheck waterfall with running balance
- **Right side:** Contribution tracker, front-load timeline, monthly cash flow, debt analysis
- Upload an existing `.xlsx` to append a new sheet

### ⚙️ IRS Limits by Year
- Year dropdown with built-in limits for 2024, 2025, 2026
- Auto-fetches `limits.json` for future updates
- Warning message for years not yet announced

## Tech Stack

- **Single HTML file** — zero build tools, zero dependencies
- **Vanilla JS** — no frameworks
- **ExcelJS** (CDN) — for styled Excel export
- **GitHub Pages** — free hosting

## Updating IRS Limits

When the IRS announces new limits (typically October), add a line to `limits.json`:

```json
{
  "2024": { "emp401k": 23000, "total401k": 69000, "hsa": 4150, "ssWageBase": 168600 },
  "2025": { "emp401k": 23500, "total401k": 70000, "hsa": 4300, "ssWageBase": 176100 },
  "2026": { "emp401k": 24500, "total401k": 72000, "hsa": 4400, "ssWageBase": 184500 },
  "2027": { "emp401k": 25000, "total401k": 74000, "hsa": 4500, "ssWageBase": 190000 }
}
```

Push to GitHub — the app fetches it on load.

## License

Personal use.
