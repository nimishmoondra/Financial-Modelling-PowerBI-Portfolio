# Corporate Financial Analytics & Valuation Portfolio

This repository contains full-scope financial modelling frameworks (3-Statement, DCF, LBO) in Excel alongside data transformation scripts and DAX measures developed for Power BI financial reporting.

---

## 📌 Project 1: Infosys Ltd M&A Valuation & Financial Analytics

### 🎯 Overview & Objectives
Engineered a comprehensive financial framework for Infosys Ltd to simulate buy-side M&A structuring, evaluate capital structure efficiency, and track dynamic corporate KPIs. 

### 🛠️ Core Capabilities Demonstrated
* **Financial Modelling:** Dynamic 3-Statement Model, Discounted Cash Flow (DCF) Valuation, Leveraged Buyout (LBO) Analysis, Accretion/Dilution Analysis, and Sensitivity Matrices.
* **Data Analytics & BI:** Power BI Data Transformation (Power Query), General Ledger Reconciliation, and Custom DAX Measure Development.

### 💡 Key DAX Calculations & Financial Logic

#### 1. Dynamic Capital Structure (Debt-to-Equity Ratio)
```dax
Debt_to_Equity = 
DIVIDE(
    SUM('Balance Sheet'[Total Debt]), 
    SUM('Balance Sheet'[Total Equity]), 
    0
)
Rolling_12M_CashFlow = 
CALCULATE(
    SUM('Cash Flow'[Operating Cash Flow]),
    DATESINPERIOD('Calendar'[Date], MAX('Calendar'[Date]), -12, MONTH)
)
Interest_Coverage_Ratio = 
DIVIDE(
    [EBIT], 
    SUM('Income Statement'[Interest Expense]), 
    0
)
