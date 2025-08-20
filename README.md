# 🧪 Medical Technologist Projects Portfolio

This repository serves as a collection of tools, dashboards, and workflows I have developed as part of my work as a Medical Technologist. Each project focuses on improving laboratory operations, Point of Care (POC) quality monitoring, and compliance workflows through automation, visualization, or education.

> 🔒 All examples and files included here are de-identified and redacted of PHI or confidential information. These projects reflect process improvement and data management work in a clinical laboratory setting.

---

## 📂 Projects Included

### 1. Chemistry Inventory Expiration Date List
Excel tool to log and track expiration dates of chemistry reagents and supplies.  
- Prevents expired reagents from being used in testing  
- Supports monthly inventory checks and compliance documentation  
- Simplifies ordering and rotation of supplies  

**File:** `Chemistry - Inventory Expiration Date List.xlsx`

---

### 2. Chemistry Usage Table
Excel workbook to track monthly reagent usage across assays.  
- Summarizes reagent consumption by test  
- Assists in forecasting supply needs  
- Identifies abnormal usage trends  

**File:** `Chemistry Usage Table.xlsx`

---

### 3. Microbiology Positivity Tracking Toolkit
End-to-end workflow for microbiology positivity reporting, including raw data cleanup, automated ExcelScript, and dashboards.  
- Raw data export → Automated cleaning script → Clean structured dataset → Dashboard visualizations  
- Saves time during monthly reporting  
- Supports infection control reviews and anomaly detection  

**Files:**  
- `Microbiology - Raw Positivity Data.xlsx`  
- `MicrobiologyRawDataCleaner.ts` (ExcelScript)  
- `Microbiology - Cleaned Data for Positivity by Test.xlsx`  
- `Microbiology - Figures for Positivity by Test.xlsx`  

---

### 4. Nova StatStrip Glucometer Cleaning Poster
Educational poster for POC staff to reinforce correct cleaning and maintenance of Nova StatStrip glucometers.  
- Cleaning protocol with bleach wipes and timing instructions  
- Vial and strip dating guidance  
- Clear instructions for broken meter handling  

**Files:**  
- `Glucometer Cleaning Poster Final June 2025.jpg`  
- `Glucometer Cleaning Poster Final June 2025.pptx`  

---

### 5. Glucose Monitoring Trend Analysis: Poor Perfusion Case Study
Excel-based case study comparing POC glucose values to main lab serum glucose in a poor perfusion patient.  
- Scatterplot visualization of POC vs Lab glucose values  
- Regression analysis to highlight measurement bias  
- Identifies false hypoglycemia events in POC readings  

**Files:**  
- `Patient Study Glucose.xlsx`  
- `Poor Perfusion POC Glucose Study.jpeg`  

---

### 6. Nova Glucometer Error Monitoring Dashboard
Power BI dashboard to monitor Nova glucometer error trends.  
- Tracks error frequency by month, device, operator, and location  
- Uses static monthly test volume table for denominator in error rate calculations  
- Redacted visuals for compliance  

**Files:**  
- `Nova Flagged Occurances.xlsx`  
- `Nova Glucometer Error Dashboard IMG.png`  
- `ReadMe.md`  

**Core visuals:**  
- KPI cards (Total Tests, Errors, Error Rate, Cost of Errors)  
- Error type distribution (Flow Error codes)  
- Location vs error counts  
- Operator vs error counts (redacted)  
- Error count by month  
- Date range slicer for interactivity  

---

### 7. Excel Script: Glucose Data Sorting and Highlighting
Office Script to automate glucose data cleanup for audits.  
- Hides irrelevant columns  
- Sorts results by patient and time  
- Alternates colors for readability  
- Flags low glucose values (<70 mg/dL) with highlighting  

**Use case:** Speeds up POC glucose audits and quality reviews.  

---

### 8. GI Procedure Room Temperature & Humidity Log Processing
Excel Power Query workflow to process raw environment monitoring logs from GI procedure rooms.  
- Consolidates data from multiple rooms into one table  
- Removes null readings automatically  
- Flags out-of-range values for compliance  
- Provides step-by-step guide for staff  

**Files:**  
- `6-June 2025 GI Procedure New MPP - EF.xlsx`  
- `How to Edit and Use GI Procedure E&F New MPP Excel File.docx`  

---

### 9. QML iSTAT Quality Monitoring Dashboard
Power BI dashboard for monitoring iSTAT patient testing data.  
- Identifies quality code trends and device flag behaviors  
- Uses summary counts and static test volumes as denominator  
- Redacted visuals for compliance  

**Files:**  
- `2025 iSTAT Quality Errors.xlsx`
- `iSTAT Quality Error Dashboard IMG 2.png`  
- `ReadMe.md`  

**Highlights:**  
- Error rate calculated with static monthly test volumes  
- Static earliest and latest dates displayed as anchors  
- Drill-through potential for operator and device analysis  

---

## 🛠 Tools & Skills Demonstrated
- Power BI (data modeling, DAX, interactive dashboards)  
- Excel (advanced formulas, pivot tables, charting)  
- Excel Office Scripts (JavaScript-based automation)  
- Power Query (data transformation and consolidation)  
- Educational material creation (PowerPoint, poster design)  
- Clinical data analysis and QA process improvement  

---

## ⚠️ Disclaimer
All examples are based on anonymized or simulated data. No patient identifiable information (PHI) is included in this repository. These projects reflect workflow improvement and monitoring initiatives in a healthcare quality context, not diagnostic interpretation or clinical decision-making.
