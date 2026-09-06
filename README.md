# Marico FCFF DCF Valuation Model

An Excel FCFF / DCF valuation model for Marico Limited, built from embedded historical financials and explicit forecast, WACC and terminal-value assumptions.

## Open the model

Open [Marico_FCFF_DCF_Valuation_Model.xlsx](workbook/Marico_FCFF_DCF_Valuation_Model.xlsx) in desktop Excel. Read in this order:

1. `Assumptions` — forecast drivers.
2. `Forecast` and `FCFF` — operating build and free cash flow.
3. `WACC_DCF` — discount rate, enterprise value and sensitivity table.
4. `Audit` — mechanical checks.

## What was improved

- Embedded the historical-financials data so the model has no external workbook link.
- Activated the forecast assumptions: forecast margins, tax, capex and working-capital drivers now feed the model.
- Corrected after-tax cost of debt to `pre-tax debt cost × (1 − tax rate)`.
- Replaced a manual WACC plug with a formula-driven capital-structure calculation; the override is intentionally blank and labelled sensitivity-only.
- Re-sourced the valuation-date market inputs and corrected FY25 other current assets to INR 413 crore from the FY25 annual report.
- Added audit checks and removed local-path/user metadata.

## Important outputs

At the model's 31 March 2025 valuation date, the formula-driven WACC is **10.53%** and enterprise value is **INR 24,361.6 crore**. Terminal value contributes approximately **82.8%** of enterprise value; this makes the result materially sensitive to WACC and terminal-growth assumptions.

This model is for educational / portfolio purposes only. It is not investment advice, and it does not state an equity value or target price.

## Sources

- [Marico Annual Report FY25 (official PDF)](https://marico.com/investorspdf/Marico_Annual_Report_FY25.pdf)
- [Damodaran's India 2025 valuation note](https://pages.stern.nyu.edu/~adamodar/pdfiles/country/val2dayIndia2025.pdf)
- [Damodaran's 2025 country-risk-premium methodology](https://pages.stern.nyu.edu/~adamodar/pdfiles/blog/DataUpdate5for2025.pdf)

See the [assumptions and audit note](documentation/ASSUMPTIONS_AND_AUDIT.md) for the complete evidence trail and model logic.
