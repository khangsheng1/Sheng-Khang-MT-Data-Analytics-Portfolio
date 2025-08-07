# QML iSTAT Quality Monitoring Dashboard

This repository contains a Power BI dashboard designed to monitor iSTAT patient testing data exported from QML. The goal of this dashboard is to identify quality code trends, highlight abnormal device behavior, and correlate device flags to testing volumes over time.

![Dashboard Screenshot](dashboard_screenshot.png)

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
- `Operator Full Name`
- `QltyCode` *(device error flags)*
- `Total # of Tests Ran` *(summary stat from QML — not patient-level data)*
- `Total # of Tests Per Month` *(summary stat from QML)*
- `Week Number`, `Month #`, `MonthName`, `Date` *(added for filtering/grouping)*

> Note: Due to the time it takes to export all raw patient-level test results (~20,000+ entries), only summary counts (`Total # of Tests`) are pulled from QML for most use cases.

---

### **Table 2** – Static Test Volume Reference
A manually created static table that provides the total number of tests performed each month. This is used as a denominator when calculating error rates by month.

| Month              | Month # | # of Test Per Month |
| ------------------ | ------- | ------------------- |
| January            | 1       | 2873                |
| February           | 2       | 2671                |
| ...                | ...     | ...                 |
| August             | 8       | 584                 |
| September–December | 9–12    | 0 (placeholder)     |


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

These are displayed as static cards on the report — they do not change with slicer or visual filters, which is useful when users interact with the rest of the dashboard.

Quality Issue Rate

Calculation = [Count of QltyCode] / [Sum of # of Test Per Month]

This measure divides the number of flagged quality events (QltyCode) by the total number of tests for the corresponding month from Table 2, allowing error rate tracking over time.

🔗 Data Model Considerations
Relationships:
Table1 → Date Table: Many-to-many (due to multiple patient tests per date)

Table2 → Date Table: Many-to-one (used as a lookup for static test counts)

⚠️ Having different cardinality between the Date Table and the two sources can cause filters not to propagate consistently, especially when interacting with visuals from different tables. It’s best to ensure:

The Date Table has unique date values

Relationships are one-to-many (Date → Table1, Date → Table2) if possible

Filter direction is set appropriately (usually single direction unless there's a strong case)

📌 Notes
The dashboard screenshot (dashboard_screenshot.png) is included for quick reference.

Data has been sanitized for privacy.

Built entirely in Power BI Online.

All measures, data transformations, and formatting were created by hand to ensure accuracy and maintainability.

🛠 Tools Used
Power BI Online

DAX

QML Export

Excel (pre-processing)

Optional clipart/icons designed using Sora and PowerPoint
