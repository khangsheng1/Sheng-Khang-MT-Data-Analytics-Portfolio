# Laboratory Excel Tools - Chemistry & Microbiology

This repository contains Excel tools and automation scripts developed during my work as a **Medical Technologist** to streamline chemistry and microbiology data management in the clinical laboratory. These resources support tracking reagent usage, monitoring inventory expiration dates, and analyzing microbiology test positivity rates.

---

## 📂 Repository Contents

### 1️⃣ Chemistry Usage Table

**File:** `Chemistry Usage Table.xlsx`

**Purpose:**  
- Track monthly reagent usage for chemistry analyzers.
- Summarize total consumption across multiple tests.
- Support monthly reporting and inventory planning.

**Features:**  
- Organized monthly tracking table.
- Auto-calculating totals for quick consumption review.
- Supports forecasting supply needs and identifying usage trends.

---

### 2️⃣ Chemistry Inventory Expiration List

**File:** `Chemistry - Inventory Expiration Date List.xlsx`

**Purpose:**  
- Track expiration dates of reagents and consumables.
- Prevent expired materials from being used in testing.
- Assist in proactive reordering and compliance documentation.

**Features:**  
- Simple table listing item names, lot numbers, quantities, and expiration dates.
- Sortable columns for identifying at-risk inventory.
- Supports monthly checks and documentation.

---

### 3️⃣ Microbiology Positivity Rate Tracker

**Files:**  
- `Microbiology - Figures for Positivity by Test.xlsx`  
- `Microbiology - Raw Positivity Data.xlsx`

**Purpose:**  
- Track and visualize positivity rates for microbiology PCR tests.
- Identify trends, detect anomalies, and support infection control reporting.

**Features:**  
- Tabular organization by test type and month.
- Built-in charts to visualize positivity trends.
- Supports reporting to leadership and infection control.

---

## ⚙️ Automated Data Processing Script

**Script Name:** `MicrobiologyRawDataCleaner.ts` (ExcelScript)

**Purpose:**  
- Clean and transform raw microbiology data exports into structured, tabular form for analysis.

**Main Functions:**  
- Clear all formatting for consistency.
- Remove unwanted rows (empty rows, keyword-based rows).
- Insert empty rows to improve data separation.
- Reorganize test names, results, and counts into clear columns.
- Fill down missing values to create a clean, analyzable dataset.
- Add metadata columns for reporting (Month Name, Year, Month Number).

**Usage Workflow:**  
1. Export raw microbiology data.
2. Run the ExcelScript to prepare the dataset.
3. Load the cleaned data into the positivity tracker for reporting.

---

## 💡 How These Tools Help

These resources help simplify routine operational tasks in the clinical laboratory:
- Improve accuracy and consistency in reagent tracking and inventory management.
- Streamline monthly reporting processes.
- Ensure timely action on soon-to-expire inventory.
- Enable clear visualization of positivity rate trends to support clinical decision-making.

---

> All templates are customizable to fit your laboratory’s specific analyzers, tests, and reporting needs.
