# Marico FCFF DCF Valuation Model

An Excel FCFF / DCF valuation model for Marico Limited. The model links three historical years (FY23A-FY25A) to three forecast years (FY26E-FY28E), then converts operating assumptions into free cash flow and enterprise value.

## What this project demonstrates

- Historical financial-statement integration, forecast building and working-capital modelling.
- A formula-driven flow from revenue to EBITDA, EBIT, NOPAT, capital expenditure, change in operating net working capital and FCFF.
- CAPM cost of equity, after-tax cost of debt and market-value capital weights to calculate WACC.
- Terminal-value calculation and a 5 x 5 WACC-versus-terminal-growth enterprise-value sensitivity table.
- Mechanical audit checks for formula links, historical tie-outs, FCFF reconciliation and valuation logic.

## Review the model in one minute

Open [Marico_FCFF_DCF_Valuation_Model.xlsx](workbook/Marico_FCFF_DCF_Valuation_Model.xlsx) in desktop Excel, then follow this path:

1. **`Assumptions`** - forecast growth, margins, tax, capex and operating-working-capital drivers.
2. **`Forecast`** and **`FCFF`** - trace the operating build to free cash flow.
3. **`WACC_DCF`** - review CAPM, capital weights, terminal value and the 5 x 5 sensitivity table.
4. **`Audit`** - inspect the ten mechanical checks.
5. **`Historical_Data`** and **`Source_Notes`** - inspect the embedded inputs and source trail.

## Base case and key limitation

At the model's 31 March 2025 valuation date, the base-case WACC is **10.53%** and enterprise value is **INR 24,361.6 crore**. Terminal value contributes approximately **82.8%** of enterprise value. That concentration makes the conclusion particularly sensitive to WACC and terminal-growth assumptions, which is why the sensitivity table should accompany any discussion of the output.

Forecast assumptions are model inputs, not company guidance. This is an educational portfolio model, not investment advice; it does not present an equity value or target price.

## Model integrity

| Control | Result |
| --- | --- |
| Historical period | FY23A-FY25A, embedded in the workbook |
| Forecast period | FY26E-FY28E |
| WACC | Formula-driven; base-case override is blank |
| Sensitivity table | Complete 5 x 5 WACC / terminal-growth grid |
| Audit checks | 10 / 10 PASS |
| External workbook links and VBA/macros | None |

## Sources

- [Marico Annual Report FY25 (official PDF)](https://marico.com/investorspdf/Marico_Annual_Report_FY25.pdf)
- [Damodaran's India 2025 valuation note](https://pages.stern.nyu.edu/~adamodar/pdfiles/country/val2dayIndia2025.pdf)
- [Damodaran's 2025 country-risk-premium methodology](https://pages.stern.nyu.edu/~adamodar/pdfiles/blog/DataUpdate5for2025.pdf)

See the [assumptions and audit note](documentation/ASSUMPTIONS_AND_AUDIT.md) for the evidence trail, formulas and methodology.
