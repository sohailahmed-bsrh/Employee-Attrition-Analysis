# IBM HR Employee Attrition Analytics

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3000&pause=1000&color=00C6FF&center=true&vCenter=true&width=700&lines=IBM+HR+Employee+Attrition+Analytics;Data-Driven+Workforce+Retention+Intelligence;Exploratory+Data+Analysis+%26+Hypothesis+Testing;Actionable+Business+Strategies+%26+Insights" alt="Typing Banner" />

<p align="center">
  <b>Comprehensive Data Science Investigation into Employee Turnover Dynamics, Compensation Disparities, and Organizational Retention Factors</b>
</p>

<p align="center">
  <b>Recommended Repository Name:</b> <code>ibm-hr-attrition-analytics</code> or <code>employee-attrition-intelligence</code>
</p>

</div>

---

## Author Profile

<div align="center">

<a href="https://sohail.devsil.com">
  <img src="https://avatars.githubusercontent.com/sohail-ahmed-26" width="130" height="130" style="border-radius: 50%; border: 3px solid #00c6ff;" alt="Sohail Ahmed" />
</a>

### Sohail Ahmed
**AI Engineer & Data Scientist | Machine Learning Practitioner**  
*BS Telecommunication | Devsil, Software Technology Park, Mansehra, KPK, Pakistan*

</div>

### Verified Accounts & Portfolios

