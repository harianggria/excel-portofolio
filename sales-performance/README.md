# Sales Performance Analysis
An Excel analytics project on order-level sales data, cleaned entirely in Power Query and analyzed through formula-driven summaries and a dashboard.

## 📁 Contents
| File | Description |
|---|---|
| `dataset-sales-performance-dashboard.xlsx` | Main deliverable — cleaned data, summary analysis, and dashboard |
| `dataset-1-sales-performance.xlsx` | Original raw dataset with intentional data quality issues |

## 🧹 Data cleaning approach
The raw dataset (725 rows) contained several intentional issues:

| Issue | Risk | Action Taken |
|---|---|---|
| 5 duplicate order rows | Inflates revenue/profit totals if double-counted | Removed in Power Query before analysis |
| Missing Order Date, Quantity, and/or Revenue (35 rows total) | Breaks time-based trends and understates/overstates totals if left in | Flagged with a `Quality Flag` column (`Passed` / `Need to be reviewed`); excluded from all summary totals rather than estimated |
| Order Date stored as text, mixing `DD/MM/YYYY` and `MM/DD/YYYY` formats inconsistently within the same column | Guessing the wrong format silently shifts an order into the wrong month, distorting the monthly trend | Resolved case-by-case: where the day or month value exceeds 12, the format is unambiguous and was parsed directly; where both values are ≤12, the date is genuinely unresolvable and was flagged for manual review instead of guessed |
| Inconsistent text in Region, Channel, Order Status, Category (casing, spacing, abbreviations) | Splits what should be one category into several, understating true performance per group | Standardized via Power Query (trim, capitalize, replace-value steps) |
| Cancelled/Returned orders mixed into revenue totals | Overstates realized revenue and understates true profit margin if counted alongside completed sales | Excluded from revenue/profit/order-count KPIs and summary tables; kept fully visible in a dedicated Order Status Trend view so cancellation patterns aren't hidden |

All cleaning happens in Power Query — the raw sheet is never hand-edited, so the pipeline is fully reproducible and auditable.

**Cleaning funnel:** 725 raw orders → 720 after removing duplicates (-5) → 684 with complete data (-36 missing/unresolvable) → 611 clean orders used for revenue/profit metrics (-73 Cancelled/Returned, kept visible separately).

## 📊 Dashboard Preview

### 1. KPI Summary
Headline numbers and the data-cleaning funnel at a glance — what's included in "clean," what's not, and why.

![KPI Summary](dashboard/KPI%20Summary.png)

### 2. Trend Analysis
Monthly revenue with Month-over-Month growth %, and order status trend over time (Cancelled/Returned included here on purpose).

![Trend Analysis](dashboard/Trend%20Analysis.png)

### 3. Profitability Analysis
Discount rate vs. average profit margin, broken out by discount band.

![Profitability Analysis](dashboard/Profitability%20Analysis.png)

### 4. Performance Breakdown
Revenue by Category, Region, Channel, and order share by category.

![Performance Breakdown](dashboard/Performance%20Breakdown.png)

### 5. Sales Rep Performance
Revenue leaderboard across the sales team, Completed orders only.

![Sales Rep Performance](dashboard/Sales%20Performance.png)

## 💡 Key insight
Returned and Cancelled orders — while a small share of total orders — carry a disproportionate profit cost, since the business still incurs the underlying cost with little or no revenue recovered. This is broken out separately in the Order Status summary rather than blended into headline totals, so the true cost of returns/cancellations is visible rather than hidden.

## 🛠️ Tools used
Power Query (M) for cleaning, Excel formulas (`SUMIFS`, `COUNTIFS`, `AVERAGEIFS`) for summaries, Excel charts for the dashboard.

---
*Dataset includes intentional data quality issues for practice purposes. This is a portfolio/practice project, not a real business report.*
*Dataset from: https://github.com/nurrzz/portfolio-datasets-for-students*
