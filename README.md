# Employee Attrition & Human Capital Predictive Analytics

<p align="center">
  <a href="https://sohail.devsil.com"><strong>Portfolio</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh/employee-attrition-analysis"><strong>Source Repository</strong></a>
</p>

---

## Executive Summary & Problem Statement

Employee turnover imposes massive costs on enterprise organizations: recruiting replacements, onboarding overhead, and lost institutional knowledge cost between 50% to 200% of an employee's annual salary. Human Resources departments often lack data-driven methods to identify flight-risk employees before notice is submitted.

This project implements an enterprise **Employee Attrition Predictive Pipeline**. By evaluating workplace factors (overtime hours, compensation ratios, promotion velocity, managerial relationship tenure), the engine identifies high-risk retention cohorts and quantifies the primary root causes of turnover.

<div align="center">
  <img src="https://raw.githubusercontent.com/sohailahmed-bsrh/myportfolio/main/assets/images/thumbnail/employee-attrition.jpeg" width="650" alt="Employee Attrition Analysis"/>
  <p><em>Human capital retention analytics, class balancing, and attrition driver attribution.</em></p>
</div>

---

## Real-World Industry Applications

- **Proactive Talent Retention**: Flags top-performing talent with elevated turnover risk to HR business partners for retention conversations.
- **Compensation & Overtime Balancing**: Analyzes the exact correlation between mandatory overtime hours and attrition rates across departments.
- **Managerial Effectiveness Tracking**: Identifies departments exhibiting abnormally high turnover rates to improve leadership training.
- **Career Path Planning**: Models the impact of promotion timelines on employee retention across engineering, sales, and operations.

---

## Technical Architecture & Engineering Walkthrough

```
                      [Enterprise Human Resources Dataset]
                                        │
                                        ▼
                      [Feature Engineering & Ratios]
              (Years In Role / Years at Company, Overtime Binary)
                                        │
                                        ▼
                   [Class Imbalance Mitigation (SMOTE / Weights)]
                                        │
         ┌──────────────────────────────┼──────────────────────────────┐
         ▼                              ▼                              ▼
[Logistic Regression]           [Random Forest]                [XGBoost Classifier]
(Interpretable Odds Ratios)   (Non-Linear Tree Splitting)     (Gradient Boosted Ensemble)
         │                              │                              │
         └──────────────────────────────┼──────────────────────────────┘
                                        │
                                        ▼
                    [Feature Attribution & SHAP Global Analysis]
                                        │
                                        ▼
                   [Executive HR Actionable Recommendations]
```

### Step 1: HR Dataset Cleaning & Factor Encoding
Ingests workplace metrics (`notebooks/Employee Attrition Analysis.ipynb`), encoding categorical variables (Department, Job Role, Education Field, OverTime) and normalizing continuous compensation variables.

### Step 2: Advanced Feature Engineering
Constructs critical career trajectory ratios:
- `Tenure_to_Age_Ratio`: Stability indicator.
- `Years_Since_Last_Promotion_Ratio`: Stagnation risk score.
- `Years_With_Current_Manager_Ratio`: Managerial stability.

### Step 3: Addressing Class Imbalance via SMOTE
Employee turnover is inherently unbalanced (e.g., 16% attrition vs 84% retention). Applies Synthetic Minority Over-sampling Technique (SMOTE) to the training split, ensuring the classifier achieves high sensitivity on positive attrition cases.

### Step 4: Machine Learning Model Benchmarking
Evaluates multiple classification estimators (Logistic Regression, Random Forest, XGBoost), optimizing for Recall and F1-Score to catch flight risks before departure.

### Step 5: Root-Cause Attribution via SHAP
Applies SHAP interpretability to rank top turnover drivers across departments, demonstrating that mandatory overtime, low job involvement, and infrequent promotion cycles dominate compensation alone.

---

## Technology Stack & Implementation Specifications

| Component | Technology | Version | Architectural Function |
| :--- | :--- | :--- | :--- |
| **Machine Learning** | Scikit-Learn | 1.3+ | Classifiers, SMOTE integration, ROC-AUC validation |
| **Gradient Boosting** | XGBoost | 2.0+ | Regularized gradient boosted decision trees |
| **Data Engine** | Pandas / NumPy | 2.x | Tabular parsing, dummy encoding, ratio computation |
| **Visualization** | Seaborn / Matplotlib | 3.8+ | Attrition correlation matrices, feature importance plots |

---

## Installation & Execution Guide

```bash
git clone https://github.com/sohailahmed-bsrh/employee-attrition-analysis.git
cd employee-attrition-analysis
python -m venv venv
# Windows: venv\Scriptsctivate | Unix: source venv/bin/activate
pip install -r requirements.txt
jupyter notebook "notebooks/Employee Attrition Analysis.ipynb"
```

---

## Author & Contact Information

<table width="100%">
  <tr>
    <td width="150" align="center" valign="middle">
      <img src="https://avatars.githubusercontent.com/u/231165170?v=4" width="120" style="border-radius: 50%;" alt="Sohail Ahmed"/>
    </td>
    <td>
      <h3>Sohail Ahmed</h3>
      <p><strong>Senior Software Engineer & AI Systems Architect</strong></p>
      <p>Specializing in Full-Stack AI Application Development, Computer Vision, Deep Learning Pipelines, and Scalable Automation Architectures.</p>
      <p>
        <a href="https://sohail.devsil.com"><strong>Portfolio Website</strong></a> | 
        <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
        <a href="https://www.linkedin.com/in/sohail-ahmed-devsil/"><strong>LinkedIn</strong></a> | 
        <a href="https://www.kaggle.com/sohail2411126"><strong>Kaggle</strong></a> | 
        <a href="https://x.com/ahmed241126"><strong>Twitter/X</strong></a> | 
        <a href="mailto:se906403@gmail.com"><strong>Email Contact</strong></a>
      </p>
    </td>
  </tr>
</table>
