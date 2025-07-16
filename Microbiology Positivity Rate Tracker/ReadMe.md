# Microbiology Positivity Rate Tracker

This Excel file was created as part of my work as a **Medical Technologist** to monitor **positivity rates** for various microbiology tests. It serves as a tool to visualize and track positivity trends across different test types, helping support quality control and infection monitoring efforts.

## 📂 File: `Microbiology - Figures for Positivity by Test.xlsx`

### 🦠 Purpose

- Track monthly positivity rates for microbiology tests.
- Monitor trends and variations in test positivity over time.
- Support reporting to infection control or quality departments.
- Assist in identifying unusual spikes in positivity rates.

### 📊 Features

- Tabular data organized by test type and month.
- Pre-built basic charts/graphs to visualize positivity trends.
- Designed for easy manual entry and monthly updates.
- Summary figures to assist with reporting and decision-making.

### ✅ Example Use Case

- Each month, test volumes and positive result counts are entered.
- The sheet calculates positivity percentages and visualizes them via charts.
- Data is reviewed by lab leadership, infection control, or quality assurance teams.
- Supports early detection of testing anomalies or outbreaks.

---

> The sheet can be customized for your facility’s test menu or reporting needs.

## 📜 Data Cleaning & Preparation Script

As part of preparing the raw microbiology test data, I developed an **ExcelScript** to automate data cleanup and formatting before analysis. This script standardizes the raw export into a tabular format suitable for positivity tracking and reporting.

### 🔍 Script Purpose

- Automatically clean and format raw microbiology report data.
- Remove unnecessary or empty rows.
- Insert headers and standardize column structure.
- Separate test names and result counts.
- Fill missing data for consistent tabular layout.
- Append metadata columns (Month, Year, Month Number) for tracking.

### ⚙️ How It Works

1. **Clear Formatting:** Removes all bold, italic, colors, and borders for a clean starting point.
2. **Delete Header Rows:** Removes the first three rows from raw data.
3. **Remove Empty Rows and Unwanted Keywords:** Deletes rows containing terms like "performing lab" or "mercy".
4. **Insert Empty Rows:** Adds empty rows before the first appearance of key test names to separate sections.
5. **Reformat Columns:**
   - Inserts new columns.
   - Populates column A with test names.
   - Moves results into appropriate columns.
   - Adds headers for easier analysis.
6. **Fill Down Values:** Ensures that test names, categories, and counts are consistently filled down.
7. **Add Metadata Columns:** Adds columns for month name, year, and month number to support time-based analysis.

### 📈 Example Use Case

- After exporting raw microbiology data:
  - Run the ExcelScript to transform and clean the data.
  - Use the processed sheet in the positivity tracker file (`Microbiology - Figures for Positivity by Test.xlsx`).
  - Analyze trends and visualize positivity rates using built-in charts.

---

> This script helps streamline reporting workflows and ensures consistency in data preparation before analysis.
