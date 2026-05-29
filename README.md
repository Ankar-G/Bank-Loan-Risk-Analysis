# 🏦 Loan Default Risk & Customer Segmentation Analysis

> An end-to-end data analytics project using Python and Power BI to identify high-risk borrowers, understand customer financial behavior, and reduce loan default losses through intelligent customer segmentation.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Problem Statement](#problem-statement)
- [Business Objectives](#business-objectives)
- [Project Workflow](#project-workflow)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Engineering](#feature-engineering)
- [Customer Segmentation](#customer-segmentation)
- [Business KPIs](#business-kpis)
- [Power BI Dashboard](#power-bi-dashboard)
- [Key Insights](#key-insights)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [How to Run](#how-to-run)
- [Dashboard Preview](#dashboard-preview)

---

## 📖 Project Overview

Banks and financial institutions face significant losses every year due to loan defaults. This project builds a full analytics pipeline — from raw data to an interactive Power BI dashboard — to help decision-makers:

- **Identify** customers most likely to default before it happens
- **Segment** customers based on financial behavior using machine learning
- **Improve** loan approval decisions with data-driven risk scoring
- **Reduce** financial losses by targeting high-risk profiles early

---

## ❓ Problem Statement

- Which customers are most likely to default on their loans?
- What types of customer segments exist based on financial behavior?
- How can we identify risky customer profiles proactively?
- How can we improve loan approval decisions using data?

---

## 🎯 Business Objectives

| Objective | Description |
|---|---|
| Default Detection | Identify factors contributing to loan default |
| Risk Profiling | Analyze the relationship between credit score, income, DTI ratio, and loan status |
| Behavioral Analysis | Understand payment behavior patterns across customer types |
| Customer Segmentation | Group customers into actionable segments for targeted strategies |
| Business Intelligence | Build an interactive dashboard tracking 9 business KPIs |

---

## 🔄 Project Workflow

```
Raw Data
   ↓
Data Cleaning & Preprocessing
   ↓
Exploratory Data Analysis (EDA)
   ↓
Feature Engineering
   ↓
K-Means Customer Segmentation
   ↓
Business KPI Calculation
   ↓
Power BI Dashboard (5 Pages)
```

---

## 🔍 Exploratory Data Analysis (EDA)

### Customer Analysis
- Age group distribution across borrowers
- Income distribution (Low / Middle / High)
- Credit score distribution and spread
- Employment type counts (salaried, self-employed, freelancer, business owner, unemployed)

### Loan Analysis
- Loan status distribution (active, closed, default)
- Loan type breakdown (personal, home, vehicle, business, education)
- Average loan amount and average interest rate by type

### Transaction Analysis
- Payment status distribution (paid, late, missed)
- Monthly payment trends across the year
- Failed and missed payment counts by segment

---

## ⚙️ Feature Engineering

New features created to improve risk detection and segmentation:

### 1. Customer Risk Category (based on Credit Score)
| Category | Credit Score Range |
|---|---|
| Poor | Below 580 |
| Fair | 580 – 669 |
| Good | 670 – 739 |
| Excellent | 740 and above |

### 2. Income Group
| Group | Description |
|---|---|
| Low Income | Bottom tier annual income |
| Middle Income | Mid-range annual income |
| High Income | Top tier annual income |

### 3. Employment Stability Score
- Derived from `Years_of_Employment`
- Categorized into stability buckets (0, 10, 20, 30+ years)

### 4. Payment Behavior Score
- Computed from: missed payments + late payments + successful payments
- Results in: **Good Payer**, **Moderate Payer**, **Risky Payer**

### 5. High Risk Flag
A binary flag raised when a customer meets any of the following conditions:
- Credit score < 600
- DTI ratio > 40%
- Multiple missed payments

---

## 👥 Customer Segmentation

**Algorithm:** K-Means Clustering

**Features used for clustering:**
- Annual Income
- Credit Score
- Loan Amount
- Debt-to-Income (DTI) Ratio

**Segments identified:**

| Segment | Share | Avg Credit Score | Avg Income | Avg Loan Amount | DTI |
|---|---|---|---|---|---|
| Reliable Customers | 25.09% | 749 | 91.76K | 1.2M | 1.15% |
| Medium Risk Customers | 10.06% | 619 | 133.75K | 1.2M | 1.15% |
| High DTI Risk Customers | 64.86% | 710 | 83.36K | 1.6M | 93.25% |

---

## 📊 Business KPIs

| KPI | Value |
|---|---|
| Total Customers | 1,012 |
| Total Loan Amount | $58.81 Billion |
| Total Amount Received | 601.75 Million |
| Avg Loan Amount | 1.23 Million |
| Avg Credit Score | 707.53 |
| Default Rate | 8.63% |
| Total Payments | 601.75 Million |
| Missed Payment % | 8.78% |
| Avg Debt-to-Income Ratio | 9.11% |

---

## 📈 Power BI Dashboard

The dashboard contains **5 interactive pages**, each with filters for Loan Type, Customer Segment, and Payment Status.

### Page 1 — Executive Summary
> Overview of key loan performance metrics and insights

High-level portfolio health: total customers, loan amount, amount received, average credit score, and default rate. Includes loan status distribution, loan type breakdown, risk category distribution, and monthly payment trend (2020–2024).

### Page 2 — Customer Analysis
> Detailed insight about our customers and their demographic profile

Borrower demographics: average income (103.38K), DTI ratio (9.11%), age (44.55). Covers income distribution, credit score histogram, employment type mix, age group distribution, gender split, and employment stability.

### Page 3 — Loan Risk Analysis
> Default risk patterns, credit behavior and high-risk customer identification

330 high-risk customers (32.61%) and 731 high DTI customers (72.23%). Features credit score vs. loan amount scatter plot, risk category loan amounts, interest rates by loan type, default rates by loan type, and high-risk segment breakdown.

### Page 4 — Transaction & Payment Analysis
> Track payment behaviors, trends and missed payments

4,198 missed payments (8.78%). Covers payment behavior categories (Good / Moderate / Risky payer), average payment by month, payment status by loan type, monthly payment volume, and missed payment trend.

### Page 5 — Customer Segmentation
> Understand customer segmentation and compare risk, income, loan amount and credit behavior

K-Means output: segment-wise comparisons for credit score, income, loan amount, DTI ratio, and a risk comparison matrix across credit categories (Excellent / Fair / Good / Poor).

---

## 💡 Key Insights

- **8.63% default rate** — 417 customers flagged as defaulted out of 975 filtered
- **64.86% of customers** fall in the High DTI Risk segment — the largest and most concerning group
- **Business loans** have the highest default rate at **9.92%**, followed by home (9.33%) and education (9.29%)
- Only **68.49% of payments** are made on time; 18.77% are late and 8.78% are missed entirely
- **Reliable customers** have an average credit score of **749** vs **619** for medium-risk customers
- **Personal loans** carry the highest average interest rate at **13.6%**
- The majority of borrowers (**60.08%**) fall in the middle income bracket
- Most borrowers are in their **40s** (379 customers), followed by 50s (189) and 30s (173)

---

## 🛠️ Tech Stack

| Tool / Library | Purpose |
|---|---|
| Python | Core programming language |
| Pandas | Data manipulation and cleaning |
| NumPy | Numerical computations |
| Matplotlib & Seaborn | EDA visualizations |
| Scikit-learn | K-Means clustering, preprocessing |
| Power BI | Interactive dashboard and reporting |
| DAX | Custom KPI measures in Power BI |
| Jupyter Notebook | Analysis environment |

---

## 📁 Project Structure

```
loan-default-risk-analysis/
│
├── data/
│   ├── raw/                  # Original dataset
│   └── processed/            # Cleaned and feature-engineered data
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_feature_engineering.ipynb
│   └── 04_kmeans_segmentation.ipynb
│
├── powerbi/
│   └── bank_loan_report.pbix  # Power BI dashboard file
│
├── images/
│   ├── executive_summary.png
│   ├── customer_analysis.png
│   ├── loan_risk_analysis.png
│   ├── transaction_payment.png
│   └── customer_segmentation.png
│
├── requirements.txt
└── README.md
```

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/loan-default-risk-analysis.git
cd loan-default-risk-analysis
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebooks in order
```bash
jupyter notebook notebooks/01_data_cleaning.ipynb
```
Run notebooks 01 → 02 → 03 → 04 sequentially.

### 4. Open the Power BI dashboard
Open `powerbi/bank_loan_report.pbix` in Power BI Desktop.
Connect it to the processed data file in `data/processed/`.

---

## 🖼️ Dashboard Preview

| Page | Preview |
|---|---|
| Executive Summary | ![Executive Summary](images/executive_summary.png) |
| Customer Analysis | ![Customer Analysis](images/customer_analysis.png) |
| Loan Risk Analysis | ![Loan Risk Analysis](images/loan_risk_analysis.png) |
| Transaction & Payment Analysis | ![Transaction & Payment](images/transaction_payment.png) |
| Customer Segmentation | ![Customer Segmentation](images/customer_segmentation.png) |

---

## 🤝 Connect With Me

If you found this project helpful or have feedback, feel free to connect:

- 💼 [LinkedIn](https://www.linkedin.com/in/ankar-goswami-23a196245/)
- 📧 goswamijit99@gmail.com

---

> ⭐ If you found this project useful, please give it a star — it helps others discover it!
