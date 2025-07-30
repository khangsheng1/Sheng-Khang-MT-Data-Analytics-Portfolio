# GI Procedure Room Temperature & Humidity Log Processing

This repository contains resources and guidance for processing **temperature and humidity logs** from GI procedure areas across facilities, using Power Query for automated data cleanup and compliance checking. This workflow supports Point of Care (POC) operations, ensuring environment monitoring data is consistent, clean, and regulatory-ready.

---

## 📁 Files Included

### 1️⃣ Raw Temperature & Humidity Logs

**File:** `6-June 2025 GI Procedure New MPP - EF.xlsx`

- Raw environment monitoring data submitted by GI procedure areas.
- Includes humidity (%RH) and temperature (°F) readings from:
  - GI Procedure E
  - GI Procedure F
  - GI South NS
- Data may include empty/null readings and unorganized timestamps.

---

### 2️⃣ Instructions Document

**File:** `How to Edit and Use GI Procedure E&F New MPP Excel File.docx`

Step-by-step instructions for cleaning and processing the raw logs using **Power Query** in Excel.

**Key Steps Covered:**
- Load raw data into Power Query.
- Apply a custom grouping function to consolidate readings by timestamp.
- Automatically remove empty/null values.
- Output a cleaned dataset for compliance checking.
- Use Excel formulas to flag out-of-range readings.

Includes guidance for:
- Renaming sheets.
- Formatting for printing.
- Marking non-compliant temperature/humidity records.

---

## 🛠️ Processing Workflow

### Power Query Grouping Function

In Power Query, after selecting the raw table:
- Use the grouping function provided in the instructions document to consolidate readings by timestamp and remove nulls.

```m
= Table.Group(Source, {"Timestamp"}, {
    {"GI Procedure E RH(%RH)", each List.Max(List.Select([#"GI Procedure E RH(%RH)"], each _ is number)), type nullable number},
    {"GI Procedure E Temp(°F)", each List.Max(List.Select([#"GI Procedure E Temp(°F)"], each _ is number)), type nullable number},
    {"GI Procedure F RH(%RH)", each List.Max(List.Select([#"GI Procedure F RH(%RH)"], each _ is number)), type nullable number},
    {"GI Procedure F Temp(°F)", each List.Max(List.Select([#"GI Procedure F Temp(°F)"], each _ is number)), type nullable number},
    {"GI South NS RH(%RH)", each List.Max(List.Select([#"GI South NS RH(%RH)"], each _ is number)), type nullable number},
    {"GI South NS Temp(°F)", each List.Max(List.Select([#"GI South NS Temp(°F)"], each _ is number)), type nullable number}
})
