# 365 Platform — Student Engagement Analysis (Q4 2021 vs Q4 2022)

**Tools:** Excel · Descriptive Statistics · Hypothesis Testing · Confidence Intervals  
**Files:** raw data and result spreadsheets are included in this repo.

---

## Project Summary
This analysis evaluates whether new platform gamification features (XP system, streaks, leaderboards, in-app coins) corresponded with measurable increases in student engagement between Q4 2021 and Q4 2022. The focus is on **low-engagement users** (students who watched **1–100 minutes** in Q4 2021) because they represent the largest growth opportunity.

---

## Key Findings (numbers computed from data)

### Paid-plan (low-engagement users)
- **Mean:** Q4 2021 = **33.8 min** → Q4 2022 = **273.0 min**  
- **Median:** Q4 2021 = **26.3 min** → Q4 2022 = **40.3 min**  
- **Standard deviation:** Q4 2021 = **28.2** → Q4 2022 = **854.6**  
**Interpretation:** Strong year-over-year uplift in average usage for paid users; high SD in 2022 shows growth is driven in part by some users with very large watch times.

### Free-plan (low-engagement users)
- **Mean:** Q4 2021 = **25.4 min** → Q4 2022 = **117.6 min**  
- **Median:** Q4 2021 = **14.2 min** → Q4 2022 = **11.8 min**  
- **Standard deviation:** Q4 2021 = **26.2** → Q4 2022 = **468.9**  
**Interpretation:** Mean rises substantially while median falls slightly — distribution is strongly right-skewed in 2022 (a few heavy users drive the mean).

---

## Statistical Tests & Confidence
- **Two-sample t-tests (unequal variances)** were used to compare minutes-watched between 2021 and 2022, run separately for free-plan and paid-plan groups (Task 4). Tests indicate the increase in minutes watched in 2022 is statistically significant for both groups.  
- **Regional comparison (Task 5):** Directional hypothesis tests (two-sample t-tests, unequal variances) comparing 2022 free-plan users in the **US vs India** show **slightly higher average engagement in India**, suggesting potential localization opportunities.  
- **Distribution checks:** Skewness and kurtosis were computed for each group to validate interpretation of mean vs median — results show heavy right skew and high kurtosis in 2022, consistent with the mean being inflated by outliers.

---

## Files in this repository
- `Engagement Project.xlsx` — raw dataset and Task 1–3 sheets.  
  Local path (uploaded): `/mnt/data/Engagement Project.xlsx`  
- `Hypothesis Testing - task 4.xlsx` — hypothesis testing outputs for 2021 vs 2022.  
  Local path: `/mnt/data/Hypothesis Testing - task 4.xlsx`  
- `Hypothesis Testing - task 5.xlsx` — regional (US vs India) test outputs.  
  Local path: `/mnt/data/Hypothesis Testing - task 5.xlsx`

> Once pushed to GitHub, these files will appear in your repo root and become downloadable.

---

## How to reproduce (Excel)
1. Open **`Engagement Project.xlsx`** → go to **Task 1 and 2**.  
2. Filter students with `minutes_watched_21` between **1 and 100**. Separate paid and free via `paid` column.  
3. Compute `AVERAGE`, `MEDIAN`, and `STDEV.S` on `minutes_watched_21` and `minutes_watched_22`.  
4. Compute skewness and kurtosis with:  
   - `SKEW(range)`  
   - `KURT(range)`  
5. Build 95% confidence intervals using:  
   - `mean ± T.INV.2T(0.05, df) * (sd / SQRT(n))`  
6. Hypothesis tests (Task 4 & 5): use **Data Analysis → t-Test: Two-Sample Assuming Unequal Variances**, or `T.TEST` with type=3.

---

## Short conclusion
Both paid and free low-engagement users showed **substantial average increases** in minutes watched in Q4 2022 vs Q4 2021. Paid users show the clearest and most consistent uplift. Free users' mean increases are driven mainly by heavy outliers. Overall, evidence supports the idea that the platform’s gamification features helped raise engagement, and regional differences point toward meaningful localization opportunities.

---

## Notes / Next steps
- Add visualizations (histograms, boxplots) for distribution behavior.  
- Investigate retention cohorts over time.  
- Run robust statistics (trimmed mean, winsorized SD) to confirm conclusions.

---

## Contact
Feel free to explore the Excel files or request visualizations / Python replication as needed.

