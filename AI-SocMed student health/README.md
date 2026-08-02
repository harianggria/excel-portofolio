# 📱 Social Media & AI Tool Usage vs. Student Health — Excel Analysis

An Excel-based analysis exploring how daily social media and AI tool usage impact sleep, physical activity, mental health, and physical health among students aged 13–25. Built with **Power Query** (data prep) and **live formula-driven pivot summaries** for cross-tab analysis.

![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=flat)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-blue?style=flat)

---

## 📌 Project Overview

This project analyzes a dataset of **15,000 students (ages 13–25)** to answer:

> *How does daily social media and AI tool usage affect sleep hours, physical activity, mental health, and physical health — and does this differ by age group?*

The raw dataset is kept **100% untouched** in its own sheet. All grouping (age bands, usage-level buckets) and aggregation happen downstream in a live, formula-driven Pivot Summary — so the source data always stays an exact match to the original file.

---

## 🗂️ Dataset
collected from : https://www.kaggle.com/datasets/debayank2024/ai-and-social-media-impact-student-health-and-grades
| | |
|---|---|
| **Source** | AI_SocialMedia_Student_Health_Dataset |
| **Rows** | 15,000 students |
| **Age range** | 13–25 years |
| **Original columns (14)** | Student_ID, Age, Gender, Education_Level, Daily_Social_Media_Hours, Daily_AI_Tool_Usage_Hours, Sleep_Hours, Physical_Activity_Hours, Mental_Health_Score, Physical_Health_Score, Social_Isolation_Score, Burnout_Level, Academic_Performance_Score, Academic_Failure_Risk |
| **Missing values** | 0 |

---

## 🛠️ Tools & Techniques

- **Power Query** — data import, data type transformation, and data quality checks (documented step-by-step in the workbook)
- **Pivot Summary (formula-driven)** — cross-tabulates Age Group × Usage Level using `SUMPRODUCT`, computed live and directly from the raw data sheet (no helper columns added to source data)
- **Excel Charts** — clustered bar charts visualizing each metric across usage levels
- **Excel Tables** — structured, filterable data source

---

## 📊 Workbook Structure

| Sheet | Description |
|---|---|
| `README` | Project summary, data source, and navigation guide |
| `Query Steps` | Documented Power Query "Applied Steps" + reusable M-code |
| `Data` | Raw dataset, 100% unchanged from source (headers & values) |
| `Pivot Summary` | Live cross-tab tables: Age Group × Usage Level, averaged across Sleep, Physical Activity, Mental Health, and Physical Health scores |
| `Dashboard` | 6 bar charts visualizing the pivot summary results |
| `Insight` | Written analysis, conclusions per age group, and recommendations |

📥 [Download the full workbook](./AI_SocialMedia_Student_Health_Dataset.xlsx)

---

## 🔑 Key Insights

- **Age barely matters — usage duration does.** The negative-impact pattern is nearly identical across all three age groups (13–17, 18–21, 22–25); correlation between Age and every health metric is close to 0.
- **Social media has the largest impact.** Heavy users (>6 hrs/day) sleep ~1 hour less than light users (<3 hrs/day) — consistent across all age groups.
- **Mental health drops the sharpest**: from an average score of ~85 (light use) down to ~70 (heavy use) — a 15-point gap, the steepest decline of any metric measured.
- **Physical health follows the same trend** (from ~92 to ~84), tracking closely with a drop in physical activity (from ~1.45 hrs/day to ~1.06 hrs/day).
- **Social isolation is strongly correlated with social media use** (r = 0.72), and isolation itself correlates negatively with physical activity (r = -0.69) and mental health (r = -0.54).
- **AI tool usage shows a similar but much milder pattern** — roughly half the impact of social media on sleep and mental health, and almost no measurable effect on physical activity.
- **Academic performance** correlates negatively with both types of screen time, more strongly with social media (r = -0.39) than AI tools (r = -0.21).

---

## 💡 Recommendations

1. Prioritize limiting daily social media use (target: <3 hrs/day) — it's the single biggest lever for improving sleep, mental health, and physical health across all ages.
2. AI tool usage is comparatively safer for physical activity but should still be moderated (<1.5–2 hrs/day) given its measurable effect on sleep and mental health.
3. Schools/campuses could use social isolation score and sleep hours as early-warning indicators, since both correlate strongly with declining academic performance.

---

## 📈 Screenshots

> *Add screenshots of the Dashboard and Pivot Summary sheets here, e.g.:*

```
![Dashboard](./screenshots/dashboard.png)
![Pivot Summary](./screenshots/pivot-summary.png)
```

---

## ⚠️ Methodology Note

This is a **descriptive correlational analysis**, not a causal study. Age Group and Usage Level buckets are computed live via `SUMPRODUCT` formulas directly against the raw data — no permanent helper columns were added to the source sheet. Correlation coefficients (Pearson's r) were computed across the full 15,000-row dataset.

---

## 📬 Contact

Feel free to reach out or connect if you have questions about this analysis or want to collaborate on similar data projects.
