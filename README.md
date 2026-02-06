# Bank Loan Portfolio Analysis

## Project Overview

In this project, I worked with a loan-level banking dataset that represents individual consumer loans issued over time. Each record corresponds to a single loan and includes information about the loan amount, repayments, interest rate, borrower profile, loan outcome, and several segmentation attributes such as purpose, state, employment length, and home ownership.

The motivation behind this work was not simply to visualize loan data or compute summary statistics. What I wanted to understand was whether portfolio growth was actually healthy, whether the bank was getting its money back in a sustainable way, and where risk was quietly accumulating beneath headline numbers.

I was less interested in how large the portfolio looked, and more interested in what the portfolio was really doing.


## Project Owner

**Mert Övet**  
Master of Science in Entrepreneurship & Applied Technologies — University of South Florida  

🔗 GitHub: https://github.com/movet306  
🔗 LinkedIn: https://www.linkedin.com/in/mertovet

---

## Problem Definition

As lending volume grows, performance can easily be misread. Rising application counts or funded amounts may appear positive, while repayment quality or risk distribution quietly deteriorates in the background.

The core questions I focused on were:

- Is portfolio growth driven by genuinely performing loans, or by volume that later turns problematic?
- How does the balance between good loans and bad loans evolve over time?
- Are repayments keeping pace with disbursements, or is the bank accumulating latent losses?
- Do risk indicators such as interest rate and debt-to-income ratio remain stable across the portfolio?
- Where does risk concentrate when the portfolio is segmented by borrower profile, geography, purpose, or loan term?

These questions require more than a single dashboard or tool. They require consistent calculations, careful segmentation, and the ability to move from high-level indicators down to individual loan records.

---
## Repository Contents

This repository brings together the same banking loan portfolio analysis across multiple tools, each serving a distinct purpose in the analytical workflow. All files below are directly linked for easy access and review.

### Raw Data
- **Loan-Level Raw Dataset (CSV)**  
  Source dataset containing individual loan records, borrower attributes, loan status, repayment information, and segmentation fields.  
  [financial_loan_raw_data.csv](https://github.com/movet306/bank-loan-performance-risk-analysis/blob/main/financial__loan_raw_data.csv)

### SQL Analysis
- **SQL Queries & Metric Calculations (PDF)**  
  All core KPIs and portfolio metrics were first calculated in SQL Server to ensure accuracy and traceability before moving to analytical tools.  
  This document contains the full set of SQL queries used for validation and aggregation.  
  *File included in repository.*

### Python Analysis
- **Python Portfolio Analysis (Jupyter Notebook)**  
  Detailed analysis of loan performance, good vs bad loan logic, time-based trends, segmentation analysis, and supporting visualizations.  
  This notebook is where portfolio logic and analytical assumptions are explicitly defined and tested.  
  [Mert_Ovet_Bank_loan_python.ipynb](https://github.com/movet306/bank-loan-performance-risk-analysis/blob/main/Mert_Ovet_Bank_loan_python.ipynb)

### Power BI Report
- **Interactive Power BI Dashboard**  
  The reporting layer built on top of validated SQL metrics, allowing dynamic filtering by state, grade, purpose, loan status, and time.  
  Includes Summary, Overview, and Details pages for both high-level monitoring and record-level inspection.  
  [Mert_Ovet_BankLoan_Case.pbix](https://github.com/movet306/bank-loan-performance-risk-analysis/blob/main/Mert_Ovet_BankLoan_Case.pbix)

### Excel Analysis
- **Excel-Based Analysis & Calculations**  
  KPI calculations, pivot-based analysis, and structured views of portfolio metrics implemented in Excel.  
  Serves as an additional validation layer and a familiar analytical format for business users.  
  [financial_loan_data_excel.xlsx](https://github.com/movet306/bank-loan-performance-risk-analysis/blob/main/financial_loan_data_excel.xlsx)

---
## Analytical Approach

### SQL-Based Metric Validation

I started by loading the full dataset into SQL Server and calculating all core metrics directly at the database level. This included total applications, funded amounts, repayments, loan status distributions, and month-to-date comparisons.

This step served two purposes. First, it ensured that all calculations were correct and traceable at the source. Second, it created a reliable baseline so that later analyses in Python and Power BI were grounded in numbers that had already been validated.

---

### Python Analysis and Portfolio Logic

After validating the core metrics, I moved to Python to structure the analytical logic more flexibly.

Loans were explicitly separated into performing and non-performing categories based on loan status. Fully Paid and Current loans were treated as good loans, while Charged Off loans were treated as bad loans. These groups were analyzed not only by count, but also by funded amount and actual cash received, since these perspectives often tell very different stories.

Time-based analysis focused on monthly trends, month-to-date values, and month-over-month changes to distinguish temporary fluctuations from sustained shifts in portfolio behavior.

Beyond time trends, the portfolio was segmented across multiple dimensions including loan purpose, employment length, home ownership, loan term, and geography. The objective was not ranking for its own sake, but understanding how volume and risk interact across different borrower profiles.

Python acted as the space where assumptions were tested, patterns were explored, and analytical logic was refined before being presented visually.

---

### Power BI Reporting Layer

Power BI was used as the final reporting and exploration layer.

The report is structured into three main views:

- **Summary**: High-level portfolio indicators for quick assessment
- **Overview**: Distribution of volume and risk across time, geography, and borrower segments
- **Details**: Loan-level table enabling drill-down from aggregates to individual records

This structure allows different stakeholders to engage with the same data at different depths without changing the underlying calculations.

---

## Key Findings

- The majority of loans are performing, with approximately 86% of applications classified as good loans.
- Total cash received exceeds total funded principal, confirming that interest income functions as expected at the portfolio level.
- Charged-off loans show a sharp drop in recovered amounts, clearly identifying where losses are realized.
- Higher interest rates and higher debt-to-income ratios are consistently associated with poorer loan outcomes.
- Certain purposes, particularly debt consolidation, dominate overall loan volume.
- Renters account for a significant share of applications, and longer employment histories correlate with higher application counts.
- Portfolio activity accelerates toward the second half of the year, with noticeable increases in both application volume and funded amounts.

---

## Why This Project Matters

This project is not about producing dashboards for their own sake. It is about building a clear and defensible view of portfolio performance that connects growth, risk, and cash flow into a single analytical narrative.

By validating calculations in SQL, refining logic in Python, and presenting insights through Power BI, I ensured consistency across tools and transparency in how conclusions were reached.

The structure of this work also allows for further extension, including deeper risk monitoring, cohort-based performance tracking, or early-warning indicators.

---

