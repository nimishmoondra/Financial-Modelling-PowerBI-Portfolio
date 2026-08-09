# Corporate Financial Analytics & Valuation Portfolio

This repository contains interactive financial reporting dashboards built in Power BI, supported by dynamic DAX measures, general ledger analysis, and full-scope M&A valuation models in Excel.

---

## 📌 Project 1: Infosys Ltd M&A Valuation & Executive Dashboard

### 🎯 Overview
Engineered an interactive capital markets reporting dashboard and full-scope buy-side valuation model (DCF, Comparable Company Analysis, LBO) to evaluate corporate capital structure and financial performance.

### 🛠️ Technical Stack
* **Business Intelligence:** Power BI Desktop (DAX, Data Transformation, Custom Tooltips)
* **Financial Modelling:** Advanced Excel (Dynamic 3-Statement, DCF, LBO, Sensitivity Matrices)
* **Data Ingestion:** Automated data workflows and general ledger reconciliation

### 📊 Dashboard Preview
![Dashboard Preview](Dashboards/infosys_dashboard_preview.png)
*(Replace 'Dashboards/infosys_dashboard_preview.png' with the exact file path of your uploaded screenshot)*

### 💡 Key DAX Measures & Logic Implemented
```dax
// Dynamic Debt-to-Equity Ratio
Debt_to_Equity = 
DIVIDE(
    SUM('Balance Sheet'[Total Debt]), 
    SUM('Balance Sheet'[Total Equity]), 
    0
)

// Rolling 12-Month Cash Flow Forecasting
Rolling_12M_CashFlow = 
CALCULATE(
    SUM('Cash Flow'[Operating Cash Flow]),
    DATESINPERIOD('Calendar'[Date], MAX('Calendar'[Date]), -12, MONTH)
)
