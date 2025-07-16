# Microbiology Positivity Tracking Toolkit

This repository contains tools and templates developed for tracking and reporting **microbiology test positivity rates**. These resources streamline the process of cleaning raw data, preparing it for analysis, and visualizing test positivity trends.

---

## 📁 Files Included

### 1️⃣ Raw Data

**File:** `Microbiology - Raw Positivity Data.xlsx`

- This file contains the unprocessed data exported directly from laboratory reporting systems.
- Raw format includes extra header rows, mixed content, and unstructured test results.
- Intended as the starting point before cleaning.

---

### 2️⃣ Data Cleaning Script

**File:** `MicrobiologyRawDataCleaner.ts` (ExcelScript)

**Purpose:**  
Automates cleanup of raw microbiology data to create a structured, tabular dataset.

**Key Functions:**  
- Clears all formatting.
- Deletes unnecessary header rows and keyword-based clutter.
- Inserts structural empty rows for readability.
- Separates test names, results counts, and total tests performed into dedicated columns.
- Adds metadata columns (`Month`, `Year`, `Month Number`).
- Produces a clean, analysis-ready dataset.

**Usage:**  
- Open the raw data file.
- Run the script to generate structured, clean data.

---

### 3️⃣ Cleaned Data Output

**File:** `Microbiology - Cleaned Data for Positivity by Test.xlsx`

- Example of a completed, cleaned dataset after script execution.
- Structured as:
  - **Column A:** Test Name
  - **Column B:** Result Type or Category
  - **Column D:** Result Count
  - **Column F:** Total Panel Tests Performed
  - **Columns G, H, I:** Metadata (Month Name, Year, Month Number)
- Ready for use in the positivity tracker file.

---

### 4️⃣ Positivity Tracker & Dashboard

**File:** `Microbiology - Figures for Positivity by Test.xlsx`

- Contains pivot tables, charts, and summaries based on the cleaned dataset.
- Visualizes test positivity trends over time.
- Supports infection control reporting, internal quality reviews, and anomaly detection.
- Designed for manual updates using cleaned datasets.

---

## 🛠️ Typical Workflow

1. **Export** raw data from lab system into `Microbiology - Raw Positivity Data.xlsx`.
2. **Run** the `MicrobiologyRawDataCleaner.ts` ExcelScript to clean and structure the data.
3. **Save** the cleaned output in `Microbiology - Cleaned Data for Positivity by Test.xlsx`.
4. **Analyze & Report** using the dashboard and charts in `Microbiology - Figures for Positivity by Test.xlsx`.

---

## 🎯 Benefits

- Standardizes positivity reporting for multiple microbiology tests.
- Saves time during monthly reporting cycles.
- Reduces errors from manual data cleaning.
- Supports data-driven infection control monitoring.

---

> All files and templates can be customized to fit specific laboratory workflows and reporting needs.