| Platform | Profile Link | Handle / Designation |
| :--- | :--- | :--- |
| **Portfolio Website** | [sohail.devsil.com](https://sohail.devsil.com) | Primary Professional Portfolio |
| **Alternate Portfolio** | [sak.kesug.com](https://www.sak.kesug.com) | Personal Portfolio & Showcase |
| **GitHub** | [github.com/sohail-ahmed-26](https://github.com/sohail-ahmed-26) | @sohail-ahmed-26 |
| **LinkedIn** | [linkedin.com/in/sohail-ahmed-devsil](https://www.linkedin.com/in/sohail-ahmed-devsil) | sohail-ahmed-devsil |
| **Kaggle** | [kaggle.com/sohail2411126](https://www.kaggle.com/sohail2411126) | @sohail2411126 |
| **YouTube** | [youtube.com/@sohailahmed-k4k](https://youtube.com/@sohailahmed-k4k?si=uZ7KjZ_0qTkNekgp) | @sohailahmed-k4k |
| **Twitter / X** | [x.com/ahmed241126](https://x.com/ahmed241126) | @ahmed241126 |
| **Instagram** | [instagram.com/sohailahmed5990](https://www.instagram.com/sohailahmed5990) | @sohailahmed5990 |

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Business Problem Statement](#business-problem-statement)
3. [Project Objectives](#project-objectives)
4. [Dataset Architecture & Features](#dataset-architecture--features)
5. [Data Cleaning & Integrity Validation](#data-cleaning--integrity-validation)
6. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
7. [Inferential Statistical Hypothesis Testing](#inferential-statistical-hypothesis-testing)
8. [Data Visualizations](#data-visualizations)
9. [Key Business Insights](#key-business-insights)
10. [Strategic Recommendations](#strategic-recommendations)
11. [Technology Stack](#technology-stack)
12. [Repository Structure](#repository-structure)
13. [Installation & Execution Guide](#installation--execution-guide)
14. [License & Acknowledgments](#license--acknowledgments)

---

## Executive Summary

Employee turnover represents one of the most substantial operational and financial challenges modern enterprises encounter. Unplanned departures disrupt team productivity, increase recruitment overhead, and lead to institutional knowledge loss.

This project delivers an end-to-end analytical study of workforce attrition utilizing the IBM HR Analytics Employee Attrition dataset. Through systematic data auditing, exploratory data analysis (EDA), rigorous inferential hypothesis testing, and multidimensional visualization, this project isolates the primary drivers of voluntary turnover and provides actionable, data-backed retention strategies for HR executives and leadership teams.

---

## Business Problem Statement

Organizations invest heavy capital in acquiring, onboarding, and training top talent. High attrition rates introduce significant frictions:

- Escalating hiring, background screening, and onboarding costs.
- Reduced project delivery velocity and diminished client satisfaction.
- Disproportionate turnover in critical business units (Sales, Human Resources).
- Knowledge transfer deficits and lowered team morale among retained personnel.

The core challenge addressed by this analysis is identifying:
- Which specific departments, salary tiers, and employee groups exhibit the highest attrition risk?
- Is compensation disparity statistically correlated with employee departure?
- What role do workplace satisfaction, work-life balance, and tenure play in employee loyalty?

---

## Project Objectives

1. **Audit Data Quality:** Perform missing value scans, duplicate checks, data type validations, and IQR outlier detection on compensation variables.
2. **Quantify Attrition Rates:** Measure baseline turnover across departments, role categories, and demographic brackets.
3. **Analyze Compensation Disparities:** Evaluate the income distribution of departing versus retained employees.
4. **Conduct Hypothesis Testing:** Statistically test whether the difference in monthly compensation between attrited and retained staff is significant using Welch's Two-Sample Independent T-Test.
5. **Evaluate Quality-of-Life Metrics:** Gauge the correlation of job satisfaction, work-life balance, and overtime with turnover.
6. **Formulate Strategic Interventions:** Provide concrete, actionable retention policies tailored for business stakeholders.

---

## Dataset Architecture & Features

The study utilizes the IBM HR Analytics Employee Attrition Dataset, comprising **1,470 records** across **35 attributes**.

### Core Dataset Parameters

| Parameter | Specification |
| :--- | :--- |
| Total Rows | 1,470 employees |
| Total Columns | 35 attributes |
| Target Variable | `Attrition` (Binary: `Yes`, `No`) |
| Retained Employees (`No`) | 1,233 (83.88%) |
| Attrited Employees (`Yes`) | 237 (16.12%) |
| Data Completeness | 100% (No missing values detected) |

### Key Feature Groups

- **Demographics:** Age, Gender, MaritalStatus, Education, EducationField.
- **Role & Department:** Department, JobRole, JobLevel, BusinessTravel, DistanceFromHome.
- **Compensation & Finance:** MonthlyIncome, DailyRate, HourlyRate, MonthlyRate, PercentSalaryHike, StockOptionLevel.
- **Experience & Tenure:** TotalWorkingYears, YearsAtCompany, YearsInCurrentRole, YearsSinceLastPromotion, YearsWithCurrManager.
- **Work Experience & Feedback:** EnvironmentSatisfaction, JobInvolvement, JobSatisfaction, WorkLifeBalance, OverTime, TrainingTimesLastYear.

---

## Data Cleaning & Integrity Validation

To guarantee analytical accuracy, systematic data cleaning was performed:

1. **Missing Value Audit:**
   - Evaluated all 35 columns using `df.isnull().sum()`.
   - Result: Zero null or missing values across the entire dataset.

2. **Duplicate Record Detection:**
   - Evaluated duplicate occurrences with `df.duplicated().sum()`.
   - Result: Zero duplicate records confirmed.

3. **Data Type Verification:**
   - Verified numeric integrity (`int64`, `float64`) and categorical classifications (`object`).

4. **Outlier Detection via Interquartile Range (IQR):**
   - Conducted on the primary continuous financial metric: `MonthlyIncome`.
   - First Quartile ($Q_1$): 25th percentile ($2,911.00).
   - Third Quartile ($Q_3$): 75th percentile ($8,379.00).
   - Interquartile Range ($IQR = Q_3 - Q_1$): $5,468.00.
   - Upper Outlier Fence: $Q_3 + 1.5 \times IQR = \$16,581.00$.
   - Observation: High-earning leadership and executive roles appear beyond the upper whisker, reflecting real-world corporate compensation distribution rather than measurement anomalies.

---

## Exploratory Data Analysis (EDA)

### 1. Overall Attrition Ratio
- **No (Retained):** 1,233 employees (83.88%)
- **Yes (Departed):** 237 employees (16.12%)
- Demonstrates an imbalanced target distribution characteristic of real-world human resource telemetry.

### 2. Department-Wise Attrition Comparison

| Department | Retained (`No`) | Departed (`Yes`) | Departmental Attrition Rate |
| :--- | :--- | :--- | :--- |
| **Sales** | 354 | 92 | **20.63%** |
| **Human Resources** | 51 | 12 | **19.05%** |
| **Research & Development** | 828 | 133 | **13.84%** |

*Key Takeaway:* Sales presents the highest relative attrition rate at 20.63%, followed closely by Human Resources at 19.05%, while Research & Development maintains the highest relative retention rate (86.16%).

### 3. Compensation Profile: Retained vs. Departed

| Metric | Retained Employees (`No`) | Departed Employees (`Yes`) | Difference / Deficit |
| :--- | :--- | :--- | :--- |
| Mean Monthly Income | $6,832.74 | $4,787.09 | -$2,045.65 (-29.94%) |
| Median Monthly Income | $5,204.00 | $3,202.00 | -$2,002.00 (-38.47%) |
| Standard Deviation | $4,818.21 | $3,640.21 | Lower variance among leavers |

*Key Takeaway:* Departing employees earn an average of approximately 30% less than retained counterparts, with the median deficit exceeding 38%.

### 4. Tenure Dynamics (Years at Company)
- **Retained Staff Mean Tenure:** 7.37 years (Median: 6.0 years)
- **Departed Staff Mean Tenure:** 5.13 years (Median: 3.0 years)
- *Key Takeaway:* Employee departures cluster heavily within the initial 1 to 3 years of organizational tenure, pointing to onboarding and early career-stage friction.

### 5. Job Satisfaction Ratings vs. Attrition

| Satisfaction Score | Rating Level | Attrition Percentage |
| :--- | :--- | :--- |
| 1 | Low | 22.84% |
| 2 | Medium | 16.43% |
| 3 | High | 16.52% |
| 4 | Very High | 11.33% |

*Key Takeaway:* Employees rating job satisfaction as "Low" (Level 1) leave at more than double the rate of employees reporting "Very High" satisfaction (Level 4).

### 6. Work-Life Balance & Overtime Analysis
- **Work-Life Balance Level 1 (Poor):** 31.25% attrition rate.
- **Work-Life Balance Level 3 (Good):** 14.22% attrition rate.
- **OverTime = Yes:** 30.53% attrition rate.
- **OverTime = No:** 10.44% attrition rate.
- *Key Takeaway:* Staff required to perform overtime work experience nearly triple (2.92x) the attrition rate of non-overtime staff.

---

## Inferential Statistical Hypothesis Testing

To validate whether the observed salary differences between departing and retained employees were statistically significant or occurred by random chance, an independent two-sample t-test was conducted.

### Hypothesis Formulation
- **Null Hypothesis ($H_0$):** There is no significant difference in the mean monthly income between employees who leave and employees who stay ($\mu_{\text{Yes}} = \mu_{\text{No}}$).
- **Alternative Hypothesis ($H_1$):** There is a statistically significant difference in the mean monthly income between employees who leave and employees who stay ($\mu_{\text{Yes}} \neq \mu_{\text{No}}$).

### Statistical Methodology & Parameters
- **Test:** Welch's Two-Sample Independent T-Test (equal variance not assumed)
- **Sample 1 (`Attrition == Yes`):** $n_1 = 237$, $\bar{x}_1 = \$4,787.09$, $s_1 = \$3,640.21$
- **Sample 2 (`Attrition == No`):** $n_2 = 1233$, $\bar{x}_2 = \$6,832.74$, $s_2 = \$4,818.21$
- **Significance Level ($\alpha$):** 0.05

### Test Output

```
Test Statistic (t): -5.694496934949914
P-Value:           2.5526903444747516e-08
```

### Statistical Inference
Because the p-value ($2.55 \times 10^{-8}$) is substantially lower than $\alpha = 0.05$ (and $\alpha = 0.001$), we reject the null hypothesis ($H_0$). There is overwhelming empirical evidence that compensation differs significantly between the two cohorts, verifying that lower income levels are strongly associated with higher employee attrition.

---

## Data Visualizations

The analytical notebook implements a clean visualization suite using Matplotlib, Seaborn, and Plotly Express:

1. **Attrition Proportion Pie & Bar Charts:** Visualizing the target variable distribution and percentage splits.
2. **Age & Monthly Income Histograms:** Displaying right-skewed compensation distributions and age concentration.
3. **Monthly Income Boxplots:** Highlighting median salary levels, interquartile ranges, and upper-echelon compensation outliers.
4. **Correlation Heatmap:** Multi-variable numeric correlation matrix illustrating dependencies across tenure, age, level, and monthly income without severe collinearity issues.
5. **Departmental Attrition Cross-tabulation:** Grouped bar charts contrasting employee headcount versus exit counts across Sales, R&D, and HR.

---

## Key Business Insights

### 1. Departmental Vulnerability
Sales and Human Resources exhibit the steepest percentage turnover rates (20.63% and 19.05% respectively). These units suffer from distinct operational pressures, target quotas, and role fatigue compared to R&D.

### 2. The Compensation Threshold
Financial compensation is a primary predictive factor in voluntary exits. Departing employees show an average monthly salary deficit of $2,045 compared to retained staff. Below-market compensation directly elevates flight risk.

### 3. Early-Career Turnover Cliff
Attrition peaks sharply during the initial 1 to 3 years of employment (median tenure of 3.0 years for departures vs 6.0 years for retained staff). Once employees surpass the 5-year threshold, retention stability rises significantly.

### 4. Overtime & Burnout Catalyst
Staff subject to mandatory or frequent overtime leave at an alarming rate of 30.53%, compared to only 10.44% for their non-overtime peers. Unmanaged workload directly accelerates attrition.

### 5. Workplace Satisfaction Dividends
Low satisfaction scores (Level 1) correlate with double the attrition rate of high satisfaction tiers (Level 4), proving that company culture, recognition, and management quality directly protect organizational stability.

---

## Strategic Recommendations

### 1. Re-benchmark Entry & Mid-Tier Compensation
- Adjust baseline compensation for lower-quartile employees, specifically in high-risk bands ($3,000 - $5,000 monthly).
- Align salary scales with regional market benchmarks to eliminate compensation-driven departures.

### 2. Department-Specific Retention Programs
- **For Sales:** Revisit sales quota structures, optimize commission schedules, and establish sustainable pipeline support to alleviate performance pressure.
- **For HR:** Create clear internal career progression ladders and enhance administrative support to mitigate workload fatigue.

### 3. Structured Early-Tenure Engagement (Years 1 to 3)
- Overhaul onboarding programs with 30-60-90 day milestone reviews.
- Institute formal mentorship pairing senior staff with new hires during their first 24 months.

### 4. Overtime Mitigation & Work-Life Balance Policies
- Cap consecutive overtime hours and implement mandatory compensatory time-off policies.
- Encourage flexible working arrangements and hybrid schedules where operationally viable.

### 5. Continuous Sentiment & Satisfaction Audits
- Conduct quarterly pulse surveys focusing on environment satisfaction and managerial relationships.
- Establish transparent internal promotion pathways so high performers envision long-term tenure.

---

## Technology Stack

- **Language:** Python 3.x
- **Data Manipulation:** pandas, numpy
- **Statistical Analysis:** scipy.stats (Welch's t-test, descriptive metrics)
- **Data Visualization:** Matplotlib, Seaborn, Plotly Express
- **Interactive Development:** Jupyter Notebook

---

## Repository Structure

```
Employee-Attrition-Analysis/
│
├── dataset/
│   └── employee_atrition.csv            # IBM HR Analytics Employee Attrition dataset (1,470 x 35)
│
├── Employee Attrition Analysis.ipynb    # Comprehensive analytical notebook (EDA, Tests, Visuals)
└── README.md                            # Executive project documentation & analysis report
```

---

## Installation & Execution Guide

### 1. Clone the Repository

```bash
git clone https://github.com/sohail-ahmed-26/Employee-Attrition-Analysis.git
cd Employee-Attrition-Analysis
```

### 2. Create and Activate a Virtual Environment

```bash
# On Linux / macOS
python3 -m venv venv
source venv/bin/activate

# On Windows
python -m venv venv
.\venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install pandas numpy scipy matplotlib seaborn plotly jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook "Employee Attrition Analysis.ipynb"
```

---

## License & Acknowledgments

- **Dataset Source:** IBM HR Analytics Employee Attrition Dataset.
- **Author:** Sohail Ahmed ([sohail.devsil.com](https://sohail.devsil.com) | [GitHub Profile](https://github.com/sohail-ahmed-26))
- **License:** Open for academic, research, and educational utilization.
