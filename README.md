# Excel Analytics Portfolio

A collection of Excel-based data analytics projects, built to practice and demonstrate a real end-to-end workflow: raw data → documented cleaning → formula-driven analysis → dashboard → business insights.

Each project folder is self-contained with its own README, workbook, and (where applicable) the Power Query M code used to clean the data.

## Projects

### 📊 Sales Performance Analysis 
Order-level sales dataset with intentional data quality issues (duplicates, missing values, inconsistent text, mixed date formats). Cleaned entirely in Power Query with a documented Quality Flag system, summarized across Category / Region / Channel / Month / Order Status, and visualized in a dashboard.

**Tools:** Power Query (M), Excel formulas, Excel dashboard & charts
**Source raw data:** https://github.com/nurrzz/portfolio-datasets-for-students

### 🤖 AI-Social Media Analysis
An Excel-based analysis exploring how daily social media and AI tool usage impact sleep, physical activity, mental health, and physical health among students aged 13–25. Built with Power Query (data prep) and live formula-driven pivot summaries for cross-tab analysis.

**Tools:** Power Query (M), Excel formulas, Excel dashboard & charts
**Source raw data:** https://www.kaggle.com/datasets/debayank2024/ai-and-social-media-impact-student-health-and-grades
## Approach

Every project in this repo follows the same discipline:

1. **Raw data stays untouched** — all cleaning happens in a documented pipeline (Power Query and/or formulas), never by hand-editing source cells
2. **Every cleaning decision is logged** in business terms — issue found, risk it posed, action taken — not just a technical changelog
3. **No hardcoded numbers** — summary tables and KPIs are live formulas, so the workbook stays correct if source data changes
4. **Uncertain/incomplete data is flagged, not guessed** — rows with missing critical fields are excluded from totals rather than silently imputed with invented values, unless a documented, defensible imputation method is used

## Tools used across this repo

Microsoft Excel · Power Query (M) · PivotTables/formula-driven summaries · Excel Dashboards

---
*Built as a portfolio project. Feedback welcome via Issues.*
