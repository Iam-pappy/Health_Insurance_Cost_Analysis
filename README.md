# 🏥 Health Insurance Cost Analysis

A data analytics project examining what drives medical insurance charges across 1,338 beneficiaries. Built with Excel (Pivot Tables + Statistical Analysis) and Power BI.

## 📊 Project Summary

| Metric | Value |
|--------|-------|
| Records Analyzed | 1,338 |
| Overall Avg Charge | $13,270 |
| Smoker Share | 20% (274 customers) |
| Strongest Cost Driver | Smoking (r = 0.79) |
| Regions Covered | Northeast, Northwest, Southeast, Southwest |


## 🗂️ Files in This Repository

| File | Description |
|------|-------------|
| `Insurance_Raw_Dataset.xlsx` | Raw dataset withe missing values and inconsistent data formats |
| `Insurance_Cleaned_Dataset.xlsx` | Cleaned dataset with derived fields (Age group, BMI category, Smoker binary, High-charge flag) |
| `Insurance_Pivot_Table_Analysis.xlsx` | Six pivot table sheets covering all key segments |
| `Health_Insurance_Cost_Analysis_Dashboard.pbix` | Power BI interactive dashboard |
| `Health_Insurance_Cost_Report.pptx` | Full business report with findings and recommendations |

---

## 🔍 Key Findings

### 1. Smoking — Dominant Cost Driver (r = 0.79)

Smoking has the strongest correlation with charges by a wide margin.

| Segment | Avg Charge | Share of Customers | Share of Total Costs |
|---------|-----------|-------------------|----------------------|
| Smokers | $32,050 | 20% | **49.5%** |
| Non-Smokers | $8,434 | 80% | 50.5% |

> 20% of customers generate nearly half of all costs. The gap per smoker is **$23,616/year**.

### 2. Age + Smoking — Compounding Risk

The absolute cost gap stays consistent across age bands (~$23–24K), but the ratio is most extreme for young smokers.

| Age Group | Smoker Avg | Non-Smoker Avg | Gap | Ratio |
|-----------|-----------|----------------|-----|-------|
| 18–30 | $27,528 | $4,462 | $23,066 | **6.2x** |
| 31–45 | $31,707 | $7,246 | $24,461 | 4.4x |
| 46–60 | $36,452 | $12,188 | $24,263 | 3.0x |
| 60+ | $38,930 | $15,367 | $23,563 | 2.53x |

- **Young smokers (18–30):** highest relative risk ratio (6.2x) — most likely underpriced
- **Senior smokers (60+):** highest absolute cost ($38,930) — top wellness intervention priority


### 3. BMI — Meaningful Secondary Driver (r = 0.20)

Over half the customer base falls in the Obese category.

| BMI Category | Count | Avg Charge |
|--------------|-------|-----------|
| Obese | 707 | $15,552 |
| Overweight | 386 | $10,988 |
| Normal | 225 | $10,409 |
| Underweight | 20 | $8,852 |

Obese customers pay **49% more** than Normal BMI customers. The Obese group is also the largest single segment (53% of all records).


### 4. Southeast Region — Highest Cost Geography

| Region | Count | Avg Charge | Avg BMI | Smoker Avg |
|--------|-------|-----------|---------|-----------|
| **Southeast** | 364 | **$14,735** | **33.4** | **$34,845** |
| Northeast | 324 | $13,406 | 29.2 | — |
| Northwest | 325 | $12,418 | 29.2 | — |
| Southwest | 325 | $12,347 | 30.6 | — |

The Southeast carries a double burden — highest average BMI (33.4) and highest smoker-specific charges ($34,845 vs. $32,050 overall). This is not random variation; it reflects a concentration of compounding risk factors.


## 📈 Correlation Summary

| Variable | Correlation (r) | Rank |
|----------|----------------|------|
| Smoking | 0.79 | #1 — Dominant |
| Age | 0.30 | #2 — Moderate |
| BMI | 0.20 | #3 — Secondary |
| Children | 0.07 | #4 — Minimal |


## 🛠️ Tools & Methods

- **Microsoft Excel** — Data cleaning, derived field engineering, pivot table analysis, correlation analysis
- **Power BI** — Interactive dashboard with slicers for region, age group, smoking status, and BMI category
- **Analysis type** — Cross-sectional (single time period snapshot)

### Pivot Table Sheets Built

1. `Statistical Analysis` — Correlation coefficients + specific segment averages
2. `Summary Table` — Overall segment overview
3. `Smoker vs Non-Smoker Charge` — Direct cost comparison
4. `Age Group + Smoker Analysis` — Cross-segmented breakdown with ratios
5. `BMI Category Analysis` — All four BMI bands with counts and averages
6. `Regional Analysis` — Geographic comparison with BMI overlay


## 💡 Recommendations

1. **Smoking-Based Premium Tiers** — Smokers cost 3.8x more but pricing rarely reflects this fully. Pilot differentiated premiums in the Southeast.
2. **Southeast Wellness Program** — Combined smoking cessation + weight management targeting the highest-cost region.
3. **Low-Risk Product Tier** — A competitive product for non-smoker + healthy BMI + under-45 customers. *(Exact avg charge for this segment requires a dedicated 3-variable pivot — see pivot table methodology note.)*
4. **Young Smoker Re-Pricing** — The 18–30 smoker segment carries a 6.2x cost ratio, the largest pricing gap in the portfolio.


## 📁 Dataset Variables

| Variable | Type | Description |
|----------|------|-------------|
| Age | Numeric | Beneficiary age |
| Sex | Categorical | Male / Female |
| BMI | Numeric | Body Mass Index |
| Children | Numeric | Number of dependants |
| Smoker | Categorical | Yes / No |
| Region | Categorical | US region (4 values) |
| Charges | Numeric | Annual medical charges (target variable) |
| Age_group | Derived | Banded: 18–30, 31–45, 46–60, 60+ |
| BMI_category | Derived | Underweight / Normal / Overweight / Obese |
| Smoker_binary | Derived | 1 = Smoker, 0 = Non-smoker |
| High_charge | Derived | High / Low (above/below median) |


## 👤 Author

Analysed and reported by Afolabi Saheed — Excel · Power BI · SQL· Python (upcoming)

*This project is part of a portfolio demonstrating end-to-end data analysis: data cleaning, pivot analysis, dashboard design, statistical correlation, and business reporting.*
