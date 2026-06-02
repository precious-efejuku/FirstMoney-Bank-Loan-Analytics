# FirstMoney-Bank-Loan-Analytics
End-to-end data analytics project: data cleaning in Excel, SQL querying, and Power BI dashboard for a retail bank's loan performance review.
# FirstMoney Bank — Branch Loan Sales & Repayment Analytics

## Project Overview

FirstMoney Bank operates 10 retail branches across Lagos, Abuja, Port Harcourt, and Kano. After a **12% rise in loan defaults** last quarter, the Head of Retail Banking commissioned an urgent review of the bank's loan sales and repayment data.

This project delivers a full-cycle analytics solution — from raw data cleaning to an executive dashboard — answering seven key business questions about branch performance, default patterns, and repayment trends.

## Business Questions Addressed

1. Which branches are over- or under-performing on loan volume?
2. Which branches have the worst default rates?
3. Who are the top 5 Relationship Managers by total loan value?
4. What is the loan product mix (Personal, Business, SME)?
5. How has monthly repayment collection changed over the year?
6. Which RMs have met, exceeded, or missed their annual targets?
7. Is there a pattern between customer segment and loan default rates?

## Dataset

| Table | Rows | Description |
|-------|------|-------------|
| Branches | 10 | Branch details (name, city, region) |
| Staff | 20 | Relationship Managers and annual targets |
| Customers | 250 | Customer profiles and segments |
| Loans | ~500 | Loan disbursements (main fact table) |
| Repayments | ~5,600 | Monthly repayment records |

**Total loan value:** ₦1.78 Billion across 500 loans

## Tools Used

- **Microsoft Excel** — Data cleaning, VLOOKUP/XLOOKUP, pivot tables, conditional formatting
- **SQL** — JOINs, CTEs, subqueries, aggregations, default rate analysis
- **Power BI** — DAX measures, data modelling, interactive dashboard with slicers

## Project Phases

### Phase 1: Data Cleaning & Exploration (Excel)

- Inspected all five datasets and documented issues in a Cleaning Log
- Removed duplicate rows from loans and repayments tables
- Fixed data type errors (dates stored as text, inconsistent formatting)
- Filled missing age values using median age by customer segment
- Enriched the loans table with branch names, RM names, and targets using XLOOKUP
- Built 3 pivot tables and applied conditional formatting to a performance flag column

> See [`Cleaning log Screenshot.png`](Cleaning%20log%20Screenshot%20.png) and [`Pivot table Screenshot.png`](Pivot%20table%20Screenshot%20.png) in this repository.

### Phase 2: SQL Querying & Analysis

Wrote 7 queries covering:

- Loan summary by type (aggregation)
- High-value defaulted loans (filtering)
- Lagos region loans (JOIN between loans and branches)
- Default rate by branch (aggregation with CASE)
- Top 5 RMs by disbursement with target attainment (multi-table JOIN)
- Monthly repayment trend with on-time rate (date extraction, aggregation)
- Customer segment default analysis (3-table JOIN with GROUP BY)

> See [`queries.sql`](queries.sql) for all labelled queries.

### Phase 3: Power BI Dashboard

Built a single-page **Loan Performance Dashboard** with:

- **4 KPI cards:** Total Loans Disbursed, Total Number of Loans, Total Repayments Collected, Default Rate %
- **5 chart types:** Clustered bar (loan volume by branch), Donut (loans by type), Clustered bar (loan status), Line (monthly repayments), Stacked bar (default rate by segment and region)
- **2 slicers:** Region and Loan Type (filtering all visuals)
- **6 DAX measures** in a dedicated measures table
- **Written commentary** with the key insight and a recommended action

> See [`dashboard-screenshot.pdf`](dashboard-screenshot.pdf) for the full dashboard.

## Key Findings

| Metric | Value |
|--------|-------|
| Total Loans Disbursed | ₦1.78B |
| Total Loans Issued | 500 |
| Total Repayments Collected | ₦1.03B |
| Overall Default Rate | 13.8% |
| Highest Default Region | North (~40%) |
| Most Affected Segment | SME customers |
| Top Branch by Volume | Maitama (₦300M+) |
| Lowest Branch by Volume | Wuse II (₦27M) |

## Recommendations

1. **Immediate:** Credit review of all active SME loans above ₦2M in the North region
2. **This quarter:** Tighten SME loan approval criteria with stricter checks
3. **Next quarter:** Investigate and support the bottom 3 branches (Wuse II, Port Harcourt GRA, Victoria Island)
4. **Ongoing:** Monthly dashboard review via Power BI to track trends

## Repository Contents

```
├── README.md                      ← You are here
├── queries.sql                    ← All 7 SQL queries (labelled Q1–Q7)
├── dashboard-screenshot.pdf       ← Power BI dashboard export
├── Cleaning log Screenshot.png    ← Excel data cleaning log
├── Pivot table Screenshot.png     ← Excel pivot table analysis
└── presentation-slides.pptx       ← Final presentation to stakeholders
```

## About Me

**Precious Oritsela Efejuku**
Sociology graduate transitioning into data analytics. This project was completed as the capstone for the TESA Data Analytics Program (Univaciti, Cohort 5) in April 2026.

- Email: precious.efejuku@gmail.com
- LinkedIn: www.linkedin.com/in/precious-efejuku
- Location: Lagos, Nigeria
