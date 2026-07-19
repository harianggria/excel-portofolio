# Sales Performance Analysis

An Excel analytics project on order-level sales data, cleaned entirely in Power Query and analyzed through formula-driven summaries and a dashboard.

## 📁 Contents

| File | Description |
|---|---|
| `dataset-1-sales-performance.xlsx` | Main deliverable — cleaned data, summary analysis, and dashboard |
| `data/dataset-1-sales-performance.xlsx` | Original raw dataset with intentional data quality issues |

## 🧹 Data cleaning approach

The raw dataset (725 rows) contained several intentional issues:

| Issue | Risk | Action Taken |
|---|---|---|
| 5 duplicate order rows | Inflates revenue/profit totals if double-counted | Removed in Power Query before analysis |
| Missing Order Date, Quantity, and/or Revenue (52 rows total) | Breaks time-based trends and understates/overstates totals if left in | Flagged with a `Quality Flag` column (`OK` / `Incomplete`); excluded from all summary totals rather than estimated |
| Inconsistent text in Region, Channel, Order Status, Category (casing, spacing, abbreviations) | Splits what should be one category into several, understating true performance per group | Standardized via Power Query (trim, capitalize, replace-value steps) |
| Order Date stored as mixed text/date types | Breaks sorting and date-based grouping | Converted to a consistent date type in Power Query |

All cleaning happens in Power Query — the raw sheet is never hand-edited, so the pipeline is fully reproducible and auditable.

## 📊 What the dashboard shows

- **Headline KPIs**: Total Revenue, Total Profit, Clean Order Count, Average Order Value, Profit Margin
- **Revenue by Category** — which product categories drive the top line
- **Monthly Revenue & Profit trend** — sorted chronologically
- **Revenue by Region** — geographic performance
- **Orders by Channel** — Retail / Online / Corporate / Marketplace split

## 💡 Key insight

Returned and Cancelled orders — while a small share of total orders — carry a disproportionate profit cost, since the business still incurs the underlying cost with little or no revenue recovered. This is broken out separately in the Order Status summary rather than blended into headline totals, so the true cost of returns/cancellations is visible rather than hidden.

## 🛠️ Tools used

Power Query (M) for cleaning, Excel formulas (`SUMIFS`, `COUNTIFS`, `AVERAGEIFS`) for summaries, Excel charts for the dashboard.

---
*Dataset includes intentional data quality issues for practice purposes. This is a portfolio/practice project, not a real business report.*
