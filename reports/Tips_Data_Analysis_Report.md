# Tips Data Analysis — Final Report

Author: Data Analyst  
Date: (add date)

---

## Executive summary
- Dataset: 244 complete transactions, 7 columns, no missing values.  
- Key findings: average tip ≈ 16.1% of bill; total bill and tip strongly positively correlated (r ≈ 0.676); party size moderately correlates with bill (r ≈ 0.598).  
- Business implication: dinner service and larger parties drive higher revenue; tipping behavior is consistent and predictable.

---

## 1. Data composition
Overview:
- Rows / columns: 244 × 7  
- Columns:
  - total_bill — numeric (USD)  
  - tip — numeric (USD)  
  - sex — categorical (Male / Female)  
  - smoker — categorical (Yes / No)  
  - day — categorical (Thur, Fri, Sat, Sun)  
  - time — categorical (Lunch / Dinner)  
  - size — integer (party size)  
- Missing values: None detected  
- Readiness: Clean and ready for analysis

Figures (composition):
- Figure 1 — Variable summary table (names, types, non-null counts)  
- Figure 2 — Bar charts: counts for categorical variables (sex, smoker, day, time)

Caption (Fig 1): Table showing variable names, data types, non-null counts and brief descriptions.  
Caption (Fig 2): Frequency distribution of categories to show balance across groups.

---

## 2. Data distribution
Analysis performed: histograms + KDE, Q–Q plots, skewness/kurtosis, normality tests.

Key observations:
- total_bill and tip: Right-skewed (many low bills, long right tail).  
- size: Discrete distribution with mode at 2.  
- Normality tests: Most numeric variables reject normality → prefer non-parametric tests.

Figures (distribution):
- Figure 3 — Histogram + KDE: total_bill  
- Figure 4 — Histogram + KDE: tip  
- Figure 5 — Histogram: party size (discrete)  
- Figure 6 — Q–Q plots for numeric variables

Caption (Fig 3–4): Histograms showing right-skew; mean and median lines annotated.  
Caption (Fig 6): Q–Q plots highlighting tail deviations from normality.

---

## 3. Data comparison
Methods: boxplots, violin plots, group summary tables, Mann–Whitney U (two-group) and Kruskal–Wallis (multi-group) tests.

Key findings:
- Time (Lunch vs Dinner): Dinner mean ≈ $20.80 vs Lunch ≈ $17.18 — statistically significant (p < 0.05).  
- Sex: Males spend ~9.6% more on average (male mean ≈ $19.79 vs female ≈ $18.06).  
- Smoker: Small differences; mixed significance depending on test.  
- Day: Weekend days show higher variability and larger outliers.

Figures (comparison):
- Figure 7 — Boxplots: total_bill by sex, smoker, time, day  
- Figure 8 — Boxplots: tip by sex, smoker, time, day  
- Figure 9 — Violin plots: total_bill by categories  
- Figure 10 — Group summary tables (count, mean, median, std)

Caption (Fig 7–9): Visual comparison of central tendency and spread across categories; violin plots show full distribution shapes.

---

## 4. Data relationship
Methods: Pearson correlation matrix (numeric), correlation heatmap, scatter plots with regression lines, interactive bubble plot (total_bill vs tip; size=party size; color=sex; symbol=smoker).

Key relationships:
- total_bill vs tip: strong positive correlation (r ≈ 0.676).  
- total_bill vs size: moderate positive correlation (r ≈ 0.598).  
- tip vs size: moderate positive correlation (~0.49).

Figures (relationship):
- Figure 11 — Correlation heatmap (numeric variables)  
- Figure 12 — Scatter + regression: total_bill vs tip (annotated r)  
- Figure 13 — Scatter: size vs total_bill and size vs tip  
- Figure 14 — Interactive bubble plot (total_bill vs tip; bubble size = party size)

Caption (Fig 12): Regression line demonstrates linear trend; r annotated to describe strength.

---

## 5. Tip-percentage analysis
Derived metric: tip_percent = (tip / total_bill) * 100

Findings:
- Mean tip% ≈ 16.1%; median similar; modest dispersion.  
- Lunch often shows slightly higher tip% (relative to lower base bills).  
- Tip% stable across sex and smoker groups.

Figures (tip%):
- Figure 15 — Histogram: tip percentage distribution  
- Figure 16 — Boxplot: tip percentage by time and sex

Caption (Fig 15–16): Tip percentage distribution and group comparisons to detect systematic deviations.

---

## 6. Key insights & recommendations
- Prioritize dinner operations and capacity management to maximize revenue.  
- Encourage larger-party bookings and group offers.  
- Monitor tip percentage (~16%) as a KPI for service quality; investigate deviations.  
- Use non-parametric methods for hypothesis testing due to skewed distributions.  
- Review outliers for potential upsell patterns or data issues.

---

## Appendix — Figures to include in PDF
1. Fig 1: Variable summary table  
2. Fig 2: Categorical distributions (sex, smoker, day, time)  
3. Fig 3–5: Histograms & KDEs (total_bill, tip, size)  
4. Fig 6: Q–Q plots for numeric variables  
5. Fig 7–9: Boxplots / violin plots for comparisons by category  
6. Fig 10: Group summary tables  
7. Fig 11: Correlation heatmap  
8. Fig 12–14: Scatter plots & interactive bubble plot  
9. Fig 15–16: Tip percentage distribution & group boxplots

---

## Export recommendation
- Recommended: execute the notebook so all plots render inline, then export to PDF using JupyterLab File → Export Notebook As → PDF or:
  ```
  jupyter nbconvert --to pdf "01_data_analysis.ipynb"
  ```
  This preserves images, captions and layout.
- Alternative: convert this markdown to PDF with pandoc after embedding the figure image files.

Notes: Replace figure placeholders (Figure X) with the actual rendered images (e.g., ![Fig3](path/to/fig3.png)) from the executed notebook prior to exporting. Ensure the notebook is executed top-to-bottom so figures are embedded in the exported PDF.
