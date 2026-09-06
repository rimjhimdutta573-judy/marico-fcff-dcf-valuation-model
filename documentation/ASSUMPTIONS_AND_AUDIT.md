# Assumptions, valuation logic and audit

## Valuation date and market inputs

The model uses **31 March 2025** as its valuation date. Because the market was closed that weekend, the equity-value input uses the preceding trading day, 28 March 2025.

| Input | Value | Logic / source |
| --- | ---: | --- |
| Risk-free rate | 6.582% | India 10-year government-bond yield at 28 March 2025, reported by Reuters. |
| Levered beta | 0.4419x | Analyst calculation: covariance of weekly Marico and NIFTY 50 adjusted returns divided by NIFTY 50 weekly-return variance; 261 weekly observations ending 30 March 2025. |
| India equity-risk premium | 9.00% | Damodaran's 2025 India valuation note: mature-market ERP plus India country risk premium. |
| Pre-tax cost of debt | 5.70% | Model assumption retained from the original model and made visible. |
| Tax rate | 22.75% | Linked from `Assumptions`; used to calculate after-tax cost of debt. |
| Market value of equity | INR 84,421.1 crore | 28 March 2025 closing price of INR 651.65 × 129.5498 crore shares outstanding. |
| Gross debt | INR 379 crore | FY25 historical financials embedded in `Historical_Data`. |
| Terminal growth | 4.00% | Explicit model assumption; sensitivity table shows 3.0%–5.0%. |

The market-data inputs are reproducible estimates, not claims of company guidance. The annual report is the primary source for historical financial statements, shares outstanding and the INR 651.65 31 March 2025 share-price reference. The FY25 balance-sheet “other current assets” value in the embedded history is INR 413 crore, matching the annual report.

Market-input links: [Reuters yield report](https://economictimes.indiatimes.com/markets/bonds/india-10-year-bond-yield-sees-biggest-drop-in-half-a-decade-on-foreign-flows-rate-cut/articleshow/119653311.cms), [Marico FY25 annual report](https://marico.com/investorspdf/Marico_Annual_Report_FY25.pdf), [Marico adjusted-price history](https://finance.yahoo.com/quote/MARICO.NS/history/) and [NIFTY 50 adjusted-price history](https://finance.yahoo.com/quote/%5ENSEI/history/). The last two links support reproduction of the beta calculation; they are market-data references, not company disclosures.

## Core equations

`Cost of equity = risk-free rate + beta × India equity-risk premium`

`After-tax cost of debt = pre-tax cost of debt × (1 − tax rate)`

`WACC = equity weight × cost of equity + debt weight × after-tax cost of debt`

`Terminal value = FCFF_(n+1) / (WACC − terminal growth)`

The WACC override cell is blank by default. It exists solely to run controlled sensitivity cases; a hardcoded WACC is not used in the base case.

## Audit results

| Check | Result |
| --- | --- |
| Historical financials available inside workbook | PASS |
| External workbook links | None |
| Assumption cells feed forecast formulas | PASS |
| After-tax debt cost formula | PASS |
| WACC formula with blank base-case override | PASS |
| Audit-sheet mechanical checks | 10 / 10 PASS |
| VBA/macros | None |
| Local user/path metadata in distributable | Removed |

## How to defend the result

The enterprise value is a DCF estimate, not an observed price. It changes because the repaired model now lets operating assumptions flow through FCFF and uses a formula-driven, market-date-aligned discount rate. The terminal-value concentration is high, so the WACC and growth sensitivity table must be shown whenever the valuation is discussed.

No proprietary source files are included in this repository. Recheck public market data and annual-report disclosures before updating the valuation date.
