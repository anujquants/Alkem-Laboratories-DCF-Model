# Alkem-Laboratories-DCF-Model
Discounted Cash Flow (DCF) Valuation Model for Alkem Laboratories built using financial modeling techniques including revenue forecasting, cost assumptions, and WACC-based valuation.
# Alkem Laboratories Limited — DCF Valuation Model

> A comprehensive Discounted Cash Flow (DCF) and Comparable Company Analysis (Comps) model built for **Alkem Laboratories Limited** (NSE: ALKEM), one of India's leading pharmaceutical companies.

---

## 📌 Overview

This financial model was built to estimate the **intrinsic value** of Alkem Laboratories using a bottom-up DCF approach, cross-validated with a Comparable Company (Comps) valuation. The model incorporates 5 years of historical financials (FY2021–FY2025), a 5-year forecast horizon (FY2026–FY2030), and a rigorous WACC estimation using regression-derived beta.

---

## 🗂️ Model Structure

The workbook is organized into **9 sheets**, each serving a specific analytical purpose:

| Sheet | Description |
|---|---|
| `Template` | Formatting guide and style conventions used throughout the model |
| `Historicals` | Raw financial data — Income Statement, Balance Sheet, and Cash Flows (FY2021–FY2025) |
| `Model` | Core DCF model with ratio-driven projections, FCFF build-up, and valuation output |
| `Scenarios` | Base / Bull / Bear case revenue growth assumptions with scenario toggle |
| `Comps_Data` | Raw peer data — market cap, EV, EBITDA, P/E, levered/unlevered betas for 7 Indian pharma companies |
| `Comps` | Comparable company valuation table with EV/Sales, EV/EBITDA, and P/E multiples |
| `WACC` | Weighted Average Cost of Capital computation — cost of equity via CAPM, cost of debt, and capital structure weights |
| `Beta` | OLS regression of Alkem vs. Nifty 50 daily returns to derive company-specific levered beta |
| `Market Data` | Nifty 50 historical prices used to compute a 10-year annualized market return (Rm) |

---

## 🔢 Key Assumptions

### Revenue Growth (Base Case)
| Year | Growth Rate |
|---|---|
| FY2026 | 10.0% |
| FY2027 | 8.9% |
| FY2028 | 7.9% |
| FY2029 | 7.0% |
| FY2030 | 6.3% |

> Base Case uses the 4-year CAGR of historical revenue. Bull Case uses peak historical growth (19.96%); Bear Case uses India's GDP growth rate (~7.4%).

### Margin & Working Capital Drivers
All P&L line items are modeled as a **percentage of revenue**, and working capital is driven by **days-based assumptions** (DSO, DIO, DPO) — both calibrated to 5-year historical averages.

### WACC
- **Beta**: Estimated via OLS regression of Alkem daily returns vs. Nifty 50 (β = 0.49); cross-checked against a peer median unlevered beta of 0.48 (re-levered for Alkem's capital structure)
- **Risk-Free Rate**: Based on Indian Government 10-year bond yield
- **Equity Risk Premium**: 10-year Nifty 50 annualized return (~13.7%)
- **Cost of Debt**: Derived from historical interest expense as % of total debt

---

## 🏢 Peer Group (Comparable Companies)

The following Indian pharmaceutical companies were used in the comps analysis:

- Sun Pharmaceutical Industries
- Divi's Laboratories
- Torrent Pharmaceuticals
- Dr. Reddy's Laboratories
- Cipla
- Lupin
- Zydus Lifesciences
- Alkem Laboratories *(subject company)*

---

## 📊 Valuation Output

The model produces an implied share price range across three methodologies:

1. **DCF Valuation** — FCFF discounted at WACC with terminal value (Gordon Growth Model)
2. **EV/EBITDA Comps** — Peer median/average applied to projected EBITDA
3. **P/E Comps** — Peer median/average applied to projected EPS

Each methodology is run across Base, Bull, and Bear scenarios.

---

## 🛠️ How to Use

### Prerequisites
- Microsoft Excel 2016 or later (or Google Sheets with minor formatting adjustments)

### Step-by-Step Guide

**Step 1 — Open the model**
Download `Alkem_Lab_DCF_Model.xlsx` and open it in Excel. Enable macros and editing if prompted.

**Step 2 — Review the Historicals sheet**
Start here to understand the company's financial trajectory. Revenue, margins, and cash flow trends from FY2021–FY2025 are laid out in a clean format.

**Step 3 — Select your scenario**
Navigate to the `Scenarios` sheet. The model supports three revenue growth scenarios:
- **Base Case** — 4-year historical CAGR
- **Bull Case** — Peak historical growth rate (also consistent with Indian pharma sector CAGR expectations)
- **Bear Case** — Conservative GDP-linked growth

Change the **Live Scenario** toggle in the `Model` sheet (Row 5, "Live Scenario" cell) to switch between scenarios.

**Step 4 — Review the WACC**
Open the `WACC` sheet to inspect the cost of capital assumptions. The beta computation methodology is documented in the `Beta` sheet, along with the regression output. Adjust the risk-free rate or ERP if you have updated market data.

**Step 5 — Review the Comps sheet**
The `Comps` sheet summarizes peer multiples. You can update the `Comps_Data` sheet with fresh market data (current stock prices, debt, cash) and the Comps sheet will recalculate automatically.

**Step 6 — Read the valuation output**
The `Model` sheet contains the final DCF output — intrinsic value per share, sensitivity tables, and a comparison against the current market price.

---

## 📐 Modeling Conventions

- **Blue text** → Hardcoded inputs (assumptions you can change)
- **Black text** → Formula-driven calculations (do not hardcode)
- **Green text** → Cross-sheet links
- All currency figures are in **₹ Millions (Rs.MM)** unless otherwise stated
- Negative numbers are shown in parentheses: `(1,234)`
- Zeros are displayed as `—`

---

## 📁 Data Sources

| Data | Source |
|---|---|
| Historical Financials | Alkem Laboratories Annual Reports (FY2021–FY2025) |
| Peer Market Data | Screener.in, NSE India |
| Beta Estimation | Yahoo Finance daily price data, Python OLS regression |
| Market Return (Rm) | Nifty 50 historical data (10-year CAGR) |
| Sector Beta Benchmark | Damodaran Online — Emerging Markets Pharma |

---

## ⚠️ Disclaimer

This model is built for **educational and research purposes only**. It does not constitute investment advice. All projections are based on publicly available data and the author's own assumptions. Past financial performance does not guarantee future results.

---

## 👤 Author

Built as part of a self-directed equity research and financial modeling project.  
Feel free to fork, use, or build on this model — attribution appreciated.

---

## 📬 Feedback

If you spot an error, have a suggestion, or want to discuss the methodology, feel free to open an [Issue](../../issues) or reach out directly.
