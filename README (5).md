# Credit Card Portfolio Profitability & Revenue Leakage Analysis

## Executive Summary

A retail bank's credit-card portfolio generated **₹50.38M in revenue** and **₹17.63M in net profit** across **10,000 customers over 12 months**, but profitability was constrained by high cashback/reward costs and delinquency exposure.

This project uses **SQL and Power BI**, supported by Excel-based validation, to identify the portfolio's most profitable products, major cost drivers, customer value segments, and credit-risk concentrations.

The analysis is designed around one management question:

> **How can the bank improve credit-card portfolio profitability without increasing customer or credit risk?**

---

## Business Problem

Portfolio growth does not automatically translate into stronger profitability. Rising cashback and reward costs, fee waivers, and customer delinquency can reduce the economic value of otherwise high-spending customers.

Management needs to understand:

- Which card products generate the strongest profit margins?
- Which revenue streams contribute most to portfolio performance?
- Which costs are reducing profitability?
- Which customer segments are most valuable?
- Where is delinquency concentrated?
- Which customers should be retained, upgraded, or monitored?

---

## Key Results

| KPI | Result |
|---|---:|
| Customers | 10,000 |
| Analysis period | 12 months |
| Transactions | 150,000+ |
| Total revenue | **₹50.38M** |
| Net profit | **₹17.63M** |
| Profit margin | **34.99%** |
| Interchange revenue | **₹17.75M** |
| Cashback cost | **₹19.78M** |
| Delinquency rate | **15.23%** |
| 90+ DPD customers | **571** |

> **Important:** Financial metrics are based on the simulated portfolio dataset included in this repository.

---

## Dataset & Data Model

The analysis uses four related tables:

- **Cardholders** — customer, card type, income segment and demographic attributes
- **Transactions** — transaction amount, category, merchant and transaction activity
- **Billing** — revenue and cost components used for portfolio profitability
- **Delinquency** — DPD bucket, outstanding balance and credit-risk information

### Relationship structure

```text
Cardholders
    │
    ├────────────── Transactions
    │
    ├────────────── Billing
    │
    └────────────── Delinquency
```

### Dataset scale

- 10,000 cardholders
- 150,000+ transactions
- 12 months of portfolio activity
- 4 analytical tables

---

## Analytical Approach

### 1. Portfolio Profitability

- Total revenue
- Total cost
- Net profit
- Profit margin
- Monthly profitability trend

### 2. Product & Customer Profitability

- Profit by card type
- Profit margin by card type
- Customer profitability
- Income-segment performance
- City-level profitability

### 3. Revenue & Cost Leakage

- Cashback cost
- Reward cost
- Fee-waiver cost
- Cost contribution to the portfolio
- Leakage/cost drivers affecting profitability

### 4. Credit Risk

- Delinquency rate
- DPD-bucket analysis
- Outstanding balance exposure
- High-risk customer concentration
- Credit utilization

### 5. Spending Behaviour

- Spending-category analysis
- Transaction trends
- Customer value
- Category-level spend

---

## Key Business Findings

### 1. Strong overall profitability, but meaningful cost pressure

The portfolio generated **₹50.38M revenue** and **₹17.63M net profit**, resulting in a **34.99% profit margin**. Cashback was the largest individual cost component at **₹19.78M**, making reward economics a major profitability lever.

### 2. Interchange is a major revenue engine

**₹17.75M** came from interchange revenue, representing **35.23% of total revenue**. This highlights the importance of sustained customer transaction activity to portfolio economics.

### 3. Platinum has the strongest margin economics

**Platinum cards delivered a 47.78% profit margin**, compared with **25.47% for Classic cards**. Classic generated the highest revenue (**₹21.46M**) but converted revenue into profit less efficiently.

### 4. Delinquency creates concentrated credit-risk exposure

The portfolio's delinquency rate was **15.23%**, with **571 customers in the 90+ DPD bucket**. These accounts represent the most severe observed delinquency segment and should be prioritized for risk intervention.

