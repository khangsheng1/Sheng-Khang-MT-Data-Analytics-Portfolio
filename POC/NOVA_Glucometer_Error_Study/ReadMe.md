# Nova Glucometer Error Monitoring Dashboard

This repository contains a Power BI dashboard that tracks Nova glucometer error events and monthly testing volumes. The goal is to surface error trends, highlight locations and operators with higher error counts, and place those counts in context with total tests by month.

![Dashboard_Screenshot](https://github.com/khangsheng1/MT-Work/blob/main/POC/NOVA_Glucometer_Error_Study/Nova%20Glucometer%20Error%20Dashboard%20IMG.png)

> 🔒 All usernames, PHI, and confidential data are redacted in screenshots and source files.

---

## Repository contents

1. `Nova Flagged Occurances.xlsx`  
   Sample export with flagged events used to build the report  
2. `Nova Glucometer Error Dashboard IMG.png`  
   Screenshot of the Power BI report  
3. `ReadMe.md`  
   This document  

---

## Overview

The dashboard uses an event table for flagged tests and a small reference table for monthly test counts. This lets you compute both absolute counts and error rates per month, location, device, and operator.

---

## Data model

**Tables in use**

### Table1 — Flagged events from Nova export
Event level rows with one record per flagged test.

Key columns  
- `Date/Time`  
- `Flow Error` (error code or text)  
- `Device`  
- `Location`  
- `Operator Full Name` (redacted in this repository)  
- Helper date fields used for grouping and filtering: `Date`, `Year`, `Month #`, `MonthName`

### Table2 — Monthly total test counts
A static reference table with the total number of tests performed each month. This acts as the denominator for error rate.

Columns  
- `Year`  
- `Month #`  
- `Month`  
- `# of Test Per Month`  
- `Total Tests` (optional, can mirror # of Test Per Month)

**Relationships**

| From table | Column   | → | To table | Column   | Cardinality | Direction |
|------------|----------|---|----------|----------|-------------|-----------|
| Table1     | Month #  | → | Table2   | Month #  | Many to one | Single    |

---

## Measures

### Static date anchors
Displayed as cards that do not respond to slicers. Useful for showing the overall dataset range.

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

### Total tests that respect the date slicer

Maps visible months in the current filter context to the monthly totals in Table2. Works even if the slicer is on DateTable.

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
```
### Error count

```
Error Rate % = DIVIDE([Count of Flow Error1],[Total Tests])
```

## Core visuals
