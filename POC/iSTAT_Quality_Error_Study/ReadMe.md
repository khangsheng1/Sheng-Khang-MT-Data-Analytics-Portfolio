# QML iSTAT Quality Monitoring Dashboard

This repository contains a Power BI dashboard designed to monitor iSTAT patient testing data exported from QML. The goal of this dashboard is to identify quality code trends, highlight abnormal device behavior, and correlate device flags to testing volumes over time.

![Dashboard_Screenshot]((https://github.com/khangsheng1/Sheng-Khang-MT-Data-Analytics-Portfolio/blob/main/POC/iSTAT_Quality_Error_Study/iSTAT%20Quality%20Error%20Dashboard%20IMG%203.png))

> 🔒 *All usernames, PHI, and confidential data have been redacted from visualizations and source files.*

---

## 📊 Overview

The dashboard utilizes two primary tables to build out visuals:

### **Table 1** – QML Patient Test Data
This table contains patient test result data pulled directly from QML export, enriched with calculated date fields and simplified monthly test volumes.

**Key columns:**
- `Date/Time`
- `Lot`
- `Device`
- `Serial Number`
- `Location`
- `Operator Full Name` *(redacted in this repository)*
- `QltyCode` *(device error flags)*
- `Total # of Tests Ran` *(summary stat from QML — not patient-level data)*
- `Total # of Tests Per Month` *(summary stat from QML)*
- `Week Number`, `Month #`, `MonthName`, `Date`, `Year` *(added for filtering/grouping)*

> Note: Due to the time it takes to export all raw patient-level test results (~20,000+ entries), only summary counts (`Total # of Tests`) are pulled from QML for most use cases.

---

### **Table 2** – Static Test Volume Reference
A manually created static table that provides the total number of tests performed each month. This is used as a denominator when calculating error rates by month.

| Month # | Month              | # of Test Per Month |
| ------- | ------------------ | ------------------- |
| 1       | January            | 2873                |
| 2       | February           | 2671                |
| ...     | ...                | ...                 |
| 8       | August             | 584                 |
| 9 - 12  | September–December | 0 (placeholder)     |

---

## 🧮 Key Measures

These DAX measures were developed to support tracking of errors and calculating stable date anchors:

### **Static Date Anchors**
```DAX

Earliest Date (Static) = 
CALCULATE(
    MIN('Table1'[Date/Time]),
    ALL('Table1')
)

Latest Date (Static) = 
CALCULATE(
    MAX('Table1'[Date/Time]),
    ALL('Table1')
)
```

Earliest Date and Latest Date are displayed as static cards on the report — they do not change with slicer or visual filters, which is useful when users interact with the rest of the dashboard.

### **Error Rate Calculation**
```
Total Tests = 
VAR MonthsVisible = 
    SUMMARIZE(
        'Table1',
        'Table1'[Year],
        'Table1'[Month #]
    )

RETURN
CALCULATE(
    SUM('Table2'[# of Test Per Month]),
    TREATAS(
        MonthsVisible,
        'Table2'[Year],
        'Table2'[Month #]
    )
)

Calculation = [Count of QltyCode] / [Total Tests]
```
This measure divides the number of flagged quality events (QltyCode) by the total number of tests for the corresponding month from Table 2, allowing error rate tracking over time.

**Data Model Considerations**

| From Table | Column    | → | To Table  | Column         | Type        |
| ---------- | --------- | - | --------- | -------------- | ----------- |
| Table1     | `Month #`    | → | Table 2 | `Month #`         | Many to One |


- **Filter direction**: Single direction from Table2 → Table1 

- **Important**: Ensure DateTable has unique values and that relationships are one-to-many for stable filtering.

📌 **Notes**
The included dashboard screenshot (dashboard_screenshot.png) provides a high-level view of the layout and measures.

Built entirely in Power BI Online.

All data modeling, calculations, and formatting were done manually for flexibility and transparency.

Includes redacted visuals to ensure privacy and HIPAA compliance.

⚠️ **Limitations**
Patient-level data is partially sampled for performance and feasibility

Manual data extraction from QML—there’s no automated export method

Table2 (monthly test volumes) is static and must be updated manually

Relationships between tables may require fine-tuning if new sources are added

🚀 **Future Improvements**
Integrate an API-based export from QML to fully automate Table1 extraction

Automate Table2 population from master instrument logs or LIS exports

Add dynamic annotations or alerts when monthly error rate exceeds threshold

Enable drill-through report on operator and device performance

🛠 **Tools Used**
Power BI Online

DAX

QML Export

Excel (pre-processing)

Optional clipart/icons designed using Sora and PowerPoint

🔒 **Disclaimer**
This dashboard was created using anonymized, de-identified data for internal quality improvement purposes. All operator names have been redacted. No patient-identifiable information was used or shared. This dashboard does not reflect diagnostic performance or patient care outcomes.