### 5. Spending behaviour matters more than geography for portfolio strategy

The analysis indicates that customer spending behaviour is a more actionable segmentation dimension than simply comparing locations. Product and reward strategies should therefore be linked to profitable spending patterns and customer economics.

---

## Business Recommendations

### 1. Optimize cashback on low-margin spending

Review cashback economics for categories and customer segments where reward cost materially reduces profit. Preserve incentives where they drive profitable transaction activity rather than applying broad cashback offers.

### 2. Upgrade profitable Classic customers

Identify high-spending, low-risk Classic cardholders and evaluate targeted Gold/Platinum upgrade offers. The objective is to migrate valuable customers toward products with stronger unit economics while maintaining retention.

### 3. Introduce early delinquency intervention

Prioritize customers entering Watchlist and early-DPD stages for payment reminders, proactive outreach and suitable repayment/EMI interventions before accounts migrate into more severe delinquency buckets.

### 4. Tighten fee-waiver governance

Review fee-waiver eligibility and approval patterns to reduce avoidable revenue loss while protecting retention for genuinely high-value customers.

### 5. Manage rewards using customer profitability

Move from broad reward programs toward segment-based offers using transaction value, product profitability and risk. This can improve reward efficiency without unnecessarily reducing customer engagement.

---

## Dashboard

The Power BI dashboard contains five analytical pages.

### Page 1 — Executive Portfolio Overview

Executive view of revenue, profit, margin, revenue composition, product profitability and portfolio-risk KPIs.

<img width="903" height="506" alt="Executive Portfolio Overview" src="https://github.com/user-attachments/assets/a34af390-8361-49ac-b9df-cde65659996b" />

### Page 2 — Product Profitability & Revenue Leakage

Compares Classic, Gold and Platinum profitability and highlights cashback, reward and fee-waiver cost drivers.

<img width="903" height="512" alt="Product Profitability and Revenue Leakage" src="https://github.com/user-attachments/assets/26063535-c88b-436b-acc6-8d80d03f6143" />

### Page 3 — Risk & Delinquency

Examines DPD buckets, outstanding-balance exposure and customer risk concentration.

<img width="876" height="488" alt="Risk and Delinquency" src="https://github.com/user-attachments/assets/496d2adb-678f-4b72-9dc5-d4f86364" />

### Page 4 — Portfolio Health

Analyzes portfolio-health distribution, watchlist customers, high-risk accounts and credit utilization.

<img width="894" height="501" alt="Portfolio Health" src="https://github.com/user-attachments/assets/b06cf9a3-9a42-409a-a626-64298dd9d931" />

### Page 5 — Customer & Spend Behaviour

Explores customer profitability, spending categories, city-level performance and transaction behaviour.

<img width="908" height="514" alt="Customer and Spend Behaviour" src="https://github.com/user-attachments/assets/470a97ca-9a53-486c-85ea-d42b96464c7b" />

---

## Technical Skills Demonstrated

**SQL:** Joins, CTEs, aggregations, CASE expressions, subqueries and window functions  
**Power BI:** Data modelling, DAX, KPI design, interactive dashboards and business storytelling  
**Excel:** Data validation and exploratory analysis  
**Analytics:** Profitability analysis, customer segmentation, cost-driver analysis and credit-risk analysis

---

## Repository Structure

```text
├── Dataset/
├── creadit analysis.sql
├── Credit Card Portfolio Profitability & Revenue Leakage Analysis.pbix
├── Dashboard screenshots
└── README.md
```

> The SQL script currently contains local MySQL file paths used during development. These paths may need to be updated for another environment before executing the data-load statements.

---

## Project Outcome

The analysis converts transaction, billing and delinquency data into a management view of **profitability, cost leakage and credit risk**. The resulting recommendations focus on improving reward efficiency, targeting profitable customers, strengthening early delinquency intervention and protecting portfolio margins.

**Tools:** SQL (MySQL) · Power BI · Excel · GitHub  
**Domain:** Banking / BFSI · Credit Cards · Portfolio Analytics
